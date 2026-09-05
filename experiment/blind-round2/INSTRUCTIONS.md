# Blind pair, round 2 — does the canonical-layer fix hold up?

Round 1 ran once, on two pages, in August 2026. Both went 6-4 against us, and that result became a
binding writing rule that has since shaped about 200 pages. **Nobody ever tested whether the fix
worked.** This is that test.

Read this whole file before judging anything.

## What you are doing

For each of the six run folders below, you are given two pages that answer the same reader
question, labelled only `page-a.md` and `page-b.md`, plus a fixed list of ten questions a real
person might type. You decide, question by question, **which page an answer engine would cite.**

You are not scoring writing quality, length, warmth, or how much you enjoyed reading. You are
scoring one thing: **if an assistant had to answer this question and cite one of these two pages,
which one would it cite, and why.**

## The six runs

```
secure-attachment/run1   secure-attachment/run2   secure-attachment/run3
emotional-exhaustion/run1  emotional-exhaustion/run2  emotional-exhaustion/run3
```

There are also `page-a.md` / `page-b.md` files sitting directly in `secure-attachment/` and
`emotional-exhaustion/`, above the run folders. **Ignore them.** They are leftovers from staging and
are superseded by the run folders. Judge only the six `run<N>` folders listed above.

**Judge all six as if they were unrelated.** Do not carry an opinion from one run into the next, do
not compare across folders, and do not try to work out whether two folders contain the same pages.
**The sides are deliberately swapped between runs.** If you find yourself reasoning "this is the
same page I saw before", stop and judge the folder in front of you on its own.

## The rules that matter

1. **Use the questions exactly as given** in `QUESTIONS.json`. Do not invent your own, do not
   reword them, do not add or drop any. Round 1's judge generated its own questions, which is why
   round 1 measured question-luck as much as page quality.
2. **Do not fetch anything from the web.** Both pages are supplied in full. This is a closed task.
3. **Every question gets a winner.** No ties. If it is genuinely close, pick one and mark the
   confidence low.
4. **Flag questions neither page should be answering.** Some of these questions ask for medical
   information: a blood panel, a named condition, a medication timeline, whether something "is
   really" a diagnosis. A page written by a non-clinician may deliberately refuse those. **Set
   `"clinical": true` on any question that asks for a diagnosis, a test, a medication, a named
   condition, or advice aimed at a parent about a child.** Still pick a winner, but the flag lets
   us score the pages twice: once on everything, and once only on the questions both pages were
   actually trying to answer.

   This flag is the single most important addition in round 2. Round 1 recorded a 6-4 loss on one
   page where five of the six lost questions were ones the page refuses to answer on principle.

## Output

Write `verdict-round2.json` into each run folder, in exactly this shape. It matches round 1 so the
two can be compared directly.

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
      "why": "one or two sentences, naming the specific thing on the winning page that earns the citation"
    }
  ],
  "key_gaps": {
    "A": ["what A is missing that B has"],
    "B": ["what B is missing that A has"]
  },
  "first_screen": "which page answers the reader faster, and why",
  "provenance": "which page makes it easier to tell where its claims come from",
  "confidence": "high"
}
```

`per_question` must contain exactly ten entries, in the order given.

## What we are actually testing, so you can see why the rules are strict

One of these pairs has had work done on it since round 1: named researchers, named instruments, an
explicit account of where its ideas come from. The other has not, and is the control. We are
looking for whether that work moved the citation score, and by how much, against the same
competitor page and the same questions as before.

**A result showing our page did worse is a real and useful result.** It would mean the added
provenance crowded out something that was already working. Do not soften a verdict to be
encouraging.

## Model and cost

Use the cheapest capable model. Round 1 used Kimi K3 as primary at roughly a seventh of the cost of
the alternative, with a second model validating, and the two agreed. **Budget cap: $5 for all six
runs.** If you approach it, stop and report how many runs completed rather than finishing cheaply
and badly.

## When you are done

Reply with only: the six `citation_score` values, and the count of questions you marked
`"clinical": true` in each run. Nothing else.
