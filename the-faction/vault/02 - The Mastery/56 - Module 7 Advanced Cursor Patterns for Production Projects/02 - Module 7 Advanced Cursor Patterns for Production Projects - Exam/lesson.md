---
course: "The Mastery"
module: "Module 7: Advanced Cursor Patterns for Production Projects"
lesson: "Module 7: Advanced Cursor Patterns for Production Projects — Exam"
type: "course_quiz"
post_id: 107131827
space_id: 24191170
source: "https://the-faction.mn.co/posts/107131827"
updated: "2026-09-10T20:10:42Z"
---

# Module 7: Advanced Cursor Patterns for Production Projects — Exam

> Exam for **Module 7: Advanced Cursor Patterns for Production Projects** (The Mastery) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. A builder opens a 500-file codebase and starts directing changes across the whole thing at once. What does this module say about that approach?

- **A.** It works if the context window setting is raised first, since modern models will hold full projects once the window limit is configured up
- **B.** No model holds a project that size in view at once, so production directing works in deliberate scopes: one area, one contract, one pass  ✅
- **C.** It is the recommended production pattern, since whole-project direction is what distinguishes advanced builders from cautious ones
- **D.** It works only on weekends, since whole-project passes need uninterrupted hours that weekday sessions cannot reliably provide builders

> **Answer:** B

### Q2. A builder is tempted to send 'modernize this codebase' as one sweeping instruction. What does this module call this, and what replaces it?

- **A.** A stretch goal, kept but softened with a please, since sweeping modernization succeeds when the framing invites model creativity
- **B.** A budget decision, delegated to the client, since sweeping instructions are fine once someone else accepts the associated risks
- **C.** How projects die; replaced by a directed sequence: map what exists, plan stages, execute one stage per pass, verify, commit between stages  ✅
- **D.** An indexing test, run deliberately, since sweeping instructions are how builders discover whether the codebase index is complete

> **Answer:** C

### Q3. Per this module, what must be true of every stage in a staged refactor plan?

- **A.** Each stage doubles the previous stage's size, since momentum builds through the refactor and later stages can absorb more change
- **B.** Each stage leaves the app working and includes a verification step, so any failure is contained to the stage that caused it  ✅
- **C.** Each stage touches every file at least once, since even coverage across the codebase is what keeps a refactor from drifting
- **D.** Each stage is executed by a different model, since rotating models across stages prevents any single model's biases accumulating

> **Answer:** B

### Q4. A builder directs the AI to review a diff set and then ships without reading the diffs themselves. What does this module say about the arrangement?

- **A.** It is the intended workflow, since AI review exists to replace builder reading and doubled review wastes the time savings
- **B.** It is acceptable above a quality threshold, since mature projects with rules files can safely delegate final review to the AI
- **C.** It works when the review found nothing, since a clean AI review is stronger evidence than a builder's own reading would be
- **D.** The AI review is a second pass, not a substitute: the builder reads the diffs regardless and remains the reviewer of record  ✅

> **Answer:** D

### Q5. This module describes quality on production projects as a system with four parts. Which set matches?

- **A.** Backups, monitoring, alerts, and rollbacks, since quality is an operations concern that starts after the code has shipped to users
- **B.** Talent, effort, focus, and caffeine, since production quality ultimately reduces to the condition of the builder on delivery day
- **C.** Rules stating standards, linting enforcing mechanics, directed review for judgment, and a smoke-test checklist for key paths  ✅
- **D.** Contracts, invoices, deadlines, and penalties, since commercial pressure is the system that actually holds quality in place

> **Answer:** C

### Q6. A change touches the authentication module. Beyond normal review, what does this module require?

- **A.** A dedicated security review pass: injection, authentication gaps, and data exposure, since auth changes get their own lens  ✅
- **B.** A public changelog entry, since authentication changes must be disclosed to users before they can be deployed anywhere
- **C.** A two-week soak period, since authentication changes need calendar time in staging regardless of what review finds
- **D.** A rewrite in a memory-safe language, since security review is secondary to eliminating the class of bugs at the source

> **Answer:** A

### Q7. A builder inherits a large codebase and begins changing it without any mapping step. What does this module say each change becomes?

- **A.** A guess about structure the builder never established, which is why the module says to map before any change on inherited code  ✅
- **B.** A billable unit, since mapping is overhead clients resist paying for and unmapped changes convert directly to invoices
- **C.** A learning opportunity, since unmapped changes teach the structure faster than any mapping exercise could have done
- **D.** A test of the AI, since unmapped changes reveal whether the model can fully compensate for the builder's missing project knowledge

> **Answer:** A

### Q8. In the module's example, stage five of a seven-stage migration breaks a report page. What happened next, per the pattern?

- **A.** The whole migration rolled back to stage one, since a mid-sequence failure invalidates the plan and everything built on it
- **B.** Stages six and seven were executed anyway, since finishing the plan first gives the fix the benefit of the final architecture
- **C.** The client was asked to accept the breakage, since a working report page was traded against the migration's overall deadline
- **D.** The seam test caught it before the client did; the stage rolled back, was re-planned smaller, and landed on the next pass  ✅

> **Answer:** D

### Q9. This module says a directed severity-ranked review should categorize issues. Which categories does it model?

- **A.** Red, orange, yellow, and green, since color scales communicate risk faster than words in a review that will be skimmed
- **B.** Blocker, should-fix, and nitpick, with file and line cited for each issue so every finding is locatable and actionable  ✅
- **C.** Frontend, backend, and database, since sorting by layer is what makes a review actionable for specialized teammates
- **D.** Cheap, moderate, and expensive, since fix cost is the ranking that lets a builder schedule remediation into a sprint

> **Answer:** B

### Q10. A builder keeps re-explaining the project's architecture at the start of every session. Which production practice does this module offer?

- **A.** Longer sessions, since fewer session boundaries means fewer re-explanations and endurance is the underlying skill to build
- **B.** Map once and save it as a context document in the repo, where it compounds across sessions and teammates instead of evaporating  ✅
- **C.** A recorded voice memo, since spoken architecture explanations transfer subtle nuance that written maps consistently lose in practice
- **D.** Memorizing the explanation, since fluent recall of architecture is the mark of a builder ready for production responsibility

> **Answer:** B

### Q11. A task list contains long, mechanical, well-specified sweeps and delicate interactive judgment work. How does this module divide it?

- **A.** Mechanical sweeps are candidates for Claude Code autonomous runs, while interactive judgment work stays in Cursor for review  ✅
- **B.** Everything goes to Claude Code, since a tool that runs autonomously strictly dominates one that needs a builder present
- **C.** Everything stays in Cursor, since splitting a task list across tools fragments the context that keeps the work coherent
- **D.** The AI decides at runtime, since tool selection is itself a task the model performs better than the builder directing it

> **Answer:** A

### Q12. A builder is fighting Cursor for an hour trying to produce a client proposal document. What does this module say this moment is?

- **A.** A prompt-quality problem, since documents emerge cleanly from Cursor when the instruction specifies formatting precisely enough
- **B.** A missing-extension problem, since document tooling exists in the marketplace and the hour was lost to an incomplete setup
- **C.** A model-selection problem, since proposal writing needs the strongest model and the fight signals the wrong one was active
- **D.** A wrong-tool moment: non-code deliverables belong in their own tools, and recognizing this is a mastery skill, not a betrayal  ✅

> **Answer:** D

### Q13. Why does this module insist on committing between refactor stages?

- **A.** So each stage gets its own branch name, since branch hygiene rather than rollback is the reason stages are separated at all
- **B.** So the commit count impresses the client, since visible activity in the repository is how production progress gets judged
- **C.** So the AI can bill per stage, since usage metering aligns to commits and uncommitted stages are unbillable work in flight
- **D.** So a failing stage can be rolled back alone instead of taking the earlier completed stages down with it when things break  ✅

> **Answer:** D

### Q14. This module names a pre-delivery practice for client work. What is it?

- **A.** A price review, since scope drift means every delivery should be re-quoted before the client sees the finished work
- **B.** A full rewrite of recent changes, since pre-delivery is the last chance to replace rushed work with considered work
- **C.** The smoke-test checklist: the handful of paths that must always work, run before every delivery, every single time  ✅
- **D.** A day of silence, since letting the build rest untouched surfaces problems that continuous work keeps hidden away

> **Answer:** C

### Q15. A standard keeps slipping across sessions despite the builder's best intentions. What does this module say to do?

- **A.** Fix the system: add the rule, the lint, the checklist line, as slipping standards are a configuration gap, not willpower  ✅
- **B.** Lower the standard to match reality, since a standard that keeps slipping was set above what the project actually needs
- **C.** Rely on remembering harder, since standards are ultimately habits and repetition is how habits become automatic over time
- **D.** Schedule a weekly standards meeting, since slippage is a communication problem that documentation cannot reach on its own

> **Answer:** A

### Q16. Which model does this module say to use for planning, architecture, and review passes on production work?

- **A.** The fastest model, since planning is iterative and quick turnaround matters more than depth at the planning stage of work
- **B.** A randomly rotated model, since varying the planner prevents architectural bias from accumulating across the project
- **C.** The strongest model, since model choice matters more on production work and these passes carry the highest judgment load  ✅
- **D.** The cheapest model, since planning output is short and spending capability budget on long generation phases pays better

> **Answer:** C

### Q17. A cross-area change spans two regions of a mapped codebase. What treatment does this module give it?

- **A.** Contract treatment: name both sides, change both sides, and test the seam where the two areas meet after the change lands  ✅
- **B.** Freeze treatment: cross-area changes wait for a quarterly window when both areas can be rebuilt together from scratch
- **C.** Split ownership: each area's half is changed in a separate sprint so no single session ever sees both sides of the change
- **D.** Escalation treatment: cross-area changes leave the builder's authority and require the original authors to approve them

> **Answer:** A

### Q18. The module's example client sees 'a working app every single week' during a month-long migration. What produced that outcome?

- **A.** Heroic weekend recoveries, since weekly working demos during migrations are achieved by repairing breakage before Mondays
- **B.** A demo environment pinned to the pre-migration build, since showing the old app weekly is what keeps clients reassured
- **C.** Staged execution where every stage leaves the app working, verified and committed, so there is never a broken in-between state  ✅
- **D.** Reduced scope each week, since trimming the migration's ambitions is exactly how weekly stability is normally purchased in practice

> **Answer:** C

### Q19. What does this module mean by 'quality by vibes,' and what is its cost?

- **A.** Quality from team morale, which costs money, since good vibes are produced by perks the project budget must absorb over time
- **B.** Quality from aesthetic taste, which costs speed, since visually driven review reads every diff twice before accepting it
- **C.** No rules, no linting, no checklist: quality varies with the builder's energy level, and clients notice the inconsistency  ✅
- **D.** Quality from intuition, which the module endorses, since experienced builders' instincts outperform any explicit system

> **Answer:** C

### Q20. A builder asks where architecture maps, decision records, and checklists should live. What does this module say, and why?

- **A.** In the builder's personal notes app, since production documents are individual work products that travel with the person
- **B.** In the client's project management tool, since stakeholders own documentation and builders only contribute drafts to it
- **C.** In chat history, since past conversations are searchable and duplicate documents drift from what was actually discussed
- **D.** In the repo as markdown, since context documents compound across sessions and teammates when they live with the code  ✅

> **Answer:** D

### Q21. This module says production patterns are 'the same primitives from earlier modules under discipline.' Which primitives does it mean?

- **A.** Diff review, rules, indexing, Git, and the terminal, composed into staged, scoped, verified production workflows  ✅
- **B.** Keyboard shortcuts, themes, fonts, and window layouts, since production readiness is mostly environmental polish
- **C.** Pricing tiers, seat licenses, usage caps, and quotas, since production is where the commercial primitives take over
- **D.** New advanced features unlocked at this level, since production workflows run on capabilities earlier modules never see

> **Answer:** A

### Q22. A directed review found nothing, but the builder's own diff read catches a subtle data-handling issue. Per this module, what does this show?

- **A.** The review instruction was malformed, since a correctly directed review would have surfaced everything the builder found
- **B.** Why the builder stays reviewer of record: the AI review is a supplement catching real problems, not a guarantee of catching all  ✅
- **C.** The issue was not real, since disagreement between reviewer and AI resolves in favor of the reviewer with more context, the model
- **D.** The builder should review less, since duplicated findings show the passes overlap and one of the two can safely be dropped

> **Answer:** B

### Q23. When is an all-at-once refactor acceptable, per this module?

- **A.** It is not: the all-at-once refactor produces an all-at-once failure you cannot bisect, which is why stages exist at all  ✅
- **B.** When a deadline demands it, since staging is a luxury of calendar room and compressed timelines justify compressed process
- **C.** On codebases under fifty files, since the staged pattern only pays for itself above a certain project size threshold
- **D.** When the AI proposes it, since a model that volunteers a single-pass plan has judged the risk acceptable for this codebase

> **Answer:** A

### Q24. A builder wants the smoke-test checklist to actually get used before deliveries. Which directed pattern does this module model?

- **A.** Reciting the checklist from memory before each delivery, since memorization is what makes a checklist part of the builder
- **B.** Run through the smoke-test checklist in the repo and tell me what to verify manually in the browser, directed pre-delivery  ✅
- **C.** Converting the checklist into a legal document, since contractual weight is what separates used checklists from ignored ones
- **D.** Emailing the checklist to the client, since external accountability is the only pressure that makes checklists survive

> **Answer:** B

### Q25. Looking across this whole course, what is the governing principle of advanced Cursor patterns for production projects?

- **A.** Delegation over involvement: at the production level the builder's job is selecting tools and accepting output, since review and verification are what the AI layer exists to absorb
- **B.** Capability over process: on production work the strongest model with the broadest instructions replaces staging, scoping, and checklists for builders who direct with confidence
- **C.** Speed over structure: production pressure rewards builders who skip mapping and staging, since clients pay for shipped features rather than for verified intermediate states
- **D.** Discipline over drama: map once, scope every pass, stage and verify every big change, review as the reviewer of record, systematize quality, and hand the work to the right tool  ✅

> **Answer:** D


---
_Take it in the browser: https://the-faction.mn.co/posts/107131827_
