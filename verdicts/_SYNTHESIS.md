# Synthesis: full corpus (65 verdicts)

Aggregates the 65 primary verdict files in `verdicts/` (one per page in `batch-order.md`;
`.sol.json` cross-model duplicates excluded). Every claim below names the verdict files it
rests on. Note on coverage: `serp_quality` was only introduced for the final batch of 15
verdicts, so the weak-SERP list in section 4 covers those 15 pages, not the full corpus.

## 1. Scoreboard

| Verdict | Count | Confidence |
|---|---|---|
| ours_wins | 58 | 44 high, 14 medium |
| split | 7 | 7 medium |
| competitor_wins | 0 | - |

The splits: how-to-set-boundaries (8,100/mo), why-am-i-so-miserable (2,900/mo), toxic-shame
(1,500/mo), emotional-exhaustion, limiting-beliefs, what-is-people-pleasing,
why-cant-i-name-my-feelings. No page was an outright loss. The pattern is consistent: our
pages win on depth, mechanism, differentials, and answering both halves of the query;
competitors win only on visible authority and a handful of concrete format elements.

## 2. Top 5 recurring gaps (verdicts flagging x combined monthly volume)

**1. Visible authority and provenance - 33 verdicts, 32,800 combined vol/mo.** The single
dominant gap. Competitors attach named, credentialed humans and dated, checkable sources to
the same claims we assert unattributed: medical-review bylines (self-loathing,
why-cant-i-name-my-feelings, why-am-i-so-miserable), quoted clinicians with titles
(trust-issues, emotionally-unavailable, where-insecurities-come-from, why-dont-i-trust-myself),
peer-reviewed reference lists with DOIs (where-insecurities-come-from, self-sabotage,
why-cant-i-trust-anyone), sourced prevalence statistics (parentification,
growing-up-with-violence, why-cant-i-name-my-feelings, why-do-i-need-validation), and license
numbers (toxic-shame). Even our highest-traffic pages carry this gap: avoidant-attachment's
verdict calls a short sources block "the only real trust-signal gap" on an 18,000/mo page, and
how-to-break-a-habit's verdict says citing the extinction research we already paraphrase
converts assertion to evidence "at near-zero cost." Action: add a sources block naming the
research each page already paraphrases, plus one prevalence figure where the literature has
one. No invented credentials - cite real, checkable work.

**2. Numbered, linear action paths - 9 verdicts, 11,700 combined vol/mo.** Competitors give
readers a countable sequence to follow (Thriveworks' eight tips for trust-issues, Wondermind's
four steps, Psychology Today's 3 steps on feeling-responsible-for-everyone, Simply
Psychology's five-step boundary script on how-to-set-boundaries). Our pages argue and explain
but rarely enumerate. how-to-forgive-yourself's verdict notes both competitors' numbered steps
are "their main scannability advantage on a how-do-I query." Action: surface one compact
numbered sequence per page (our material already contains the steps; it is a formatting and
composition change, not new content).

**3. Scannable self-check lists - 12 verdicts, 2,900 combined vol/mo.** A compact symptom or
trait list a reader can self-score in seconds: Cleveland Clinic's signs-of-self-loathing list
(self-loathing), Verywell's abandonment checklist (fear-of-abandonment), Psychology Today's
people-pleasing traits (what-is-people-pleasing), the abuse-signs checklist
(walking-on-eggshells). Our identify-boxes do related work but competitors' checklists are
shorter and positioned for skimmers. Action: add one 5-7 item checklist near the top of pages
whose verdict flags this, phrased as observable behaviors.

**4. Word-for-word scripts - 3 verdicts, 8,100 combined vol/mo.** Where a query implies a
conversation, competitors hand the reader exact sentences: the boundary scripts for four
relationship types (how-to-set-boundaries), the non-accusatory workplace line
(why-do-i-avoid-conflict), the "I love it when you X" opener (emotionally-unavailable).
how-to-set-boundaries is our highest-volume split (8,100/mo) precisely because our page argues
against scripts but never replaces them with usable language. Action: add a short block of
verbatim sentences for the three or four most-searched situations per relevant page.

**5. Named clinical terminology and frameworks - 16 verdicts, 0 combined vol/mo (all on
unmeasured long-tail pages).** Competitors hand the searcher the field's own vocabulary to
search next: alexithymia and interoception (why-cant-i-name-my-feelings), IFS with named
protector parts (self-sabotage), instrumental vs emotional parentification (parentification),
fawn response attributed to Pete Walker (what-is-people-pleasing, and our own fawn-response
verdict flags the missing credit), the mistrust/abuse schema (why-cant-i-trust-anyone),
predictive processing (why-cant-i-change), object constancy (fear-of-abandonment), ACE scores
(growing-up-with-violence). Action: name the standard term where one exists and credit its
originator; this is the cheapest authority signal available and doubles as an FAQ magnet.
(Closely related, counted separately: naming specific therapy modalities - CBT, DBT, ACT,
EMDR, schema therapy - appears in 10 verdicts including emotional-suppression, self-loathing,
self-sabotage, limiting-beliefs.)

## 3. The 10 pages most in need of fixes (priority order)

1. **avoidant-attachment** (18,000/mo, ours_wins/high): add a short sources block naming the
   attachment research the page already paraphrases.
2. **secure-attachment** (15,000/mo, ours_wins/medium): add a same-situation,
   three-attachment-responses comparison block early in the body.
3. **how-to-set-boundaries** (8,100/mo, split): add verbatim boundary sentences for partner,
   parent, friend, and work - the element both competitors lead with.
4. **victim-mentality** (5,100/mo, ours_wins/medium): promote "dealing with someone else's
   victim mentality" from one FAQ into a full body section; that audience is a large share of
   the query.
5. **how-to-break-a-habit** (4,700/mo, ours_wins/high): name and cite the extinction/resurgence
   research inside the relapse sections.
6. **how-to-forgive-yourself** (3,600/mo, ours_wins/high): surface a compact numbered sequence
   (name it, make the makable amends, reassign the punishment).
7. **fawn-response** (3,300/mo, ours_wins/high): credit Pete Walker and Complex PTSD: From
   Surviving to Thriving in the definition section; provenance of the term is the cheapest
   authority signal on a definitional query.
8. **how-to-rebuild-trust** (3,300/mo, ours_wins/medium): add guidance on the disclosure
   dilemma (how much detail about the betrayal helps vs harms).
9. **why-am-i-so-miserable** (2,900/mo, split): add a rule-out-the-circumstantial-causes
   checklist (sleep, money, burnout, grief, physical health) near the top.
10. **toxic-shame** (1,500/mo, split): add the side-by-side shame-vs-guilt table at the top -
    the exact format the query's second half asks for.

## 4. Weak or off-intent SERPs (cheapest ranking wins)

`serp_quality` exists only on the final 15 verdicts. Of those, 11 strong, 4 weak, 0 off-intent:

- **unrealistic-parental-expectations** - weak: genuine top results are academic/PubMed pages
  excluded by the judging rules, leaving one interview, one anecdote, and one listicle.
- **where-insecurities-come-from** - weak: page one is dominated by journal and PMC papers
  (Taylor and Francis, MDPI, Frontiers, Cambridge), with only two article-shaped consumer
  pages.
- **why-do-i-absorb-other-peoples-emotions** - weak: the top author result is a thin empath
  coping-tips post; only two genuinely competitive articles exist.
- **why-do-i-need-validation** - weak: top result is a numbered listicle, the rest short
  single-therapist blogs; no authoritative long-form article dominates.

On all four, a definitive long-form page has no strong incumbent to displace. The remaining 50
pages were judged before the field existed; re-running a SERP-quality pass on the
high-volume head of the list would complete this picture.

## 5. Questions competitors answer that we don't (deduplicated, by theme)

**Clinical labels and definitions.** What is alexithymia and how common is it
(why-cant-i-name-my-feelings); what is interoception (why-cant-i-name-my-feelings); what is
the fawn/flop response and is people-pleasing a trauma response (what-is-people-pleasing,
fawn-response); what is the mistrust/abuse schema in a child vs an adult
(why-cant-i-trust-anyone); what is the self-sacrifice schema (feeling-responsible-for-everyone);
what is object constancy (fear-of-abandonment); what is an ACE score (growing-up-with-violence);
what is generalized trust (why-cant-i-trust-anyone); what is unrefreshing sleep
(emotional-exhaustion); what is predictive processing (why-cant-i-change); what is IFS
(self-sabotage); instrumental vs emotional parentification (parentification, enmeshed-family);
dismissive vs fearful avoidant (avoidant-attachment); identity exploration vs commitment
(i-dont-know-who-i-am-anymore); adaptive vs toxic perfectionism
(how-to-stop-being-a-perfectionist); trauma vs PTSD (growing-up-with-violence); self-love vs
self-care (how-to-love-yourself); being valued vs being enough (need-for-significance);
emotional avoidance vs suppression (emotional-suppression); fear of engulfment
(fear-of-intimacy).

**Treatment and professional help.** What therapy treats X - self-loathing, self-sabotage,
fear of abandonment, emotional wounds, enmeshment, limiting beliefs (self-loathing,
self-sabotage, fear-of-abandonment, emotional-wounds, enmeshed-family, limiting-beliefs); when
should I see a professional (self-loathing, emotional-wounds); where do I even start getting
help (secure-attachment); can couples counseling help (emotionally-unavailable); how does a
professional diagnose emotional blunting (emotional-numbness).

**Prevalence and normality.** How common is parentification / alexithymia / impostor syndrome /
achievement pressure (parentification, why-cant-i-name-my-feelings, why-do-i-need-validation,
unrealistic-parental-expectations); is losing your sense of self normal (how-to-find-yourself,
i-dont-know-who-i-am-anymore); do the effects persist into middle age (controlling-parents);
are women more likely to be people-pleasers (what-is-people-pleasing).

**Causes and mechanisms.** Why does a manipulator stay calm while you get upset
(emotional-manipulation); the neuroscience of emotional contagion and mirror neurons
(why-do-i-absorb-other-peoples-emotions); who sends vs catches emotions in a group
(why-do-i-absorb-other-peoples-emotions); how does bullying or rejection in childhood cause
trust issues (why-cant-i-trust-anyone); can physical conditions cause this - sleep disorders,
iron, fibromyalgia, chronic pain (emotional-exhaustion, hypervigilance, feeling-empty-inside);
why does the habit return in old places (how-to-break-a-habit); why does clarity sometimes make
change harder (why-cant-i-change); why does achieving a goal only satisfy briefly
(why-do-i-feel-not-good-enough, why-am-i-so-miserable); can social media be making me unhappy
(why-am-i-so-miserable, why-do-i-feel-not-good-enough); why do we rush to replace authority
with gurus (lack-of-guidance-growing-up); can an institution cause betrayal trauma
(betrayal-trauma); why stay loyal to the person who betrayed you (betrayal-trauma); where does
the defeatist belief about emotions come from (emotional-home).

**Signs and self-identification.** Signs of avoidant attachment in children
(avoidant-attachment); what neglect looks like while it is still happening
(childhood-emotional-neglect); signs of an enmeshed parent (enmeshed-family); symptoms of
unresolved emotional wounds (emotional-wounds); how to identify your own insecurities
(where-insecurities-come-from); is my relentless inner critic toxic shame (toxic-shame); is
walking on eggshells a sign of emotional abuse (walking-on-eggshells); signs it is time to
start over (how-to-start-over).

**What to do and say.** What do I say when my mind goes blank (how-to-set-boundaries); how to
set boundaries with someone in active addiction (how-to-set-boundaries); exact words to raise
an issue without being accusatory (why-do-i-avoid-conflict); how to talk to an unavailable
partner without defensiveness (emotionally-unavailable); how to talk to a partner about their
reactions (walking-on-eggshells); what can I do right now when pain is overwhelming
(emotional-wounds); concrete steps to feel less responsible (feeling-responsible-for-everyone);
how to overcome insecurity day to day (where-insecurities-come-from); what should you not do
when starting over (how-to-start-over); which regulation strategy fits this intensity
(how-to-change-how-you-feel); step-by-step ways to rebuild trust with a specific person
(trust-issues); can I become the calm anchor instead of the absorber
(why-do-i-absorb-other-peoples-emotions); when is it smart not to speak your truth
(how-to-stop-people-pleasing).

**Relationships and the second audience.** Can parents prevent avoidant attachment
(avoidant-attachment); how do I support my child without pushing them into anxiety
(unrealistic-parental-expectations); how do I stop repeating the pattern with my own children
(parentification); should I ask for all the details of the affair (how-to-rebuild-trust); what
would it take to feel safe with this person again (how-to-rebuild-trust); what can a couple do
to make raising differences safe (why-do-i-avoid-conflict); where do I get help if I am afraid
of my partner (walking-on-eggshells); what is intellectual bullying (emotional-manipulation).

**Mind, body, and decision-making.** What parts of the brain are involved in not naming
feelings (why-cant-i-name-my-feelings); what are the health effects of self-distrust /
conflict avoidance (why-dont-i-trust-myself, why-do-i-avoid-conflict); can intuition be wrong /
does gut mean ignoring logic (how-to-trust-yourself); does having too many choices undermine
self-trust (why-dont-i-trust-myself); is distraction ever productive (emotional-home); does
reappraisal actually change the feeling (how-to-change-how-you-feel); why don't I care about
anything anymore (feeling-empty-inside); do people notice me more than I think
(feeling-invisible); can I be loved yet still feel unknown (feeling-unloved); what am I really
looking for under the need for validation (why-do-i-need-validation); is it healthy to forgive
yourself (how-to-forgive-yourself); why do affirmations not touch shame (toxic-shame); can a
personality disorder be behind needing control (need-for-certainty); can you matter too much
(need-for-significance); which life skills were never taught and where to learn them now
(lack-of-guidance-growing-up); are present-day upsets really about childhood
(inner-child-work); what is complicated grief after a difficult parent dies
(unresolved-father-issues); how long does rewiring a belief take (limiting-beliefs); is
all-or-nothing thinking linked to panic disorder (black-and-white-thinking); what is a
caregiver's emotional hunger (anxious-attachment-style); what types of trauma cause fawning
(fawn-response); how does fear of intimacy relate to social anxiety (fear-of-intimacy).

---

Method note: verdicts were produced per INSTRUCTIONS.md with the final-batch rigor additions
(third-article rule, serp_quality, register analysis). All 65 pages have a verdict; no page in
batch-order.md is unjudged.
