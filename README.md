# stock-research

Personal investment research repository. Raw notes, data extractions, earnings summaries, and theses on individual companies, sectors, and macro themes — primarily AI infrastructure, semiconductors, SaaS, and China tech.

---

## Repository Structure

```
stock-research/
├── memos/          # Dated research notes (130+ files)
├── earnings/       # Earnings call notes grouped by ticker
├── theses/         # Long-form investment theses and templates
├── data/           # Structured quantitative data (CSV)
├── principles/     # The owner's own investing philosophy and frameworks
├── AGENTS.md       # Guidance for AI coding agents (Codex, Claude Code)
└── CLAUDE.md       # Guidance for Claude Code specifically
```

### `memos/`

The main research corpus. Each file is a dated, tagged note extracted from a primary source — earnings calls, research reports, podcasts, screenshots, or primary data.

**Naming convention:** `YYYY-MM-DD-kebab-case-description.md`

**Format:**
```markdown
- tags:: [[$NVDA]], [[HBM]], [[semiconductor]]

- ## Section Title
    - **Source**: SemiAnalysis, May 2026
    - **Thesis**: one-line investment takeaway
    - Key data in markdown tables
```

Every memo opens with a `tags::` line using `[[WikiLink]]` syntax, which Logseq renders as clickable tag links. Dense data is rendered as markdown tables.

### `earnings/`

Earnings call notes, grouped by ticker with one file per company-quarter.

**Naming convention:** `earnings/<Ticker>/<Ticker>-YYYY-QN.md`

Example: `earnings/MediaTek/MediaTek-2026-Q1.md`

### `theses/`

Long-form investment theses and the thesis template. Start here when building a position write-up.

- `investment-thesis-template.md` — structured template for a full thesis

### `data/`

CSV files with structured quantitative data extracted from screenshots, reports, or proprietary estimates.

Example: `ai-chip-component-cost-shares-by-quarter.csv` — quarterly HBM/memory/logic/packaging cost shares across major AI chip vendors (NVIDIA, AMD, Google, Amazon), used in the corresponding memo.

### `principles/`

The owner's **own** investing philosophy, decision frameworks, and durable wisdom — first-party, unlike the third-party extractions in `memos/`. Use these to understand the lens the rest of the repo is written through.

- `my-investment-philosophy.md` — the owner's core strategy (high-quality compounders, position sizing, staying invested) plus Munger-derived risk principles
- `investing-wisdom.md` — philosophy, principles, risk, and independence notes
- `company-culture-trade-offs.md` — framework of organizational culture trade-offs (independence vs. collaboration, speed vs. thoroughness, etc.)

---

## Coverage Themes

| Theme | Examples |
|---|---|
| AI infrastructure | HBM demand/supply, data center buildout, hyperscaler capex |
| Semiconductors | TSMC, NVIDIA roadmap, DRAM/NAND pricing, advanced packaging |
| Memory | Super-cycle thesis, chipflation, LTAs, two-tier market |
| AI labs | Anthropic, OpenAI revenue/cost structure, model efficiency |
| SaaS | Enterprise AI adoption, platform metrics, competitive dynamics |
| China tech | Token economics, CXMT, YMTC, A-share market |
| Macro | Labor markets, capex cycle, policy |

---

## Reading in Logseq

[Logseq](https://logseq.com/) renders this repo's markdown natively — WikiLinks become clickable, tags are filterable, and the outliner format displays correctly.

### Setup (5 minutes)

1. **Download Logseq** from [logseq.com](https://logseq.com/) if you haven't already.

2. **Add this repo as a graph:**
   - Open Logseq
   - Click **"Add new graph"** (or the graph switcher in the top-left)
   - Select **"Open a local folder"**
   - Navigate to and select the `stock-research` directory
   - Logseq will index all `.md` files and create a `logseq/` config subfolder

3. **Navigate to memos:**
   - Left sidebar → **Files** tab → open the `memos/` folder
   - Or use **Cmd+K** (Mac) / **Ctrl+K** (Windows) to search by filename or content

4. **Browse by tag:**
   - Click any `[[WikiLink]]` in a memo to see all pages linking to that tag
   - Or use the **Graph view** (left sidebar) to explore tag connections visually

5. **Search across the corpus:**
   - **Cmd+Shift+F** opens full-text search across all memos
   - Search by ticker (e.g. `NVDA`), topic (e.g. `HBM`), or source (e.g. `SemiAnalysis`)

### Tips

- The `tags::` line at the top of each memo functions as Logseq page properties — clicking a tag like `[[HBM]]` shows every memo tagged with it
- Tables render natively in Logseq's preview mode; toggle between edit and preview with **Escape**
- Logseq's **Linked References** panel (bottom of any page) shows all memos that reference a given ticker or topic — useful for building a full picture on a name

---

## AI Agent Usage

See [AGENTS.md](AGENTS.md) for guidance on using AI coding agents (Claude Code, Codex) to create, search, and update memos in this repo.
