tags:: [[$NVDA]], [[CPU]], [[Arm]], [[Vera]], [[Grace]], [[$INTC]], [[$AMD]], [[$ARM]], [[agents]], [[key-person-risk]], [[Jensen Huang]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-11-19
file-updated-at:: 2026-11-19

- ## Nvidia's CPU effort: from a troubled Grace to a standalone Vera
	- **Source**: user-provided research excerpt, November 2026 (author and publication not given). The view that Vera is "on a more solid development path" and the point about founder persistence are the author's.
	- **Thesis**: Grace struggled mid-development, fell back on Arm's off-the-shelf cores, trailed x86 on performance, and sold mostly bundled with GPUs. Nvidia kept investing anyway. Vera, with Nvidia's own Olympus cores, entered mass production in 2026 and is Nvidia's first CPU sold as a standalone product. The author uses this as an example of multi-generation investment that survives setbacks, which the author argues is usually sustained only by a founder.

- ## Grace vs. Vera
	- | | Grace (first generation) | Vera (next generation) |
	  |---|---|---|
	  | CPU cores | Arm's off-the-shelf **Neoverse V2**, adopted after significant problems midway through development | Nvidia's own **Olympus** cores |
	  | Performance | Lagged x86 competitors | The author believes Vera is now on a more solid development path |
	  | How it is sold | Mainly **bundled with Nvidia GPUs** | **Offered as a standalone CPU for the first time**. Mass production began in 2026 |
	  | Volume or customers | Nearly **2.5M units shipped** cumulatively | Planned deployments at Meta, OCI, CoreWeave and others. Dell, HPE, Lenovo and Supermicro are expected to launch standalone Vera servers |

- ## The founder-persistence argument
	- **The author's point**: long-term investment that spans several product generations and tolerates setbacks is "often sustained only by a founder with the willingness and ability to stay the course." Grace's struggles did not stop the CPU program.
	- **Why it matters now**: Jensen Huang resigned on November 12, 2026 ([[2026-11-12-nvidia-huang-exit-hbm-vendor-agreements]]). The founder-dependence concern overlaps with the "exoskeleton around one man" argument in [[2026-11-18-nvidia-vanishing-moats-after-huang]].

- ## Related data in the repo
	- **Q3 FY2027 call**: CoreWeave, Meta, Nscale and OpenAI adopted the Vera CPU, joining AWS, OCI and SpaceXSI. Nvidia expects **total CPU revenue to more than double in FY2028**, as agentic AI drives CPU demand "far outstripping supply" ([[NVDA-2026-Q3]]).
	- **Positioning and size**: Dylan Patel cites **\$20B of Vera CPU revenue guidance** and describes Vera as having fewer than 100 fast cores. That suits AI workloads where GPUs stall waiting on a CPU, while high-core-count AMD and Graviton parts suit batched serving. Patel also warns that today's CPU surge is partly catch-up on GPUs shipped without attached CPUs ([[2026-07-16-dylan-patel-podcast-ai-infra-memory-cpu-optics-power]]).
	- **CPU shortage**: agent workloads are tightening general CPU supply, with allocation refusals, longer lead times and upfront-payment demands ([[2026-09-18-cpu-shortage-agents-cloud-capacity]], [[2026-11-16-daytona-burazin-cpu-shortage-upfront-payments]]).
	- **Arm adoption**: part of Google's reported Arm migration gain comes from Grace CPUs shipped inside GB200/GB300 racks, which ride on accelerator purchases ([[2026-10-16-google-x86-arm-warehouse-scale-migration]]).
