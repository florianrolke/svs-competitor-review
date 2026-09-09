# Blind pair, round 6 — does the page read as more the reader's own?

Round 4 asked whether a set of placement edits made a page more citable. This round asks something
different and narrower. Every folder below holds **two versions of the same page, one of them
edited in two small places**. Your job is to say which version reads better on ten specific
counts. Read this whole file before judging anything.

## What you are doing

For each of the nine run folders below you are given two versions of one page, labelled only
`page-a.md` and `page-b.md`, plus a fixed list of ten questions in `QUESTIONS.json`. Every question
asks the same kind of thing: **which of these two pages does this better.** You answer all ten for
every folder.

The ten questions are not about writing quality in general, and not about length. Five of them are
about **ownership**: whether the page leaves the reader in charge of changing the thing it
describes, or hands the job to somebody else. Three are about **recognition**: whether the opening
reads like the reader's own experience in their own words. Two are about **clarity**: whether the
argument runs cleanly from the question at the top to the answer.

The two versions in a folder share almost every sentence. That is expected, and it is the point:
where they differ is exactly what is being measured. Longer is not automatically better, and
neither is shorter. Judge what the difference does to the reader.

## The nine runs

```
anxious-attachment-style/run1   anxious-attachment-style/run2   anxious-attachment-style/run3
cynicism/run1                   cynicism/run2                   cynicism/run3
emotionally-unavailable/run1    emotionally-unavailable/run2    emotionally-unavailable/run3
```

**Judge all nine as if they were unrelated.** Do not carry an opinion from one run into the next,
and do not try to work out whether two folders contain the same pages. **The sides are deliberately
swapped between runs.** Judge the folder in front of you on its own, and do not try to work out
which version was the edited one.

## The rules that matter

1. **Use the questions exactly as given** in `QUESTIONS.json`. Do not invent, reword, add, or drop.
2. **Do not fetch anything from the web.** Both pages are supplied in full. This is a closed task.
3. **Every question gets a winner.** No ties. If it is genuinely close, pick one and mark the
   confidence low.
4. **Set `"clinical": true`** on any question you answered mainly on the strength of clinical or
   safety material rather than on the writing. Still pick a winner.
5. **Name the specific thing on the winning page that decides it** in `why`: a sentence, a
   paragraph, a placement, a heading. Vague praise is not a reason.

## Output

Write `verdict-round6.json` into each run folder, in exactly this shape:

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
      "why": "one or two sentences naming the specific thing on the winning page that decides it"
    }
  ],
  "key_gaps": {"A": ["what A does worse than B"], "B": ["what B does worse than A"]},
  "first_screen": "which page's first screen leaves the reader more in charge, and why",
  "provenance": "which page makes it easier to tell where its claims come from",
  "confidence": "high"
}
```

`per_question` must contain exactly ten entries, in the order given. The field names are carried
over from round 4 unchanged so the existing scorer reads these verdicts without modification;
`cite` here means the page you picked for that question.

## Model and cost

Same judges and effort as round 5. **Budget cap: $3 for all nine runs.** If you approach it, stop
and report how many runs completed.

## When you are done

Reply with only: the nine `citation_score` values, and the count of questions you marked
`"clinical": true` in each run. Nothing else.
