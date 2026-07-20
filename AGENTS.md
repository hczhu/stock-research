# AGENTS.md

Guidance for AI coding assistants (Claude Code, Codex, etc.) working in this repository.

## Repository Overview

Plain-text research memo repository for personal stock investing. No build system, tests, or application code.

## Directory Structure

| Directory | Purpose |
|-----------|---------|
| `memos/` | Research notes — earnings summaries, podcast/report extractions, investment analysis |
| `data/` | CSV files with structured quantitative data (e.g. cost shares, pricing tables by quarter) |
| `earnings/` | Earnings call notes grouped by ticker, one file per company-quarter (e.g. `earnings/MediaTek/MediaTek-2026-Q1.md`) |
| `theses/` | Long-form investment theses and thesis templates |
| `principles/` | The owner's own investing philosophy, frameworks, and durable wisdom — first-party, not third-party research. Use as reference/context when answering investment questions; do not treat as source material to re-extract into memos. |

## Before Creating a New Memo

**Always check for an existing memo from the same source before writing a new one.**

```bash
# Search by source name, company, or key phrases from the content
grep -ril "<source name or key phrase>" memos/
```

- If a memo already exists that was extracted from the same original content (same PDF, same podcast episode, same earnings call), **do not create a duplicate**. Update or extend the existing file instead.
- Check both the `tags::` line and the `**Source**:` field of candidate files to confirm they share the same origin.
- A memo covering a different angle or topic *from the same source* should be a new section in the existing file, not a separate file, unless the topics are genuinely non-overlapping and the file would become unwieldy.

## File Naming Convention

```
memos/YYYY-MM-DD-kebab-case-description.md
```

Use the date the memo is created or the date of the source material, whichever is more meaningful. Multi-word titles with spaces are acceptable for older files but kebab-case is preferred for new ones.

Earnings notes live under ticker-specific subdirectories:

```
earnings/<Ticker>/<Ticker>-YYYY-QN.md
```

Example: `earnings/SNOW/SNOW-2026-Q1.md`.

## Memo Format

All memos use Logseq outliner Markdown — every line starts with `- ` and nesting uses tabs:

```markdown
- tags:: [[Ticker]], [[Topic]], [[sector]]

- ## Section Title
	- Content line
		- Nested content
	- **Bold label**: value
```

**Required elements for new memos:**
- `tags::` line at the top using `[[WikiLink]]` syntax — include ticker symbols, sector (e.g. `[[semiconductor]]`, `[[AI]]`), and topic tags
- A `## Section Title` as the first section
- `**Source**:` attribution where the content comes from a third party

**Optional but common elements:**
- `**Thesis**:` — one-line investment takeaway
- Data tables using standard Markdown table syntax
- `## Key Data Points` or `## Stock Read-Throughs` sections
- `## X Post` section at top when memo is intended for publishing (use `——` as section dividers, single post format for X Premium)

**Disallowed sections:**
- Do **not** write a `## Working conclusion` section in memos. Put any final synthesis under a more specific section title such as `## Key Takeaways` or `## Stock Read-Throughs`.
- Do **not** write a `## Risks and Caveats` section in memos.
- Do **not** write an `## Investment Implications` section.
- Do **not** write a `## Catalysts` section.
- Do **not** write a `## Risks and Counterarguments` section.
- Do **not** write a `## What to Monitor` section.
- Do **not** write a `## Variant Perception` section.

## Input Handling

- **No images**: Never use images in memos. When the input prompt contains images (screenshots, charts, tables), OCR them to extract text and data points, then work from the extracted content.
- **High data-point density**: When a text block contains many data points (metrics, figures, comparisons), structure it as a Markdown table rather than prose or bullet lists.

## Do Not Disclose Positions

Never include the owner's position, holdings, trade sizes, entry prices, or entry dates in thesis files, memos, or any other notes. This means:

- Do not add a `**Position**:` field to thesis headers or templates.
- Do not mention whether the owner is long, short, watching, or holding a name.
- Do not record dollar amounts invested, number of shares, or purchase dates.
- Analytical context (e.g., "Big 3 P/E <10 at the time of writing") is fine; personal position metadata is not.

## GitHub + Logseq Dual Rendering

Memos must render correctly **both** in Logseq (outliner) and on GitHub (CommonMark/GFM). GitHub treats tab-indented lines that are not nested under a list item as **indented code blocks** (monospace boxes) — the most common way an outline file breaks on GitHub.

1. **Headings must be bullets**: write `- ## Section Title`, never a bare `## Section Title` followed by tab-indented children — the children render as a code block on GitHub.
2. **Only tab-indent under a parent bullet** — one tab per nesting level; no free-standing tab-indented text.
3. **Tables hang off a bullet**: start the table on the bullet line (`- | Col | Col |`) and indent subsequent rows with the same tabs plus two spaces so the `|` characters align vertically. A table on bare tab-indented lines (no bullet) becomes a code block on GitHub.
4. Escape currency dollar signs per the rule below.
5. After merging, spot-check the rendered memo on GitHub when it contains new tables or deep nesting.

## Dollar Signs in Markdown

Markdown renderers with LaTeX/MathJax support (GitHub, Logseq math plugin) treat `$...$` as inline math. Two currency dollar signs on the same line — e.g. `$37 ... high-$40s` — silently render as a math block, stripping spaces and garbling the text.

**Rule**: escape currency dollar signs as `\$` whenever two or more `$[digit]` patterns appear on the same line. Examples:

- `~\$37 two weeks before the talk, now high-\$40s`
- `\$220B (2025) → \$890B (2026E)`
- `≈\$47–49B vs ≈\$53B`

Ticker symbols (`$MGM`, `$MU`) and WikiLink tags (`[[$MU]]`) do not need escaping — they are standalone and do not form pairs.

## Tag Conventions

Use canonical tag forms — no duplicates or near-duplicates:

| Use | Not |
|-----|-----|
| `[[DRAM]]` | `[[memory]]` |
| `[[$NVDA]]` (ticker form) | `[[NVIDIA]]`, `[[Nvidia]]` |
| `[[data-center]]` | `[[data center]]`, `[[data centers]]`, `[[data-centers]]` |
| `[[GPU]]` | `[[GPUs]]` |
| `[[inference]]` | `[[AI inference]]`, `[[AI Inference]]` |
| `[[hyperscalers]]` | `[[hyperscaler]]` |
| `[[semiconductor]]` | `[[Semiconductors]]` |
| `[[agents]]` | `[[AI-agents]]` |
| `[[capex]]` | `[[capital-expenditures]]` |
| `[[Michael-Burry]]` | `[[Michael Burry]]` |

Before adding a tag, grep existing memos to confirm the canonical form already in use.

## Workflow Rules

- Never push directly to `main`. Always branch → PR → merge. After merging, `git checkout main && git pull`.
- Non-code changes (new memos, edits) can be committed and PR'd without prior confirmation.
- When searching for context before answering investment questions, `grep` across `memos/`, `earnings/`, and `theses/` by ticker symbol, company name, or topic keyword.
- Structured data in `data/` is CSV; read it directly to answer quantitative questions rather than guessing from memo text.
- When data-point density is relatively high in a paragraph, use a Markdown table instead of dense prose.
- Avoid narrow table columns — every column should render at least as wide as a typical word so headers and values do not wrap mid-word. When a column's values are very short (a bare number, percentage, or ticker), widen them into a short phrase or fold the data into an adjacent column.
- In `earnings/` files, do **not** repeat superficial financial recaps. Avoid headline financial numbers, guidance numbers, and other easily recoverable quarterly boilerplate unless a specific number is itself the insight. Emphasize what changed strategically: customer wins, product direction, go-to-market changes, margin-structure explanations, management tone, competitive read-throughs, and unusual operating signals.

## Content Themes

Memos span: AI infrastructure (GPU, HBM, DRAM, packaging), hyperscaler capex and strategy, SaaS metrics and competitive dynamics, China tech, semiconductor supply chain, and macro. Most memos are based on earnings calls, sell-side research, industry podcasts, or primary source data extracted from screenshots.
