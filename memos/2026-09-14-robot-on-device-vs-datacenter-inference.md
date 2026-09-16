- tags:: [[robotics]] [[humanoid]] [[inference]] [[edge-AI]] [[data-center]] [[networking]] [[GPU]] [[LPDDR]] [[DRAM]] [[TCO]] [[SemiAnalysis]] [[$NVDA]] [[$GOOGL]]
-
- ## Where Does a Robot Think? On-device versus datacenter inference
	- **Source**: SemiAnalysis, "A Brain Too Big to Carry - On-Device vs Datacenter Inference," September 14, 2026. The supplied PDF includes company interviews, SemiAnalysis hardware and TCO models, and reader criticism of the TCO assumptions.
	- **Thesis**: General-purpose robots are likely to use a hybrid architecture: hard-real-time motion and safety remain onboard, while large planning and reasoning models can move to shared datacenter or on-premise GPUs. Offload becomes silicon-, memory-, and potentially cost-efficient at sufficient fleet density, but unreliable wireless links and questionable utilization assumptions make fully remote inference unsuitable for many early deployments. [[$NVDA]] benefits under either architecture through Jetson at the edge and Blackwell in the datacenter; [[$GOOGL]] gains a robotics inference foothold through Boston Dynamics' use of Gemini and TPUs.
-
- ## The workload naturally splits by latency
	- | Robot layer | Typical frequency and budget | Likely compute location |
	  |---|---|---|
	  | Servo and safety | **Above 200 Hz**; balance, contact, collision response and actuator control | Always onboard |
	  | Action and motion | Roughly **20-100 Hz**; a 100 Hz loop has only **10 ms** per output | Onboard because a wireless round trip can consume the full budget |
	  | Planning and reasoning | Generally **below 20 Hz**; a 5 Hz planner has **200 ms** per decision | Can be offloaded when connectivity is predictable |
	- Typical wireless round-trip latency is **10-50 ms**, with a well-engineered link below 10 ms. Average delay can be planned around; unpredictable tail latency and jitter are harder because the robot cannot know when the next command will arrive.
	- Safety cannot depend on the network. Loss of connectivity to an offboard safety model would force a blind fail-safe, so perception-to-actuation safeguards must remain local even if cognition is remote.
	- The most plausible architecture is therefore not cloud *or* edge, but a hierarchy: onboard control plus an offboard planner, fleet orchestrator, training pipeline, and data layer.
-
- ## Model scale is already pressing against robot hardware
	- Generalist robot models remain much smaller than frontier language models: Physical Intelligence's π0 is about **3B parameters**, π0.7 **5B**, ByteDance GR-3 **4B**, Generalist roughly **10B**, and NVIDIA DreamZero **14B**.
	- Small parameter counts reflect limited robotics data and onboard constraints, not evidence that capability has stopped scaling.
	- DreamZero needs **two GB200 GPUs** off-robot for real-time inference, while the later **3B-parameter RoboTTT** uses test-time training and minutes of context to fit onboard. The field has not converged on one model architecture or compute envelope.
	- Jetson Thor supplies roughly **one-tenth the FLOPs** and **one-thirtieth the memory bandwidth** of a GB200. Large multimodal reasoning models therefore cannot simply be moved onto today's robot module.
	- A rack GPU draws roughly **1.2-1.4 kW per chip**, versus approximately **40-130 W** for Jetson Thor. A humanoid may carry only about **2 kWh** of battery, making datacenter-class compute and cooling physically impractical onboard.
-
- ## Shared compute can reduce scarce silicon and memory per robot
	- Jetson memory has doubled by generation: Xavier carried **32 GB**, AGX Orin **64 GB**, and Jetson Thor **128 GB of LPDDR5X**.
	- Robot modules increasingly compete for the same leading-edge capacity as datacenter accelerators: Orin used Samsung SF8, Thor moved to TSMC N4, and the report expects future generations to track N3 and N2.
	- Datacenter GPUs currently earn estimated gross margins in the mid-to-high 70% range versus the mid-60% range for Jetson modules, giving NVIDIA an incentive to prioritize scarce wafers for datacenter products until robot demand scales.
	- The report estimates that **1 million** approximately 400 mm² Jetson-class chips in 2030 would consume only about **10,000 wafers annually**. Robotics does not become a meaningful front-end capacity burden until volumes reach tens of millions.
	- The relevant comparison is resource use per deployed robot:
		- Shared datacenter compute crosses below onboard silicon consumption at roughly **7 robots per GPU**.
		- Shared compute crosses below onboard DRAM consumption at roughly **5 robots per GPU**.
	- These crossover estimates are model-dependent, but the direction is robust: pooling is most valuable when expensive compute and memory would otherwise sit idle in every robot.
-
- ## TCO model: offload wins only after utilization and batching assumptions
	- The benchmark reconstructs NVIDIA RoboTTT's timing profile because public code and weights are unavailable. It measures serving cost rather than task accuracy; the inserted fast-weight path produces unusable actions.
	- SemiAnalysis estimates one B300 can serve **12 robots** and one RTX 6000 Pro can serve **4 robots** within a **500 ms p99 chunk deadline**.
	- | Configuration for 96 robots | Upfront capital | Aggregate TCO per hour | Modeled role |
	  |---|---:|---:|---|
	  | B300 offload server plus wireless boards | **~\$554K** | **\$18.63** | 12 robots per GPU |
	  | Three 8-GPU RTX 6000 Pro servers | **~\$436K** | **\$15.61** | 4 robots per GPU |
	  | 96 Jetson Thor modules and supporting hardware | **~\$394K** | **\$14.97** | One module per robot |
	- Before utilization adjustments, Jetson has the lowest total fleet TCO. The report's offload advantage is instead expressed per theoretical FP4 FLOP: B300 **\$0.15/hour/PFLOP**, Jetson Thor **\$0.16**, and RTX 6000 Pro **\$0.39**.
	- The base case assumes **90% B300 utilization** and **40% onboard utilization**. After adjustment, B300 is modeled at **\$0.17/hour/PFLOP** versus **\$0.37** for Jetson, or about **46%** of the onboard cost.
	- Home robots reportedly operate only **1-2 hours per day** today, or **4-8% utilization**, with a path toward 4-5 hours. Figure's BMW deployment logged roughly **1,250 operating hours over 11 months**, around 10 hours per weekday at approximately **40% utilization**.
	- For an industrial deployment, the report finds B300 cost per FLOP becomes favorable from about **5 robots per GPU**.
	- **Modeling caution**: cost per theoretical FLOP is not cost per robot or successful task. The PDF's reader discussion also questions whether a latency-sensitive local server can simultaneously achieve 90% utilization, and whether unused B300 FLOPs should be credited when they do not support more robots within the deadline. The exact TCO conclusion is therefore weaker than the architectural pooling argument.
-
- ## Deployment evidence favors different splits by environment
	- | Company | Current inference split | Reason |
	  |---|---|---|
	  | Boston Dynamics | Atlas runs the visuomotor policy on Jetson Thor; high-level System 2 reasoning runs on Google TPUs through Gemini/DeepMind | Factory generality requires a model too large to carry; the planner is queried every few seconds and sometimes once or twice per second |
	  | Agility Robotics | Digit keeps perception, action, and safety onboard; fleet orchestration, mapping, updates, data uploads, and teleoperation use the cloud | Factory wireless is difficult and Agility wants minimal changes to customer infrastructure |
	  | Verne Robotics | End-to-end policies run locally on Jetson-class or RTX 50-series hardware | Warehouse and light-manufacturing tasks do not yet require broad open-world reasoning |
	  | Sunday Robotics | Moved ACT-2 from cloud inference to fully onboard execution after real-home trials | WiFi latency was acceptable, but dead zones and jitter prevented sustained reliability |
	  | Weave Robotics | Likely local policy inference; network remains necessary for training-data uploads and teleoperation | Consumer routers and home dead zones make the link unreliable for the critical path |
	- Sunday reports **99.1% zero-shot success** folding nine garment types in unseen homes. Without pretraining, performance was **96% in-domain versus 14% out-of-domain**; with its full pretraining corpus, both reached 100% in the cited evaluation. This supports scaling robot pretraining, but not necessarily cloud inference.
	- The deployment pattern is consistent: bounded industrial sites with valuable general-purpose fleets are the best offload candidates; homes favor onboard inference until networking improves; open-road autonomy requires local inference because the operator cannot control RF conditions.
-
- ## Networking becomes part of the robotics compute stack
	- Robot traffic inverts consumer-network design: continuous, latency-sensitive video travels **upstream**, while most WiFi and broadband infrastructure is optimized for downstream traffic.
	- Deterministic offload requires robot-aware uplink scheduling, location-aware beamforming, centralized timing, multi-link WiFi/5G redundancy, clean 6 GHz spectrum, and handoffs completed within the observation cadence.
	- Typical access-point roaming can interrupt traffic for **10 ms to several seconds**, long enough to drop multiple frames, break a policy, or destabilize teleoperation.
	- Fleet batching also requires sub-millisecond clock synchronization so observations arrive together and late frames move to the next batch rather than blocking inference.
	- The network is therefore not a commodity connection in the offload case; radios, access points, site surveys, orchestration, and GPU scheduling must be co-designed. This adds deployment cost that can erode the modeled datacenter advantage.
-
- ## Public-company exposure
	- **[[$NVDA]] wins both sides near term**: Jetson is the standard onboard module, while B300 benefits if high-level reasoning migrates to pooled GPUs. Hybrid architectures may increase total NVIDIA content rather than substitute one product for another.
	- NVIDIA's constraint is allocation: low-volume Jetson competes with higher-margin datacenter GPUs for advanced nodes. Robot demand must become material before edge supply earns equal priority.
	- **[[$GOOGL]] has an early strategic position** through Boston Dynamics' use of Gemini embodied reasoning and Google TPUs. Robotics could become another captive inference workload for Google's model-plus-infrastructure stack.
	- **LPDDR demand rises in either outcome**: every capable onboard robot adds high-capacity LPDDR, while offload reduces DRAM per robot only when enough machines share each GPU. Fleet density determines whether robotics is primarily an edge-memory or datacenter-memory workload.
	- The report is most bullish for providers that can sell a complete hybrid stack—onboard modules, datacenter accelerators, networking, orchestration, and model software—rather than for a pure cloud or pure edge vendor.
