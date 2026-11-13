tags:: [[$RBLX]], [[Roblox]], [[David-Baszucki]], [[Stratechery]], [[Ben-Thompson]], [[aggregation-theory]], [[gaming]], [[play-market]], [[Universal-Player]], [[Robloxification]], [[Roblox-Build]], [[Roblox-Everywhere]], [[Roblox-Reality]], [[discovery]], [[advertising]], [[AI-coding]], [[game-development]], [[UGC]], [[$U]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-11-12
file-updated-at:: 2026-11-12

- ## Roblox moves from game engine to aggregator of play
	- **Source**: Stratechery, Ben Thompson, "An Interview With Roblox CEO David Baszucki About Aggregating Play," Nov 12, 2026 (user-provided PDF of the transcript). It is Thompson's third interview with Baszucki, after Feb 2022 and Nov 2023.
	- **Thesis**: AI makes game creation abundant, so Roblox is repositioning from a 3D multiplayer engine to an aggregator of the whole **play market**.
		- It wants to pull every kind of game onto its rails: AI-made games through **Roblox Build**, imported games through **Universal Player** and **Robloxification**, and standalone apps through **Roblox Everywhere**.
		- It then wants to monetize the demand side: discovery, the social graph, the economy, safety and user-acquisition ads.
		- Baszucki's own phrasing of the strategy: ^^**"do everything within the carefully thought-out boundaries of the future of play."**^^
	- Related: [[RBLX-2026-Q3]] (the formal roadmap and AI metrics), [[2026-09-11-roblox-rdc-2026-platform-creator-tools]], [[2026-06-25-roblox-retention-first-discovery-algorithm-change]], [[2026-11-11-solo-dev-ai-game-making-last-15-percent-ui-ux-door-problem]].
- ## Data points from Baszucki
	- ^^**"in under 18 on Roblox, we've shared we may have literally 20% of gaming revenue in the U.S. flowing through the platform"**^^
	- | Metric | What was said |
	  |---|---|
	  | U.S. under-18 gaming revenue | About **20%** flows through Roblox. The aim is to reach "that same penetration over 18" |
	  | Daily users | "Well over **100 million** people coming every day" |
	  | Fastest-growing cohort | **18 and up**, "growing very fast," from new users and from users aging up. Smaller than under-18 |
	  | MCP usage (Claude Code, Codex and other agents plugged into Roblox Studio) | **5×** quarter over quarter (Thompson's citation of the earnings call; Baszucki didn't dispute it) |
	  | AI-made hits | **Two games in the top 20** made by AI. **80% of the top 100** have AI-contributed content |
	  | Roblox Build | "Not tens or hundreds, but **thousands** of games" published, some already earning money. Canada went live around the interview date; Serbia and New Zealand are in testing; not yet live in the U.S. |
	  | Usage inside Roblox | Board members build games on their phones "like **15 times a day**." Non-engineers inside the company now build |
	  | Game load time | Typical games launch in **5–7 seconds**, the window for pre-roll ads |
	  | Engineering speed | Teams now rethink "a nine-month project" as "a **two-month** project" |
	- *My note*: the Q3 call gave **70,000** Build games across four test markets ([[RBLX-2026-Q3]]). The "thousands" here is an understatement or a different count. Canada going live is new since the call.
- ## From the game market to the play market
	- **Three realizations**:
		- **Play is more than games**: in the physical world, play also means "connecting, it's community, it's creating the play… watching other people's play, it's dressing up to play." So "we started thinking about the market, not as the game market, but the play market."
		- **Roblox can no longer be "a 3D multiplayer game engine."** "All of the constraints… that helped us focus and grow at a certain scale have to flip from focusing constraints to constraints we give up on."
		- **A simpler, more fun spec**: "it's so much more fun and simple to just say, 'We're going after the play market.'"
	- **A history of dropped constraints**:
		- PC/Mac only, followed by a "giant company debate" over whether 3D could work on phones.
		- No imported 3D meshes, later reversed ("mea culpa'd it").
		- 2D and offline play is "one of the last holdouts."
	- **Thompson's challenge, "Let's literally do everything"**: Baszucki narrowed it to the line in the thesis. The boundaries run from 2D puzzle games to photorealistic Roblox Reality, from a 2GB Android phone to a high-end PC, and from inside the Roblox app to Roblox Everywhere. "It is focused, because there's still some pretty tight guardrails."
	- **Why now**: AI expands the product spec and AI engineering delivers it, "back and forth, iterate, iterate."
- ## Products and roadmap
	- **Roblox Build (creation)**:
		- Prompt-to-game on a phone, which Baszucki frames as the short-form video of games. "We're entering an era where making a game could be as big as playing a game." It revives the founding slogan "You Make the Game."
		- **Game creation harness vs coding harness**: a game spans art, 3D objects, scenes, avatars, NPCs, missions and code. The harness routes by asset type, and across several models within each type.
		- **Model mix**: frontier models, open-source models and Roblox's own models all run in Build, with cheaper open-source models used where they are good enough. The **Cube** model is trained on opted-in Roblox 3D assets and runs on Roblox's own hardware. Roblox has proprietary data for NPC behavior.
		- **Pricing**: aiming to be "free for everyone," with heavy iterators able to "buy tokens."
		- **Feedback loop**: a creator watches "four people in my game" and edits it until it becomes six. Thompson calls it a "4D" social object, one that changes in response to its players.
	- **Universal Player (running any game)**:
		- "A superset of all games that can run multiplayer," from "a traditional 2D offline puzzle game" to "super high-scale multiplayer, photorealistic reality."
		- The analogy is video: any video plays on any 4K TV, but "there's not a universal rail" for games.
		- Imported games become discoverable in the Roblox app, which answers Thompson's point that users won't download a game separately.
	- **Robloxification (what an imported game gains)**:
		- A single-player PC game becomes **multiplayer by default**, because it runs against Roblox's cloud.
		- It **runs on phones** through 3D streaming.
		- Players **join instantly** instead of downloading 500GB.
		- It gets **access to Roblox's economy** and other services.
	- **Roblox Everywhere (shipping outside the app)**:
		- Ends the rule that "100% everything is in the Roblox app." Creators can ship standalone games to the iOS App Store, Google Play, PC and consoles using Universal Player.
		- **Roblox's payoff**: that content "can then be available for discovery in the app." Baszucki's calculus is that it is "the best way to grow users in the Roblox app itself."
		- **Roblox-published copies**: with the developer's permission, in-app hits could appear in app stores. Example: searching "Grow a Garden" in an app store.
		- **Economics for developers publishing directly**: not yet disclosed, but they will need to be "pretty provocative" to remove "any reason for the creator not to think about it."
		- **Other selling points**: a high-end PC player and a 2GB Android phone player can share the same game. The platform automatically adjusts to each jurisdiction's age, rating and cultural rules.
		- **Not cloud gaming**: Baszucki rejects video streaming (Gaikai, OnLive), which adds 50–100ms of latency, in favor of "multi-device native 3D, very low latency."
	- **Roblox Reality (photorealism)**:
		- Synchronizes 10,000 players in an efficient rough 3D representation. Each player's view is upsampled by a real-time AI video model to look like 4K, 60Hz photorealism. The analogy is hybrid filmmaking.
		- It works "out of the box" on early tests with Grow a Garden.
		- Baszucki calls it both a technology play (a low-latency video model conditioned on 3D and depth maps, unlike single-player world models) and a vertical-integration play.
	- **Discovery**:
		- The ranking objective changed from short-term to **long-term retention**, measured "from every user-game pair." Adopt Me is the example of a game that lasts for years.
		- With more games, **content understanding** matters. Every game runs in Roblox's cloud, so Roblox can inspect it and surface novel ones, even "1 in 100" inside "AI slop."
		- A planned short-form-video-like feed shows 3D games friends are already playing, to "jump into a game."
	- **Advertising**:
		- **User-acquisition ads**: these are accelerating, bought by creators who need "a thousand users."
		- **Pre-roll video**: Roblox is bringing back short, skippable pre-roll video (5+ seconds), shown during game load from carefully chosen brands. An earlier 30–45-second pre-roll test was pulled.
		- **Constraints**: "COPPA-compliant, privacy-compliant, Roblox-values-compliant."
		- **Paid acquisition for adults**: mixed with organic growth, on the rule that spend must earn back more incremental revenue than it costs.
- ## My notes
	- **The aggregator logic**: this is the supply-flood scenario from [[2026-11-11-solo-dev-ai-game-making-last-15-percent-ui-ux-door-problem]], seen from the platform side.
		- AI makes most of the production work cheap. The scarce inputs become discovery, friends, safety and an economy, which Roblox already runs at 100M+ daily users.
		- Baszucki's YouTube analogy makes the same point: anyone could rebuild YouTube with AI, but people still go to YouTube.
	- **The 20% figure sets up ads**: Roblox's demand-side power is concentrated under 18 in the U.S.
		- Every new AI-made or imported game needs players, so the supply flood becomes demand for user-acquisition ads on Roblox. Thompson's framing: "better than spending on Meta."
		- How valuable that inventory is depends on adults catching up to under-18 penetration. Baszucki says adults are the fastest-growing cohort, but gives no share number for them.
	- **Roblox Everywhere goes against usual aggregator logic**:
		- Aggregators usually keep supply inside the app. Here Roblox lets content leave, betting that the engine brings content back for discovery.
		- That makes Roblox a cross-platform engine competing with Unity ($U) and Unreal for developers. The "provocative" pricing points to fees below theirs.
		- The open question is whether developers who already reach players outside Roblox still need Roblox's discovery. The economics haven't been shared.
	- **Doing everything at once**: Build, Universal Player, Everywhere, Reality, 2D/offline, ads and the adult push are all under way together.
		- Baszucki's answer is AI-accelerated engineering (nine months to two). Model inference for Build and Reality also adds cost, and Q3 free cash flow fell 18% YoY ([[RBLX-2026-Q3]]).
		- No dates were given in the interview. The Q3 call put Everywhere's first native titles and Reality's early access in H1 2027.
	- **Universal Player is still an ambition**:
		- Baszucki concedes a 100,000-player photorealistic California is "not technically possible" today.
		- Converting existing PC or console games depends on rights holders and on how well AI-assisted porting works. A similar approach worked for Google's x86-to-Arm migration ([[2026-10-16-google-x86-arm-warehouse-scale-migration]]), but game engines are far less uniform than one company's codebase.
