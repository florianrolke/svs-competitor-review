# Judging procedure — one page per run

You are judging landing pages competing for one search query. Be adversarial and specific. No
politeness, no praise sandwiches. Judge ONLY what is on the pages.

## Steps

1. Pick the first slug in `batch-order.md` with no `verdicts/<slug>.json` yet.
2. Read `pages/<slug>.md`. The query you are judging is its frontmatter `primaryQuestion`.
   Open `preview/<slug>.html` too — that is what a reader actually sees, including the
   above-the-fold block.
3. Search the web for that query. Take the top 2 organic results that are actual articles —
   skip Reddit, YouTube, forums, dictionaries, and pure product pages. Fetch and read both.
4. Produce the JSON below. Write it to `verdicts/<slug>.json` and commit with message
   `verdict: <slug>`.

## Output — exactly this object, nothing else

```json
{
  "slug": "...",
  "query": "...",
  "competitors": ["url1", "url2"],
  "verdict": "ours_wins | competitor_wins | split",
  "confidence": "high | medium | low",
  "why_in_two_sentences": "...",
  "what_the_winner_does_that_we_dont": ["specific, actionable items only"],
  "what_we_do_that_they_dont": ["..."],
  "above_the_fold": {
    "ours": "what a reader sees before scrolling and whether it earns the next scroll",
    "theirs": "same for the better competitor",
    "gap": "the single change to our fold with the most impact, or 'none'"
  },
  "questions_they_answer_that_we_dont": ["verbatim question phrasings worth adding as FAQs"],
  "intent_mismatch": "any way our page answers a different question than the query asks, or 'none'",
  "trust_signals": "provenance/authority/specificity comparison in one sentence",
  "one_change_with_most_traffic_impact": "..."
}
```

## Rules

- Every item in `what_the_winner_does_that_we_dont` must be concrete enough to act on without
  re-reading the competitor.
- Do not recommend rewriting body prose style. Composition, coverage, and fold gaps only.
- Never recommend em-dashes, urgency, scarcity, invented credentials, or medical claims.
- If both fetched competitors are unusable, take the next organic results and say so in
  `why_in_two_sentences`.
- Output must parse as JSON. No markdown fences inside the file, no trailing commentary.
