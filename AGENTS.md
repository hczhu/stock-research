# AGENTS.md

Guidance for AI agents (Codex, Claude Code, etc.) working in this repository.

## Repository Overview

Plain-text research memo repository for personal stock investing. No build system, tests, or application code.

## Directory Structure

| Directory | Purpose |
|-----------|---------|
| `memos/` | Research notes — earnings summaries, podcast/report extractions, investment analysis |
| `data/` | CSV files with structured quantitative data (e.g. cost shares, pricing tables by quarter) |
| `earnings/` | Earnings call notes grouped by ticker, one file per company-quarter (e.g. `earnings/MediaTek/MediaTek-2026-Q1.md`) |
| `theses/` | Long-form investment theses and thesis templates |

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

Use the date the memo is created or the date of the source material, whichever is more meaningful.

Earnings notes live under ticker-specific subdirectories:

```markdown
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

**Required elements:**
- `tags::` line at the top using `[[WikiLink]]` syntax
- `**Source**:` attribution
- At least one `## Section Title`

## Do Not Disclose Positions

Never include the owner's position, holdings, trade sizes, entry prices, or entry dates in thesis files, memos, or any other notes. This means:

- Do not add a `**Position**:` field to thesis headers or templates.
- Do not mention whether the owner is long, short, watching, or holding a name.
- Do not record dollar amounts invested, number of shares, or purchase dates.
- Analytical context (e.g., "Big 3 P/E <10 at the time of writing") is fine; personal position metadata is not.

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

- Never push directly to `main`. Always branch → PR → merge.
- Non-code changes (new memos, edits) can be committed and PR'd without prior confirmation.
- When searching for context before answering investment questions, `grep` across `memos/` by ticker, company name, or topic keyword.
- When data-point density is relatively high in a paragraph, use a Markdown table instead of dense prose.
- Avoid narrow table columns — every column should render at least as wide as a typical word so headers and values do not wrap mid-word (e.g. `Weight` breaking into `Wei`/`ght`, or `19%` into `19`/`%`). When a column's values are very short (a bare number, percentage, or ticker), widen them into a short phrase (e.g. `19% of index` instead of `19%`) or fold the data into an adjacent column rather than leaving a sub-word-width column.
- Exception: do not use tables in `Anecdotes & Opinions` sections. Use one short paragraph per anecdote/opinion, and use quoted text blocks for literal words from sources.
- In `earnings/` files, do **not** repeat superficial financial recaps. Avoid headline financial numbers, guidance numbers, and other easily recoverable quarterly boilerplate unless a specific number is itself the insight.
- Earnings notes should emphasize what changed strategically: customer wins, product direction, go-to-market changes, margin-structure explanations, management tone, competitive read-throughs, and unusual operating signals.
