# Blind pair, round 4 — did the placement edits make the page more citable?

Rounds 1 to 3 compared one of our pages against a page from a different tool. This round does
something narrower. Every folder below holds **two versions of the same page, one of them edited**:
headings rewritten into the questions a searcher actually types, named findings moved inside the
section that answers them, and in a few places a new section. Your job is to say whether the edit
bought anything. Read this whole file before judging anything.

## What you are doing

For each of the nine run folders below, you are given two pages that answer the same reader
question, labelled only `page-a.md` and `page-b.md`, plus a fixed list of ten questions a real
person might type. You decide, question by question, **which page an answer engine would cite.**

You are not scoring writing quality, length, warmth, or how much you enjoyed reading. You are
scoring one thing: **if an assistant had to answer this question and cite one of these two pages,
which one would it cite, and why.**

The two pages in a folder share most of their sentences. That is expected, and it is the point:
where they differ is exactly what is being measured. Longer is not automatically better. A page
that buried the answer in a section the question would never reach should lose to one that did not,
whatever else it contains.

## The nine runs

```
waiting-for-permission/run1        waiting-for-permission/run2        waiting-for-permission/run3
how-to-love-yourself/run1          how-to-love-yourself/run2          how-to-love-yourself/run3
the-life-i-will-start-later/run1   the-life-i-will-start-later/run2   the-life-i-will-start-later/run3
```

**Judge all nine as if they were unrelated.** Do not carry an opinion from one run into the next,
and do not try to work out whether two folders contain the same pages. **The sides are deliberately
swapped between runs.** Judge the folder in front of you on its own.

## The rules that matter

1. **Use the questions exactly as given** in `QUESTIONS.json`. Do not invent, reword, add, or drop.
2. **Do not fetch anything from the web.** Both pages are supplied in full. This is a closed task.
3. **Every question gets a winner.** No ties. If it is genuinely close, pick one and mark the
   confidence low.
4. **Set `"clinical": true`** on any question that asks for a diagnosis, a test, a medication, a
   named condition, or advice aimed at a parent about a child. Still pick a winner.
5. **Name the specific thing on the winning page that earns the citation** in `why`: a heading, a
   named finding, a list, a table. Vague praise is not a reason.

## Output

Write `verdict-round4.json` into each run folder, in exactly this shape:

```json
{
  "query": "the line from QUERY.txt",
  "winner_overall": "A",
  "citation_score": {"A": 0, "B": 0},
  "per_question": [
    {
      "q": "the question, verbatim from QUESTIONS.json",
      "cite": "A",
      "clinical": false,
      "confidence": "high",
      "why": "one or two sentences naming the specific thing on the winning page that earns the citation"
    }
  ],
  "key_gaps": {"A": ["what A is missing that B has"], "B": ["what B is missing that A has"]},
  "first_screen": "which page answers the reader faster, and why",
  "provenance": "which page makes it easier to tell where its claims come from",
  "confidence": "high"
}
```

`per_question` must contain exactly ten entries, in the order given.

## Model and cost

Same judge and effort as round 3: Kimi K3, medium effort. **Budget cap: $3 for all nine runs.**
If you approach it, stop and report how many runs completed.

## When you are done

Reply with only: the nine `citation_score` values, and the count of questions you marked
`"clinical": true` in each run. Nothing else.
