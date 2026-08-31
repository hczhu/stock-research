tags:: [[$V]], [[$MA]], [[$AXP]], [[$COF]], [[$JPM]], [[payments]], [[fintech]], [[interchange]], [[regulation]], [[consumer]], [[NBER]]

- ## NBER: interchange fees move ~\$30B a year from cash and debit users to credit users
	- **Source**: NBER Digest summary of Working Paper 35067, **"Who Pays for Payments?"** — Mark Egan, Gregor Matvos, Amit Seru, Lulu Wang, Vincent Yao, July 1, 2026.
	- **Why this belongs in a research file**: it is not a consumer-economics curiosity. **A rigorous, well-identified academic quantification of a large regressive transfer is the raw material regulation is built from** — the Durbin Amendment came out of exactly this genre of analysis. The paper hands legislators a defensible \$30bn number and a \$9.2bn income-transfer figure, and it does so with unusually strong data.
	- **Thesis**: The headline transfer matters less than **the Durbin finding**, which is that capping interchange on one rail while leaving another uncapped **redirected the subsidy rather than removing it** — and made the distributional outcome worse, not better. That is the single most useful input for handicapping the next round of interchange regulation.
- ## The measured transfer
	- Interchange runs **~1.9% of transaction value**, most of it funding cardholder rewards. Because merchants generally price uniformly regardless of payment method, non-card users fund card rewards.
	- **Purchasing-power effect by payment type**:
	  | Payment type | Effect |
	  |---------------------|-------------------|
	  | **Cash** | **−96 bps** |
	  | **Regulated debit** | **−47 bps** |
	  | **Basic credit** | **+48 bps** |
	  | **Premium credit** | **+59 bps** |
	- **On the rewards-received-minus-fees-paid measure** shown in the paper's figure: cash **~−11%**, regulated debit **~−9%**, exempt debit slightly below zero, basic credit **~+7%**, premium credit **~+13%** — a **~24 point spread** between the best and worst positioned users. (Regulated debit = issued by banks with **>\$10bn in assets**; exempt debit = smaller banks, which explains why exempt debit sits near neutral.)
	- **Aggregate**: **~\$30 billion annually** from cash and debit users to credit users, of which **~\$9.2 billion (about 31%)** flows from households earning **under \$150,000** to those earning more, because credit card use rises with income.
- ## The data is the reason to take it seriously
	- **Fiserv merchant-level data, 2006–2022**, at establishment level — payment values, transaction counts, and interchange fees **by card type**, organized by merchant-sector-location.
	- The 2022 cross-section covers **~1 million merchants, roughly one-fifth of all US card payments.**
	- A second dataset of **~800,000 merchants (2019–2022)** uniquely captures **cash** alongside cards — which is what makes the cash-user estimate possible at all, since cash is normally invisible in payment data.
	- Supplemented by the Atlanta Fed's Survey and Diary of Consumer Payment Choice and MRI-Simmons to map payment behaviour to household income.
	- **This is materially better evidence than prior work on the question**, and that matters for how much weight regulators will put on it.
- ## Why the transfer is not larger — and where it concentrates
	- **Two forces cut it by ~25%** relative to a homogeneous world, implying a naive estimate of **~\$40bn** and **~\$10bn absorbed by structure**:
		- **Cash, debit, and credit users shop at different merchants**, so the overlap required for cross-subsidy is limited.
		- **Where they do overlap — large grocery and gas — interchange is already lower** through sector discounts and negotiated rates.
	- **The commercially useful inversion of that finding**: the cross-subsidy is **concentrated in sectors with high credit mix and no negotiating leverage** — restaurants, small retail, services. **Small merchants pay the highest effective rates and capture none of the offsetting rewards**, which is a structural read-through for small-merchant acquirers whose customers bear that cost.
- ## The Durbin lesson — the most important finding here
	- The Durbin Amendment capped interchange on debit issued by large banks. **The paper's finding is that its practical effect was to transfer value to credit card users**, via lower retail prices, **at the expense of regulated debit users**, who lost roughly **\$9.6 billion** in rewards and free checking benefits. **Net: middle-income to higher-income households** — the opposite of the intended direction.
	- **The generalizable mechanism**: **capping one rail while leaving another uncapped shifts the subsidy rather than eliminating it.** Issuers recover the lost economics by cutting rewards and free services on the capped product, and the benefit accrues to whoever remains on the uncapped rail.
	- **How to apply it to the next round of regulation**: a credit-interchange cap or routing mandate should be expected to produce **reduced credit rewards and reintroduced fees**, with the incidence falling on whichever users are least able to switch — and with merchant pass-through to prices being the open question rather than the assumption.
	- **This is also a caution about reading the paper as an argument for reform.** It documents a regressive transfer *and* documents that the last attempt to fix one made it worse. Those are the same finding.
- ## The premium mix shift is the operating trend
	- **Premium cards went from 15% of credit card volume in 2006 to 60% by 2022 — a 4× share gain.**
	- **Premium cardholders gained ~\$7.9 billion**, and — the counterintuitive detail — **debit users, not cash users, bore the largest dollar losses**, because they shop most frequently alongside premium card users.
	- **Why this is the number to watch**: premium is where issuer economics concentrate, and it is now the majority of volume. **Any regulation aimed at the regressive transfer necessarily targets the highest-margin part of the card business**, and the paper supplies the evidence that premium specifically is what drives the effect.
- ## Who is actually exposed — a distinction that is usually conflated
	- **Interchange goes to the issuing bank, not the network.** Visa and Mastercard earn service and assessment fees on volume; they set interchange schedules but do not receive them. **So a cap hits issuers directly and networks only indirectly**, through volume, mix, and any behavioural response.
	- **Most exposed**: issuers with heavy premium-card and rewards-funded models — the economics that the 15%→60% shift built. **Amex is structurally different** as a closed-loop network capturing the full merchant discount, which cuts both ways: more fee exposure, but also more control over the offsetting value proposition.
	- **Beneficiaries of a cap** would be **large merchants** with the scale to keep any savings, and the analysis suggests small merchants would benefit least since they already pay the highest rates and would gain least from routing flexibility.
	- **The prior on outcomes should be shaped by Durbin**: after the debit cap, the merchant-side savings were real but consumer pass-through was contested, while the issuer-side response — losing free checking and debit rewards — was immediate and measurable. **The party that loses is easier to predict than the party that gains.**
- ## The paper's main vulnerability
	- **The pass-through assumption is doing a lot of work.** The figure's own note states the calculations **assume merchants pass interchange fees forward to all purchases** — that is a modelling choice, not a measured result. **If pass-through is partial, merchants bear more of the cost, the consumer-to-consumer transfer is smaller than \$30bn, and the case for reform shifts from a distributional argument to a merchant-margin argument.** The headline scales more or less linearly with this assumption.
	- Related: uniform pricing is the second load-bearing assumption. Surcharging and cash discounts exist and are growing in some sectors; where they do, the cross-subsidy mechanically weakens.
	- **What would strengthen the finding**: evidence on realized pass-through rates by sector, and a test of whether merchants that do surcharge show the predicted narrowing of the transfer. Neither appears in the summary.
