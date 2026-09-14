---
course: "The Frontier"
module: "Module 5: Prompt Testing and Evaluation"
lesson: "Module 5: Prompt Testing and Evaluation — Exam"
type: "course_quiz"
post_id: 106161842
space_id: 24391596
source: "https://the-faction.mn.co/posts/106161842"
updated: "2026-08-21T15:23:05Z"
---

# Module 5: Prompt Testing and Evaluation — Exam

> Exam for **Module 5: Prompt Testing and Evaluation** (The Frontier) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. Your support bot handles 10,000 conversations a day. You tweak one line to make refund replies warmer and it looks great on the three chats you eyeball. Why is that not a valid testing strategy?

- **A.** Three samples are enough for tone changes, but refund wording changes need at least ten sampled conversations to confirm
- **B.** Spot checks are valid only if the three conversations were chosen randomly, so the fix is randomizing which chats you review
- **C.** Eyeballing works for user-facing text, but only structured outputs like JSON need automated checks before they ship safely
- **D.** Spot checks are biased toward easy inputs and miss rare failure modes, so the change could break hundreds of chats unseen  ✅

> **Answer:** D

### Q2. You are about to build a data extraction system that pulls invoice fields from uploaded PDFs. Before drafting the prompt, what should you do first?

- **A.** Write the evaluation criteria first: required fields, allowed values, and failure conditions, so success is defined up front  ✅
- **B.** Draft the prompt first, then infer criteria from its best outputs, since you cannot know good until the model shows you it
- **C.** Start with a large test set and let the failing cases reveal the criteria, because criteria written up front are only guesses
- **D.** Ship a small pilot to production and derive criteria from real complaints, since only live traffic defines what correct means

> **Answer:** A

### Q3. After a model swap, your working prompt starts failing cases it used to pass. You decide to build a regression test set. What is the one question that set exists to answer?

- **A.** Did this change break anything that used to work, answered by rerunning saved inputs with pass criteria after every edit  ✅
- **B.** Does your prompt outperform competitor systems, so you can prove your version beats the industry baseline on output quality
- **C.** Can the prompt handle fresh synthetic inputs generated each run, so it is always tested on data it has never seen before
- **D.** Which model is cheapest and fastest across versions, so you can pick the lowest-cost option that still produces valid output

> **Answer:** A

### Q4. Your extraction system corrupts a record in production on an input format you never anticipated. You fix the prompt and it now handles that input. What should happen next?

- **A.** Patch the prompt for that input and move on, since one-off failures are noise and adding them bloats future test runs
- **B.** Remove similar cases from the test set so the failure pattern cannot skew your aggregate scores on the next regression run
- **C.** Add the failing input to the test set permanently, so the set grows into a record of what your prompt must never break again  ✅
- **D.** Log the failure in the scorecard but keep the test set frozen, since a stable set is required to compare fairly across all versions

> **Answer:** C

### Q5. Comparing prompt versions for your support bot, a teammate rewrote three instructions at once between version A and version B, then ran both on the same inputs. What is wrong with this A/B test?

- **A.** The comparison is fine as long as both versions run on identical inputs, since input parity is what makes a test controlled
- **B.** Change one variable at a time, because with three edits bundled you cannot tell which helped and which is silently hurting  ✅
- **C.** Bundling edits is standard practice; the fix is running version B on a larger input set so extra changes average themselves out
- **D.** The problem is sample size, not the edits; three changes are acceptable when each version is scored by the same rubric after

> **Answer:** B

### Q6. In an A/B test of your brand-voice content prompt, version B produces one strikingly better post than version A on a shared input. What should you do before calling a winner?

- **A.** Declare B the winner, since a clearly superior output on a shared input is the strongest evidence one version can produce
- **B.** Rerun only version A, because the burden of proof sits with the incumbent prompt rather than with the challenger version
- **C.** Ship B behind a feature flag and let production traffic decide, since live users are more reliable than any offline test
- **D.** Run each input multiple times for both versions, because outputs vary and a single result can flatter either version  ✅

> **Answer:** D

### Q7. You ran prompt versions A and B against the full input set, multiple runs each, scored with the same rubric. How should the winner be declared?

- **A.** On aggregate scores across the whole input set, never on whichever version produced the single most impressive output  ✅
- **B.** On the single hardest input alone, since a version that handles the worst case will handle everything easier than it
- **C.** By having stakeholders review five sample outputs from each and vote, since human judgment beats numeric scoring here
- **D.** By picking the version with the shorter prompt text, since fewer instructions means fewer failure points in production

> **Answer:** A

### Q8. Your data extraction system outputs flawless JSON every time, but a client reports invoice numbers in the results that do not exist in the source documents. Which quality dimension did your testing miss?

- **A.** Format compliance, because invented invoice numbers are a structural defect a stricter JSON schema check would have caught
- **B.** Hallucination rate, because a perfectly structured output can still invent facts, and structure checks never catch fabrication  ✅
- **C.** Consistency, because invented values appear when the same input produces different outputs, so run-to-run variance is the true root cause
- **D.** Accuracy alone, because hallucination is just an accuracy subtype and tracking it separately double-counts the same failures

> **Answer:** B

### Q9. Your extraction prompt hallucinates a field value 2 percent of the time and processes 10,000 documents a day. What does that rate mean in practice?

- **A.** About 200 corrupted records flowing silently into your database every day, which makes the rate a serious liability at scale  ✅
- **B.** About 20 corrupted records per day, a level low enough that occasional manual review can absorb it without any test set
- **C.** About 2,000 corrupted records per day, meaning the prompt is failing on roughly one in every five of the documents it processes
- **D.** No corrupted records at all, because a 2 percent hallucination rate refers to formatting drift, not invented field values

> **Answer:** A

### Q10. You run a brand-voice content pipeline and want to measure consistency as a quality dimension. What does consistency mean here?

- **A.** Whether the output matches the tone of one gold-standard sample, judged by the builder reading both versions carefully side by side
- **B.** Whether the prompt keeps working after the model provider ships an update, measured by rerunning the set once per quarter
- **C.** Whether the same input produces equivalent output across repeated runs, since run-to-run variance is measured, not assumed  ✅
- **D.** Whether every output stays under the length limit, since posts that run long are the clearest signal of a drifting voice

> **Answer:** C

### Q11. A builder validates a data pipeline's outputs with a JSON schema check only and considers testing complete. What is the flaw in that approach?

- **A.** There is none; malformed structure and invented values both surface as schema violations, so one validator covers both risks
- **B.** The validator should be replaced with human review, since automated structure checks add little once a prompt is stable
- **C.** Structure checks catch broken JSON but not invented values, so the pipeline can pass validation while writing confident fiction  ✅
- **D.** The validator only needs stricter typing, because hallucinated fields are always the wrong data type and strict types expose them

> **Answer:** C

### Q12. You are setting up a professional development loop for a new support bot prompt. Which sequence describes the loop correctly?

- **A.** Draft, ship, monitor, patch: get the prompt into production quickly and let real traffic surface the failures worth fixing
- **B.** Measure, draft, ship, test: score the old version first, then draft and release, testing afterward to confirm the gamble paid off
- **C.** Test, draft, iterate, archive: run the set before writing anything, then retire each version once its scores stop improving
- **D.** Draft against predefined criteria, test on the full input set, measure the four dimensions, iterate on the weakest failure mode  ✅

> **Answer:** D

### Q13. Your test set of 30 clean, well-formed inputs passes 100 percent, yet the prompt keeps failing in production. What is the most likely cause?

- **A.** The set is too large; trim it to the twenty cleanest cases so each regression run finishes fast enough to run on every change
- **B.** The model is at fault; swap providers, because a prompt that passes its own test set has been validated as production ready
- **C.** The pass criteria are too strict; loosen them until production inputs pass at the same rate as the curated test inputs did
- **D.** The set only covers happy paths; production feeds your prompt typos, hostile users, and malformed data, where prompts die  ✅

> **Answer:** D

### Q14. A teammate changes one word in a production prompt and ships it without rerunning the regression set, calling the edit too small to test. How should you assess that?

- **A.** Reasonable, because one-word edits sit below the threshold where behavior can change, so a quick spot check is plenty
- **B.** Risky, because the untested small tweak is exactly the one that breaks a working case; every change reruns the full set  ✅
- **C.** Reasonable, provided the changed word is not inside a numbered instruction, since only structural edits alter behavior
- **D.** Risky, but only for prompts over a thousand tokens, since short prompts are simple enough to verify by reading carefully

> **Answer:** B

### Q15. Before your agency builds a client's support bot prompt, you create an evaluation rubric document. What is this toolkit item?

- **A.** A written spec, created before the prompt, defining pass and fail per dimension; the contract and scoring key for every run  ✅
- **B.** A changelog of every prompt edit with timestamps, kept so the team can roll back to the last version that scored above bar
- **C.** A gallery of the very best outputs the prompt has produced, curated so new team members can see what excellent results look like
- **D.** A list of banned words and phrases the output must avoid, compiled from client feedback and rechecked after model updates

> **Answer:** A

### Q16. You are constructing your first regression test set for a prompt that runs thousands of times daily. What should it look like?

- **A.** Three to five handpicked showcase inputs, refreshed weekly, so the set stays small enough to review by eye after each change
- **B.** Only synthetic inputs generated by another AI, since real production data is too messy to pair with objective pass criteria
- **C.** A single worst-case input run fifty times, because depth on the hardest case reveals more than breadth across easy cases
- **D.** A versioned file of 20 to 100 plus inputs with pass criteria, spanning common cases and edge cases, grown with each failure  ✅

> **Answer:** D

### Q17. You need an A/B comparison harness to test two versions of your extraction prompt. Per the module toolkit, what does that item look like in practice?

- **A.** A managed enterprise experimentation platform, since prompt comparisons are only trustworthy on dedicated statistical tools
- **B.** A live traffic splitter routing half of real users to each version, since offline comparisons can never predict real production wins
- **C.** A script or spreadsheet workflow, buildable by directing your AI for an afternoon, running both versions on identical inputs  ✅
- **D.** A shared document where teammates paste favorite outputs from each version and discuss which one feels stronger overall

> **Answer:** C

### Q18. Your team debates whether last month's prompt changes actually improved the support bot. Which toolkit item settles this, and how?

- **A.** The regression test set, because once a prompt is stable, tracked pass rates make measuring the quality dimensions redundant
- **B.** The quality scorecard: it tracks the four dimensions per version over time, turning the debate into a chart instead of talk  ✅
- **C.** The cost report, because model API spend per version proves whether the prompt program pays for itself when challenged
- **D.** User star ratings collected after each conversation, since perceived quality is the only dimension that truly matters

> **Answer:** B

### Q19. Six months in, your regression test set has not gained a single case since launch, though production has logged a dozen novel failures. What does this mean?

- **A.** Nothing is wrong; a passing test set is a passing set, and stability in the safety net is exactly what regression testing is for
- **B.** The set has proven the prompt finished, so testing effort should shift entirely to monitoring model provider changelogs
- **C.** The set should be regenerated from scratch monthly, since aging inputs lose validity even when production keeps failing
- **D.** Your safety net has holes; production failures are not becoming test cases, so the set no longer reflects real traffic  ✅

> **Answer:** D

### Q20. An agency client asks how you know the new prompt works. A teammate answers that it looked good when they tried it. How should a professional view that answer?

- **A.** It is acceptable evidence when the builder is senior, since experienced judgment on sampled outputs approximates measurement
- **B.** It is an anecdote, and the fix is longer prompts, since more detailed instructions reduce the need for output testing overall
- **C.** It is an anecdote, not evidence; testing converts usually gets it right into a number you can defend, monitor, and improve  ✅
- **D.** It is sufficient for creative outputs but not data outputs, since voice quality cannot be reduced to measurable criteria

> **Answer:** C

### Q21. Your extraction prompt scores well on accuracy, consistency, and format compliance, but hallucinates 3 percent of field values. What is the right call?

- **A.** Do not ship it; strong scores on three dimensions cannot offset a 3 percent hallucination rate, a liability at any volume  ✅
- **B.** Ship it; three of four dimensions passing is a 75 percent quality score, comfortably above the standard 70 percent ship bar
- **C.** Ship it with a cleaner JSON schema, since tighter formatting rules will pull the invented values back toward grounded output
- **D.** Do not ship yet, but only because consistency needs a second measurement window before any extraction prompt goes live

> **Answer:** A

### Q22. You drafted against criteria, tested the full input set, and measured all four dimensions; hallucination rate is the weak spot. What is the next stage of the loop?

- **A.** Rewrite the entire prompt from scratch, since partial edits accumulate drift and a clean rebuild resets all four scores
- **B.** Iterate on the weakest failure mode until the numbers clear your ship threshold, then rerun the full set on every change  ✅
- **C.** Raise the ship threshold to match current scores, since thresholds should reflect what the model can realistically deliver
- **D.** Freeze the prompt and open a ticket with the model provider, since remaining failures at this stage are model defects

> **Answer:** B

### Q23. A builder asks why they should write evaluation criteria before drafting, since they plan to test thoroughly afterward anyway. What is the professional answer?

- **A.** Defining success precisely first forces clarity that makes the prompt itself better; if you cannot define it, do not build  ✅
- **B.** Criteria written first mostly protect against scope creep from clients, with little effect on the quality of the prompt text
- **C.** Writing criteria first matters only in regulated industries, where auditors require documentation before development starts
- **D.** It saves API costs by shortening the test phase, which is the main benefit, since criteria rarely change how prompts are written

> **Answer:** A

### Q24. Your content pipeline drifts off brand voice on about 1 in 20 posts, eroding client trust one publish at a time. How do you get this failure under measurement and control?

- **A.** Read every published post yourself for a month, since brand voice is subjective and only sustained human immersion can spot slow drift
- **B.** Add tone constraints to the pass criteria and run the regression set on every change, measuring consistency over repeated runs  ✅
- **C.** Lower the model temperature to zero, which removes variance entirely and makes voice testing unnecessary for content work
- **D.** Publish drafts to a small audience segment first, since engagement metrics are the most direct measure of voice compliance

> **Answer:** B

### Q25. Which statement best captures the governing principle of Module 5, Prompt Testing and Evaluation?

- **A.** The most capable model wins; testing effort matters far less than choosing the strongest available model for each task
- **B.** Prompts should be short; every added instruction increases failure surface, so minimal prompts need only minimal testing effort
- **C.** Ship prompts on evidence, not vibes: define success first, measure systematically, and let numbers, not impressions, decide  ✅
- **D.** Automation replaces judgment; once a test harness exists, builders no longer need to review any outputs before shipping

> **Answer:** C


---
_Take it in the browser: https://the-faction.mn.co/posts/106161842_
