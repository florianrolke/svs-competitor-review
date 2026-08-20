# SVS competitor review — Replit agent workspace

Private repo for running cross-model competitor comparisons (Kimi K3 / Sol 5.6 on Replit) against
the Sacred Valley Seminars pattern pages. The pages drive organic traffic; the question this repo
answers, per page, is: **what do the pages currently outranking us do that we don't?**

## Layout

| Path | What |
|---|---|
| `pages/<slug>.md` | The live page markdown, frontmatter included (`primaryQuestion` is the query to judge) |
| `preview/<slug>.html` | The rendered page as a reader sees it — judge the above-the-fold from here |
| `INSTRUCTIONS.md` | The judging procedure and the exact JSON your run must produce |
| `batch-order.md` | Pages ranked by search volume — work top-down, traffic first |
| `verdicts/<slug>.json` | Your output, one file per page |

## How to run (Replit agent)

1. Read `INSTRUCTIONS.md` fully.
2. Take the FIRST slug in `batch-order.md` that has no file in `verdicts/`.
3. Follow the procedure for exactly ONE page, write `verdicts/<slug>.json`, commit it.
4. Repeat as budget allows. One page per commit keeps every result recoverable.

## Rules that protect the results

- Judges never edit anything under `pages/` or `preview/`. Output goes to `verdicts/` only.
- If a fetched competitor page is paywalled, empty, or not an article, pick the next organic
  result instead; note the substitution in the verdict JSON.
- Never recommend: em-dashes, urgency/scarcity, invented credentials, medical claims — the site
  bans them and such recommendations are dead weight.

Results are collected back by Claude, aggregated into themes, and applied selectively with the
site's own gate re-run on every touched page.
