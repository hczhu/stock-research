tags:: [[$U]], [[Unity]], [[Epic-Games]], [[Unreal-Engine]], [[game-engine]], [[video-games]], [[coding-agents]], [[MCP]], [[Godot]], [[Anthropic]], [[competitive-landscape]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-11-20
file-updated-at:: 2026-11-20

- ## Epic rebuilds Unreal Engine for AI agents
	- **Source**: Matthew S. Smith, "Will AI Coding Eat Video Game Engines?", IEEE Spectrum, November 18, 2026 (user-provided PDF). It quotes Epic COO Daniel Vogel, Epic EVP of development Marcus Wassmer, indie developer Travis McGeathy and gameplay engineer Ryan Barker.
	- **Thesis**: AI coding agents threaten the value of game-engine editors that took decades to build. Epic's answer is to make **Unreal Engine 6 (UE6) built for agents**: all code moves to the text-based Verse language, the engine is exposed through APIs, and assets are stored as text. Vogel: "if Unreal Engine was static, what's the value at the end of next year? This is why we are pivoting hard towards velocity."
	- **Owner's take**: an AI-native Unreal will **lower the barrier to making games on Unreal** and **eat into Unity's low-end market**.

- ## The threat to game engines
	- **Rebuilding without the editor**: when Seeker Entertainment ran out of money in September, its Unreal 5.7 game KinForge lost its AWS servers and became unplayable. Co-founder McGeathy pointed **Claude Code** at the project. In about **four hours** of mostly hands-off work, it added peer-to-peer play over the internet and LAN, and even persistent save states, without going through Unreal's editor UI.
	- **Building the engine itself**: **Fable 5.2**, Anthropic's model released November 9, can generate a 3D game with a custom engine in the style of Call of Duty.
	- **Lower switching costs**: "AI made transitioning from using Unreal into Godot trivial" (McGeathy, an Unreal veteran new to Godot). Barker used an LLM to build the same physics test scenes in Unreal and Godot to compare them.
	- **Why most studios will still use an engine**: McGeathy: "Your goal as a game developer is to make a game. It's not to make a game engine." Wassmer: "You still have to burn a lot of tokens to get something of scale that is optimized and that runs across all platforms."

- ## What Epic is changing in UE6
	- | Change | From | To | Why it matters for AI |
	  |---|---|---|---|
	  | Gameplay scripting | **Blueprints** (visual node graphs, stored as binary files) and C++ | **Verse**, a strict text language from Fortnite (2023) whose compiler catches errors before code runs | LLMs "would much rather work with the code" and can't read Blueprint binaries. Blueprints will be removed in UE6, even though Blueprint-heavy *Clair Obscur: Expedition 33* won awards |
	  | World model | Object-oriented actor framework | **Scene Graph** (2024), similar to an entity component system | Better performance and less duplicate code. It is harder for humans to code around, but an LLM can manage that complexity |
	  | Tool access | Agents use an MCP server that sends commands to the editor | Modular engine with systems exposed through APIs. **"Python All The Things"** makes the whole editor scriptable | Agents avoid slow, unreliable computer use |
	  | Assets | Mostly binary | More assets stored as text, plus a command-line tool for the remaining binary files | Agents can edit assets without loading the full editor |
	  | Editor role | Moving things around visually | Seeing project context and making tweaks. **Unreal Canvas** in UE 5.9 (developer preview, November 9) is a Miro-like collaborative workspace for working with agents | Vogel: "You're not going to move stuff visually in the editor. Those times are gone" |
	- **Openness**: Epic won't block developers from converting to other engines. "Our explicit goal is to be able to interoperate with other ecosystems and other games" (Wassmer).
	- **Starting position**: Unreal is the second most-used engine after Unity and first by games sold.

- ## How this fits the owner's take
	- **Evidence for the owner's take**:
		- Unity's stronghold is small games, about 50% of games selling under 100K units vs. 23–27% for Unreal, while Unreal leads in large games ([[2026-11-20-game-engine-share-unity-vs-unreal-vgi-steam-2024]]).
		- Unreal's barrier to entry has been complexity: a Microsoft developer described its real-time systems as heavy, needing large teams to optimize ([[2026-03-28-microsoft-game-unity-unreal-engine]]). Text-based, agent-driven Unreal lowers exactly that barrier.
	- **Evidence from the sources that cuts both ways**:
		- **Unity is making the same move**: it opened its editor to coding agents and added a command-line interface in August. Creator daily active users are **up 25%** since then. Its **Unity Spark** no-code platform with Google launches fully in 2027 ([[U-2026-Q3]]).
		- **Switching gets cheaper in every direction**: AI made moving from Unreal to **Godot**, a free and open-source engine, "trivial." Lower switching costs may help free engines as much as Unreal at the low end.
		- **Some developers may skip engines**: frontier models can now generate small games with custom engines, which pressures every engine's low end, Unity's and Unreal's alike.
	- **Related**: Casey Muratori argues the games industry already showed what happens when a technical barrier to entry gets commoditized ([[2026-09-13-casey-muratori-performance-games-engines-as-ai-preview]]).
