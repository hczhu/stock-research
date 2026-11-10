tags:: [[$SNAP]], [[Snap]], [[Evan-Spiegel]], [[Specs]], [[AR]], [[augmented-reality]], [[smart-glasses]], [[wearables]], [[messaging]], [[social-media]], [[subscriptions]], [[Snapchat-Plus]], [[AI-coding]], [[distribution]], [[teen-safety]], [[content-moderation]], [[$META]], [[$AAPL]], [[$GOOGL]], [[podcast]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-11-10

- ## Evan Spiegel on Cheeky Pint: Specs, AI-written code and why close friends beat network size
	- **Source**: *Cheeky Pint* podcast, John Collison (Stripe) with Snap CEO Evan Spiegel. User-provided auto-generated transcript, undated. Spiegel says Specs reach consumers "later this year," so it was recorded in 2026 before launch.
		- Figures are Spiegel's spoken claims, not filings.
		- Related: [[2026-06-18-snap-specs-ar-glasses-launch-awe]] (Specs price, weight, battery), [[2026-11-10-cheeky-pint-meta-muse-wonder-training-msl-anecdotes]] (Meta's glasses and agent view), [[2026-08-26-meta-state-ag-teen-safety-agreement]], [[2026-02-19-zuckerberg-testimony-teen-revenue-share-age-verification]].
	- **Thesis**: Spiegel describes 2026 as Snap's "crucible moment."
		- Snapchat is near **1B monthly active users** and **net income profitability**.
		- Specs, see-through AR glasses with full spatial computing, launch to consumers after 12 years of work.
		- AI is changing how Snap builds software.
		- His bet on Specs is that AI-made software removes the app-store lock-in that has kept new computing platforms from getting started. His bet on the core app is that what matters is who you talk to, not how big your network is.
- ## Business data points
	- | Metric | Spiegel's figure | Note |
	  |---|---|---|
	  | Monthly active users | "About to reach a billion" | |
	  | Profitability | "On the verge of net income profitability" | Even with heavy hardware spending on Specs |
	  | Snapchat+ subscribers | **25M** | |
	  | Direct revenue run rate | **Over \$1B** | Built mostly over the last 2–3 years |
	  | Selfies on Snapchat | **Over 1 trillion** in a year | Apple announced about 500B on iPhone over the same period. Spiegel says Snap "low-balled" its public number. Collison works it out to about 1,000 per user per year |
	  | New code written by AI | **More than two-thirds** | "That's happened really, really quickly" |
	  | Specs development | Since about 2014 | Google Glass came out in 2013. Snap's first camera glasses were more than a decade ago |
	- **Two revenue streams**:
		- **Advertising**, including Promoted Places on the Snap Map with closed-loop measurement of store visits. "A lot of folks care right now about driving folks into their retail locations."
		- **Direct revenue**: Snapchat+ and a Lens+ tier that unlocks more AI and editing tools.
	- **Snap's camera is a large AI generation platform**: "the Snapchat camera is one of the largest image and video generation platforms in the world, just given the frequency of engagement." Snap is also building its own video foundation models.
	- **Why subscriptions work for Snap**: power users always asked for niche features like app themes that Snap never had staff to build. Snapchat+ pays for that list. Paying and free users don't want different things; paying users are the most passionate ones.
	- **Snap's competitors are messaging apps first, camera apps second**: the contest is whether you open the Snap camera or the lock-screen camera when something happens. Netflix-style entertainment isn't the main rival.
- ## AI inside Snap: first-hand examples
	- **More than two-thirds of new code is AI-written**, and Claude is "transforming software development full-stop at Snap in every part of our organization."
	- **Saturn's \$100K tool, replaced in a day**: the team behind Saturn, Snap's calendar app for friends and family, was paying for an enterprise bug-reporting service that "probably costs like \$100,000 a year." They built a replacement in a day. More important to Spiegel, they said it was a better tool because it was built for them.
	- **Designers ship code**: "Here's my PR" for features stuck in the backlog. Spiegel reviews hundreds of ideas a week in a couple of hours with the design team, and more of them now arrive as working prototypes.
	- **Half a person per new app**: "every time we'd kicked around … an idea for a new app … I don't think we can spare 15 people." Now "with half a … team member's time, we can build a totally new service and distribute it through Snapchat." That makes a multi-app strategy possible.
	- **Network effects protect Snap**: "we're so fortunate to be in a software business that has network effects, thank God." Spiegel thinks that shields Snap from the AI cannibalization hitting other software companies.
	- **Distribution is worth more**: as building gets easier, "people are going to reallocate more resources away from things like software engineering … to distribution." It's harder for brands to get noticed, which makes Snap's reach more valuable.
- ## Specs: product and technical insights
	- **The gap in the market**:
		- Today there are low-capability AI or camera glasses ("AirPods with a camera") and high-capability passthrough VR like Vision Pro.
		- Specs aim for normal-glasses wearability with full spatial-computer capability. Spiegel says that space is "unoccupied today."
	- **Snap owns the whole stack**:
		- Developer tools: Lens Studio, becoming more agentic.
		- Rendering engine: Lens Core, tuned for a decade on low-end phones, which helps with power and heat on glasses.
		- Snap OS: built from scratch on Linux. "Android is way too bloated to work effectively on a pair of glasses."
		- Optics: Snap's own optical engine, waveguide and projector, plus "some other fancy stuff that we haven't announced yet."
	- **Google's approach as a contrast**: Spiegel says Google's latest glasses project "has a huge compute pack. We just don't think it's realistic for people to carry around a compute pack."
	- **Key parts made in-house in the US and UK**: the most IP-sensitive components sit next to R&D for fast iteration. Spiegel says this is how Snap leads on display: waveguide resolution and performance "far exceed" competitors'. Hardware IP is "way easier to protect … compared to software, especially today in the age of AI."
	- **Snap's 10× rule**: Snap doesn't build a new product unless it is 10× better than the next best option. Camera-only glasses fail that test:
		- They sell for about \$150–200 and buyers won't pay more.
		- They have no operating system and don't understand the world or run apps, so they can't become a platform. Rivals will undercut them on price.
		- The phone or a GoPro is good enough. Snap learned this "the hard way" with its own camera glasses.
	- **First use cases**:
		- **Screens go first**: "Why would you pay thousands of dollars to put two or three TVs in your home" when glasses give you any size of screen? The same goes for laptop or desktop displays, especially on planes.
		- **New experiences matter more to Snap**: laser tag with kids, dinosaurs in the backyard, building Lego together.
		- **Watching AI agents from glasses**: developers have already built Specs lenses to check on coding agents. Collison: "the senior people have the smallest screen."
	- **No killer app needed**: "the killer app concept is a little bit of a mirage." With software this easy to write, users will build their own tools. That gets past the old obstacle for new platforms, the "one million apps or two million apps on the App Store." Spiegel points to the iOS app submissions chart, which was flat and is now "exploding."
	- **Launch plan**: early adopters first. The 1984 Macintosh cost about \$8,000 in 2026 dollars; Specs "certainly won't be \$8,000." (The June AWE memo has pre-orders at \$2,195.) New lenses for Specs are published almost every day.
	- **VR stays a niche**: Spiegel expects it only for things like training and flight simulators. "I can't imagine a huge swath of humanity wanting to interact with the world through a screen."
	- **Phones stay central**: Spiegel doesn't think we move beyond the smartphone. Desktops remain best for word processing and getting things done, phones for mobile messaging, and glasses for shared experiences.
- ## Social network design: Snap's two findings
	- **1. Who you talk to beats how big your network is.**
		- Most conversations are with a handful of people: a spouse, close friends, a few co-workers. Snap is a messaging service, so it delivers most of its value with "one friend, two friends, three friends."
		- This is why Snap could grow when everyone said it could never compete with Meta's bigger network.
		- Spiegel's personal example: the best part of his day is snaps from his wife of their two-year-old.
	- **2. Separate social from media (Snap's 2016–17 principle).**
		- Facebook's news feed needed more content, so it pushed users to add more friends. Past a certain point people didn't know who would see their posts, so they stopped posting. Facebook then filled the feed with public content.
		- Snap instead opened up publisher and creator content early, through Discover. It was "one of the first companies to actually rank that content with AI," so users never had to add friends to have something to watch.
		- No public comments on stories: "you can't be embarrassed by your aunt on Snapchat."
	- **Streaks, which Spiegel tried to kill**:
		- Snap is "anti-metric," with almost no user-facing numbers, and Spiegel "fought very hard to kill streaks over the years."
		- Emails to his public address changed his mind. One user moved across the world, divorced and changed jobs, and kept in touch with a best friend every day through a streak. "Sometimes having an invitation to communicate … is so important."
	- **Norway first**:
		- Snapchat's first traction was only in Norway. After raising "\$400,000 or something," the founders flew there and were recognized in a 7-Eleven.
		- Spiegel's explanation: Norway had high-end iPhones and cheap, good mobile data when Snapchat was iPhone-only and data-heavy (around 2012), and a culture that values close family and friends. Norway is "still" strong for Snap.
	- **Most data should be temporary**: Spiegel expects people to save what matters and let the rest disappear, as humans always have. Most messaging apps have since adopted deletion settings, which seemed "crazy" when Snap argued for it in 2012.
- ## Teens, regulation and moderation
	- **Australia's under-16 ban is easy to get around**:
		- It covers only a short list of named apps, so teens move to clone apps; "there are millions of apps in the app store."
		- Age checks rely on face scans or government IDs, and many teens have no ID.
		- Spiegel's alternative is operating-system controls such as Apple's Screen Time, which his family uses for their 15-year-old. He wants governments to teach parents about those tools.
	- **Studies Spiegel cites**: he says three or more independent studies Snap didn't fund (Australia, possibly the Netherlands, the US) found Snapchat positively associated with wellbeing and relationships, while TikTok and Instagram were negatively associated. His reasoning: relationships are the top predictor of good mental health, and Snap is built around real friends. *The studies aren't named in the transcript.*
	- **Moderate the content, not the algorithm**: "people have focused far too much on the algorithms and not enough on the content." Snap has moderated all public content since Discover launched. In the human-moderation era that limited Snap to a few publishers and slowed growth. AI moderation now covers everything. Content promoting anorexia should be removed under Snap's guidelines, not just down-ranked. US regulation focuses on algorithms because moderating content runs into First Amendment limits.
	- **Kids and screens**: Spiegel opposes blanket rules and worries about big swings in public mood (screens were saviors during COVID and are villains now). His 15-year-old got a phone early to coordinate between two homes. His biggest worry is that young people won't learn to use AI tools while trust in technology is low.
- ## Leadership and how Snap works
	- **Debate in the design review**: meetings are fun, "everyone's laughing." Any idea can be brought, and shelved ideas come back two or three years later. "Sometimes a great idea is actually we should get rid of this thing."
	- **Not design-led, but a dialogue**: the culture is a "thoughtfully managed dialogue" among design, engineering, product and data science. It copies the original partnership between Spiegel (design) and co-founder Bobby Murphy (engineering).
	- **The hardest problems at once**: Snap competes with the largest companies in messaging, hardware and foundation models (its own video models), so it has to recruit and keep top talent.
- ## What it means for the stock
	- *My reading; the episode doesn't discuss the stock.*
	- **Direct revenue is now material**: more than \$1B run rate from 25M subscribers works out to about \$40 a year each. As AI features add real compute cost, subscription tiers like Lens+ match revenue to cost the way chatbot subscriptions do.
	- **Margins are the near-term AI benefit**: two-thirds AI-written code, half-person app teams and \$100K tools replaced in a day point to lower engineering cost and more product shots per dollar. That fits "on the verge of net income profitability" while spending on Specs.
	- **Specs are a platform bet against Meta and Google**: Snap's arguments are that it owns the whole stack, needs no compute pack, leads on waveguides with US/UK manufacturing, and that AI-made software removes the app-store barrier. Against that, the June memo found the device heavy (132–156g) with about 4 hours of battery. Early-adopter pricing means little revenue at first.
	- **Regulatory risk is real, but Snap is distinguishing itself**: Snap's case is that it is a messaging app, not a social feed, and that independent studies back it, with OS-level controls as its preferred policy. Bans like Australia's hit named apps first. How regulators treat messaging versus feeds matters more to Snap than to Meta.
	- **The distribution premium**: if AI makes building cheap and distribution scarce, Snap's near-1B reach is worth more both to advertisers and to its own new apps.
