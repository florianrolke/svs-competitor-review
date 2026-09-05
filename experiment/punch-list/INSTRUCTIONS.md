# Cross-family punch list — where does each page fail to earn a citation?

Read this whole file before touching a page.

## What you are doing

You are a citation judge, not an editor. For each of our pages, in the order given in
`PAGES.txt`, you will invent the ten questions a real person would type into an assistant about
that page's topic, sort them into the ones our page is allowed to answer and the ones it is not,
and for every allowed question report **whether the page answers it, under what heading, and
whether a named finding sits inside that section.**

The output is a list of additions. You never propose removing, shortening, or rewriting anything.

## Where the pages are

`pages/<slug>.md` in this repository. `PAGES.txt` in this folder gives the order: highest search
demand first, then alphabetical. Work top-down and stop when the budget says stop. Skip any slug
in `pages/` that is not listed in `PAGES.txt`.

## Step 1 — the ten questions

Read the page in full. Then write the ten questions a person who typed this page's title into an
assistant would plausibly also ask, **in their own words**. Mix them the way real people do: some
are "why do I..." questions about themselves, some are "what do I do about it" questions, some are
about how it shows up with a partner, a boss, a parent, and some are the encyclopedic questions
an assistant gets asked constantly (what it is, where the idea comes from, how it is measured).
Do not pad with trivia and do not tilt the list toward what the page happens to cover.

## Step 2 — COMPETING or POLICY

Our pages follow standing rules. They will never:

- name a diagnosis, disorder, condition, diagnostic manual, or medication, even to rule one out;
- name a medical test or panel, or say what to ask a doctor for;
- give advice aimed at a parent about a child;
- treat a couple or a marriage as the patient (a relationship can be the setting a personal
  pattern shows up in; it is never the thing being treated);
- use the word trauma, or frame anything as trauma treatment;
- name any course, teacher, guru, or seminar other than its own.

If a question can only be answered well by doing one of those, mark it `"kind": "POLICY"` and
say which rule in `policy_reason`. Everything else is `"kind": "COMPETING"`.

## Step 3 — for every COMPETING question, three facts

- `answered`: `"yes"`, `"partial"`, or `"no"`. Does the page actually answer it, anywhere?
- `where`: the exact H2 under which the answer sits, copied verbatim, or `""`.
- `heading_is_question`: `true` only if that H2 is, in substance, the question the searcher asked
  (same question, any wording). A heading that is a clever title, a metaphor, or a different
  question is `false` even when the answer is underneath it.
- `named_finding_inside`: the named researcher, instrument, study, or checklist inside that
  section that an assistant could quote as the source of the answer, or `""` if there is none.
  Being named elsewhere on the page, in a sources section for example, does not count.
- `what_to_add`: one sentence. The specific H2 phrased as the question, and the specific named
  finding that would earn the citation. **If you do not know a canonical finding by name with
  confidence, write "no named finding known" rather than inventing one.** An invented citation is
  the worst possible output of this job. Leave `what_to_add` as `""` when `answered` is `"yes"`,
  `heading_is_question` is `true`, and `named_finding_inside` is non-empty.

## Output

One file per page: `experiment/punch-list/<slug>.json`, exactly this shape:

```json
{
  "slug": "the-slug",
  "questions": [
    {
      "q": "the question in the searcher's words",
      "kind": "COMPETING",
      "policy_reason": "",
      "answered": "partial",
      "where": "## The exact H2, verbatim",
      "heading_is_question": false,
      "named_finding_inside": "",
      "what_to_add": "An H2 'What does a secure person do after a fight?' carrying Gottman's repair-attempt finding."
    }
  ]
}
```

Ten entries per page, every field present on every entry (POLICY entries carry `answered`,
`where`, `heading_is_question`, `named_finding_inside` and `what_to_add` as `""`/`false`).

## Rules

1. **Do not fetch anything from the web.** The pages are supplied in full. Closed task.
2. **Judge each page on its own.** Do not compare pages to each other.
3. **Commit after every five pages** (`git add experiment/punch-list && git commit`), so a budget
   stop loses nothing. Push at the end, or at any commit if you prefer.
4. **Budget cap: $12 total.** Use Kimi K3 at medium effort. When you approach the cap, finish the
   page you are on, commit, push, and stop. Partial coverage in the right order is the intended
   outcome; do not go cheap and shallow to reach the end of the list.
5. Never edit a page. Never write into `pages/`.

## When you are done

Reply with only: the number of pages judged, the last slug judged, and the commit hash. Nothing else.
