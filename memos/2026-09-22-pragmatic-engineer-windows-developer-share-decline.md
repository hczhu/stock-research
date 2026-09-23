- tags:: [[$MSFT]], [[$NVDA]], [[$QCOM]], [[$INTC]], [[$AMD]], [[$AAPL]], [[$ARM]], [[Windows]], [[Linux]], [[WSL]], [[developer-tools]], [[edge-AI]], [[inference]], [[agents]], [[MCP]], [[enterprise-software]], [[cybersecurity]], [[x86]], [[PC]], [[Copilot]], [[competitive-landscape]]

- **Source**: Gergely Orosz and Ivan Klaric, *The Pragmatic Engineer*, "How will AI change operating systems? Part 2: Windows," September 22 2026. Based on interviews with Pavan Davuluri (EVP, Windows and Devices), Scott Hanselman (VP, Microsoft CoreAI and GitHub) and Logan Iyer (CVP, Windows Platform and Developer). Part 1 covered Ubuntu. **Access-driven piece** — Microsoft supplied the interviews and most of the screenshots, so the roadmap claims are the company's own; the criticism is the authors'.

- **Thesis**: The developer-share decline is real but the financial exposure is small, because **Microsoft's developer franchise already decoupled from Windows** — VS Code, GitHub and Azure monetize on macOS and Linux. The tell is that Microsoft is open-sourcing its own agent primitives and shipping them cross-platform: **MXC runs on macOS and Linux, MAF is a library, Windows ML is built on ONNX.** What is genuinely Windows-exclusive is the *enterprise control plane* — Entra agent identity, Defender agent scanning, Intune policy management for agent containment — which is an E5 security-suite attach story, not a developer story. Read the article as a security-seat memo wearing a developer-relations costume.

- ## What the survey evidence actually supports

	- | Source | Sample | Finding |
	  |---|---|---|
	  | Statcounter | All desktop users | Windows ~63% overall share |
	  | Stack Overflow 2025 | 49,000 respondents | Windows still the single most popular professional OS, but used by a minority of devs; far below the XP-era 90%+ peak |
	  | JetBrains State of Developer Ecosystem 2025 | 24,500 responses | Half of devs use more than one OS; **macOS close to overtaking Windows** as the most-used standalone dev OS |
	  | Pragmatic Engineer X/LinkedIn poll, Sep 2026 | 9,937 responses | **Windows third, behind Linux and macOS** |

	- **The headline poll result is partly a measurement artifact and the authors say so themselves.** It was single-choice with **no WSL option** — and WSL is precisely the mechanism by which Windows usage hides. A dev running Ubuntu under WSL on a Windows box has no honest answer except "Linux." The poll structurally undercounts the thing the rest of the article argues is Microsoft's best asset.

	- The sample is also self-selected among the newsletter's readership, which over-indexes on VC-funded startups and Big Tech, where Macs have been the default for years. **The two credible surveys say "macOS is catching up"; only the unreliable one says "Windows is third."** Treat the direction as established and the magnitude as unmeasured.

	- Canonical's Jon Seager supplies the one counter-datapoint with real weight: **Ubuntu adoption via WSL is growing significantly faster than Ubuntu desktop adoption**, and he expects more Windows machines to run Ubuntu than native ones. Windows may be losing the survey question while keeping the hardware.

- ## The self-inflicted part, now being reversed

	- The article's own list of what drove developers away is almost entirely product decisions, not technical deficits: **mandatory Microsoft accounts** on Windows 11 (still required on a fresh install, and the only OS to demand a vendor account to install it), Start-menu and search clutter carrying ads and web results, removal of taskbar customization, and Copilot buttons pushed into Notepad, Paint and Photos — the immediate cause of "Microslop."

	- **Recall is the reputational core of it.** Announced May 2024, screenshots every few seconds indexed into a **local SQLite database in plaintext** with no redaction of banking or personal data and no way to turn it off; June 2024 GA cancelled; shipped opt-in April 2025. The authors' question is the right one — why would developers trust an OS vendor that only corrected after predictable public uproar?

	- Reversals now shipping: resizable Start menu, removable recommendations, repaired search, the **vertical taskbar restored after roughly five years**, Copilot icons removed from many surfaces, and **dev config** — a YAML machine-state file provisioned through WinGet with PowerShell for OS settings, terraform-style, handling multi-reboot setup unattended.

	- The investable read is not the feature list. It is that **a decade of accumulated product decisions took a dedicated team years to partially undo** — the same restaking-cost argument as [[2026-09-22-drew-cohen-piton-network-incumbent-constraint]]. Nothing here is technically hard; all of it was cheap to avoid and expensive to reverse.

- ## The agent primitives, and which of them are actually proprietary

	- **Agent identity via Entra ID.** Agents get local identities and appear as users in Task Manager alongside humans, so existing observability applies to them. **Defender is becoming "agent aware,"** scanning for known agent activity the way it scans for viruses — which is the explicit acknowledgment that an unregistered agent impersonating a user is indistinguishable from malware.

	- **On Device Agent Registry (ODR)** — the OS-level registry where agents discover and register local MCP servers, with built-in connectors for File Explorer and System Settings. Origin Technology's reverse engineering indicates **ODR inserts itself as a proxy between MCP client and server** (the process ID returned to the agent is ODR's own), which would let Windows inspect every payload. **Unconfirmed by Microsoft.** If true it is the most strategically significant detail in the article: a mandatory, inspectable choke point on all local tool traffic, owned by the OS vendor.

	- **Microsoft Execution Containers (MXC)** — JSON containment policies over five isolation levels (process, session, WSL container, lightweight Hyper-V, full VM), letting developers trade blast radius against start-up cost. It does not implement containment itself; it delegates to existing mechanisms, using **seatbelt on macOS**. OpenClaw for Windows is among the first adopters. Admin policy flows through **Intune**.

	- **Microsoft Agent Framework (MAF)** — C#, Python and Go, with tools, multi-turn sessions, persisted memory and a workflow engine.

	- **Sort the list by what is exclusive.** MXC and MAF are open source and cross-OS; Windows ML rides ONNX. Only **Entra identity, ODR and Defender/Intune** are Windows-bound, and all three are administrative rather than creative surfaces. Microsoft is not trying to make Windows the place agents are *built* — it is trying to make Windows the place fleets of agents are *governed*.

- ## Local inference: this source arms both sides of a debate the repo already holds

	- The repo carries a direct disagreement. [[2026-06-03-sinofsky-nvidia-spark-ai-pc-platform-shift]] argues token cost inevitably drives compute to local devices; [[2026-06-04-stratechery-nvidia-ai-pc-microsoft-solara-mai]] argues local inference is a fading bet and "thin is in."

	- **For Sinofsky**: a pre-release Surface with NVIDIA silicon ran Qwen locally against GitHub Copilot at **~40 tokens/sec**, which the authors judge usable for daily development. **Windows ML** removes the packaging obstacle — an ONNX-based, hardware-agnostic layer with per-vendor Execution Providers downloaded on demand and certified by Microsoft, replacing DirectML, which was GPU-only and gated on **driver updates that took about six months to reach meaningful adoption**. SLMs are being embedded in the OS itself, with **Aion-1.0-Instruct already shipping inside Edge** behind a Prompt API, so app developers stop paying per token for things like sentiment analysis. Microsoft has no frontier model, which sharpens the incentive.

	- **For Thompson**: **Copilot+ PCs, launched 2024, were a demand bust.** Three reasons given — missing games because kernel-level anti-cheat does not run on ARM, a price premium, and **NPUs never mattering** because the same features became available on any Windows 11 PC with a GPU. The only clear win was battery, at 20+ hours of video and 15+ hours of general use. Meanwhile the authors note that at Ramp and Uber developers run most AI harnesses in **cloud** environments, consistent with [[2026-09-13-pragmatic-engineer-codex-harness-shrinks-cloud-execution]].

	- **The synthesis is that the NPU bet failed and the GPU bet is still open.** The unit that made local inference usable was a discrete NVIDIA GPU, not the NPU the Copilot+ spec was built around. That is a negative read on the NPU-differentiated PC silicon story and a positive one on NVIDIA's client ambitions — and it means the 40 tok/s datapoint does not generalize to the installed base.

- ## The ARM transition priced as a restaking cost

	- Three attempts across more than a decade: **Windows RT (~2012)**, a tablet fork that could not run standard Windows apps and was abandoned; **Windows 10 on ARM (~2017)**, full x86 translation that was slow, drained batteries and **could not execute x64 apps at all**, arriving exactly as the industry abandoned 32-bit, so Photoshop and Chrome could not run; **Windows 11 on ARM (~2024)** with the **Prism** engine, which finally made 64-bit emulation responsive enough.

	- This is the clearest available illustration of the point in [[2026-09-21-expert-call-cpu-shortage-gpu-overbuild-correction]] that **legacy is a forward performance obligation**: the installed base did not merely need recompilation, it required kernel changes and a competitive emulator, and the bill came due over twelve years. Linux pays a smaller version of the same bill — **Chrome only reached ARM64 Linux in early August 2026**, and the holdouts are proprietary apps, not open-source ones.

	- The historical counterweight is that **Windows compatibility has decided ISA outcomes before**: it ran unmodified on AMD's backward-compatible x64 while Itanium demanded rebuilds, and Intel discontinued Itanium in 2021. Whoever Windows runs well on gets the volume.

- ## Silicon read-throughs

	- **[[$NVDA]]** — RTX Spark, announced early June 2026, pairs a 20-core Grace ARM CPU with a Blackwell GPU on one package, with a claimed **1 PFLOP of FP4**. Microsoft describes close collaboration on the silicon rather than acting as a passive OS supplier. The **October 7 Microsoft/NVIDIA event** is the near-dated item, and the thing to look for is a battery figure, since none has been published — that omission is conspicuous given battery was the only Copilot+ win.

	- **[[$QCOM]]** — Qualcomm was the Windows-on-ARM partner for the Copilot+ generation; NVIDIA arriving as the co-designed partner for the next one is a direct competitive negative for Qualcomm's PC franchise, which never got volume from the first attempt.

	- **[[$INTC]]** and **[[$AMD]]** — a credible ARM Windows machine removes the compatibility moat that has protected x86 on the client, and it arrives from a vendor that already owns the GPU the local-inference story depends on.

	- **[[$AAPL]]** — the authors credit Apple with getting the ARM transition right and name M-series performance as a reason Macs became the startup default. RTX Spark is the first Windows-side answer with comparable ambition, but Copilot+ is the precedent for treating announced specifications as unproven demand.

	- **[[$MSFT]]** — the Windows P&L is not where this lands. If the agent-governance surface (Entra identity, Defender agent scanning, Intune containment policy) becomes the way enterprises control agent fleets, the revenue shows up in the **security and management suite**, which attaches per seat and is far higher margin than an OS licence. That, not developer sentiment, is the line worth watching.
