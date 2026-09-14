---
course: "The Mastery"
module: "Module 4: Migrations Without Downtime"
lesson: "Module 4: Migrations Without Downtime — Exam"
type: "course_quiz"
post_id: 105097609
space_id: 24191170
source: "https://the-faction.mn.co/posts/105097609"
updated: "2026-08-10T20:44:09Z"
---

# Module 4: Migrations Without Downtime — Exam

> Exam for **Module 4: Migrations Without Downtime** (The Mastery) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. What is a database migration?

- **A.** A scripted, versioned change to the database's structure that can be applied and tracked reliably  ✅
- **B.** Moving the database to a different hosting provider in search of lower monthly pricing
- **C.** Exporting all data to spreadsheets so a new schema can be populated from clean files
- **D.** The nightly transfer of data from the application's memory into permanent disk storage

> **Answer:** A

### Q2. Why do schema changes on a live app risk downtime at all?

- **A.** Hosting providers require an approval window before any structural change may legally execute
- **B.** Users must be logged out during changes, since sessions pin the old schema in memory
- **C.** The app's code must be deleted and redeployed from scratch after each schema change
- **D.** Some changes lock tables while they run, and a locked table means requests pile up and fail  ✅

> **Answer:** D

### Q3. What is the expand-contract pattern for zero-downtime changes?

- **A.** Growing the server before a migration and shrinking it afterward to control the cost curve
- **B.** Compressing the tables before a change so the migration finishes inside one short window
- **C.** Add the new structure alongside the old, move code over gradually, then remove the old when unused  ✅
- **D.** Doubling the database's capacity, applying changes to the copy, then contracting back to one system

> **Answer:** C

### Q4. Your AI wants to rename a column that live code depends on. What is the safe sequence?

- **A.** Rename it at 3 AM, since the risk window is small and traffic is minimal during the late night hours
- **B.** Add the new column, write to both, migrate readers, backfill, then drop the old one when unused  ✅
- **C.** Rename it in one step, since modern databases propagate renames to running application code
- **D.** Skip the rename entirely; column names are permanent once any table reaches production

> **Answer:** B

### Q5. What does backfilling mean during a migration?

- **A.** Populating a newly added column with correct values for the rows that already existed  ✅
- **B.** Restoring deleted rows from backups after a migration removed more than was intended
- **C.** Reversing a migration by replaying the day's traffic against the previous schema state
- **D.** Filling the migration log with entries so audits show continuous database activity

> **Answer:** A

### Q6. Why should a large backfill run in small batches instead of one massive update?

- **A.** Databases bill per statement, so one giant update costs more than many small ones combined
- **B.** Small batches produce more log lines, giving the team better material for the retrospective
- **C.** A single huge update can lock the table and overwhelm resources; batches keep the app responsive  ✅
- **D.** Batching lets several AI agents work simultaneously, finishing the backfill many times faster overall

> **Answer:** C

### Q7. What must be true about the app's code during a schema migration's middle phase?

- **A.** It must be paused entirely, since no code can safely run while the structure is still in motion
- **B.** It must be rolled back to the previous release, matching the schema still on the disk
- **C.** It must run at half capacity, so the database has headroom to apply all the changes
- **D.** It must work with both old and new structure, since both exist while the change rolls out  ✅

> **Answer:** D

### Q8. Where should every migration run before it touches production?

- **A.** On the founder's local laptop, the environment most representative of real world conditions
- **B.** On a staging environment with production-like data, where locks and failures cost nothing  ✅
- **C.** In a code review only, since reading a migration reveals everything running it would
- **D.** On production first but during low traffic, since only production shows true behavior

> **Answer:** B

### Q9. Why must migrations live in version control alongside application code?

- **A.** Schema state and code state must move together and be reproducible for any point in time  ✅
- **B.** Version control compresses SQL efficiently, cutting the cost of storing migration history
- **C.** Regulators require public schemas, and version control satisfies the publication rule
- **D.** It lets the AI agent bill migration work separately from ordinary feature development

> **Answer:** A

### Q10. Your AI applied a schema change directly to production by hand to fix something quickly. What is the real problem?

- **A.** Manual changes run slower than scripted ones, extending the downtime window unnecessarily
- **B.** Untracked drift: production no longer matches the recorded schema, and future migrations may break  ✅
- **C.** The vendor's warranty on the database is void once manual changes have been detected
- **D.** Nothing, if it worked; speed of resolution is what matters most in a production incident

> **Answer:** B

### Q11. What makes a migration "reversible", and why should you care?

- **A.** It runs equally fast in both directions, guaranteeing symmetrical maintenance windows
- **B.** It carries insurance coverage, transferring the financial risk of failure over to the provider
- **C.** A defined way to undo it exists; when a deploy goes wrong you retreat instead of improvising  ✅
- **D.** The AI can regenerate it from memory, since the prompts that created it remain in logs

> **Answer:** C

### Q12. Which type of change is generally safe to apply without special choreography?

- **A.** Purely additive ones, like a new nullable column or a new table nothing depends on yet  ✅
- **B.** Any change to a column's type, since databases convert stored values automatically
- **C.** Dropping unused-looking columns, since anything unused is safe by its very own definition
- **D.** Renames of any kind, since names are labels with no effect on running behavior

> **Answer:** A

### Q13. The migration ran, and errors are spiking. What should already exist before this moment?

- **A.** A public apology template, drafted in advance so communications go out within the hour
- **B.** A list of competitors' outages, for context when explaining the incident to stakeholders
- **C.** A hiring plan for a database administrator, triggered automatically by the first failure
- **D.** A rollback plan and a healthy pre-change backup, decided before the migration ever ran  ✅

> **Answer:** D

### Q14. Why is dropping a column more dangerous than adding one?

- **A.** Dropped data is gone; if anything still read that column, you find out after it's unrecoverable  ✅
- **B.** Drops take longer than adds, since removal rewrites more of the table than creation does
- **C.** Drops require vendor approval on managed plans, which can take days you may not have
- **D.** Dropping renumbers the remaining columns, which silently breaks every stored query

> **Answer:** A

### Q15. When should the migration run relative to deploying the new app code that needs it?

- **A.** At the exact same second, using a combined script that updates both of them in a single action
- **B.** In an order where each step keeps the system working: expand first, code next, contract last  ✅
- **C.** Code first always, since applications should tolerate missing tables for a few hours
- **D.** Whenever the AI agent chooses, since ordering is an implementation detail it optimizes

> **Answer:** B

### Q16. What is the risk of testing migrations only against small, clean sample data?

- **A.** Small tests finish too quickly to appear in logs, leaving the audit trail woefully incomplete
- **B.** Sample data is copyrighted in most cases, creating exposure when the tests are shared
- **C.** None; migration correctness is logical, so data volume cannot ever change the outcome
- **D.** Production's volume and messy edge cases surface locks, timeouts, and failures samples miss  ✅

> **Answer:** D

### Q17. A migration will lock a large table for an estimated ten minutes. What do you direct?

- **A.** Run it immediately, since estimates overstate lock time and it will most likely finish faster
- **B.** Cancel the change permanently, since any lock measured in minutes is a design failure
- **C.** Find a lock-avoiding approach, like online schema change tools or batched incremental steps  ✅
- **D.** Accept it and email users afterward, converting the outage into a transparency moment

> **Answer:** C

### Q18. How do you know whether an old column is truly unused before dropping it?

- **A.** Search the code, check query logs over time, and monitor access, then drop only with evidence  ✅
- **B.** Ask the AI agent whether it remembers using the column in any of its previous builds
- **C.** Drop it and watch the error dashboards, since production is the only honest usage test
- **D.** Rename it with a warning prefix and wait a day; silence within a day proves that it is truly dead

> **Answer:** A

### Q19. What belongs in a migration's description beyond the change itself?

- **A.** The weather and time of authorship, environmental context for future forensic review
- **B.** The names of every stakeholder who approved it, for clear accountability in any later disputes
- **C.** The why: the intent and context, so a future reader understands the reason, not just the diff  ✅
- **D.** An apology in advance, softening relations with whoever has to debug it in the future

> **Answer:** C

### Q20. Your AI generated a migration that alters ten tables at once. Why direct it to split the work?

- **A.** Multi-table migrations are billed at premium rates by every managed database provider
- **B.** Smaller steps limit the blast radius and make failures diagnosable and reversible piece by piece  ✅
- **C.** Databases apply multi-table changes alphabetically, which rarely matches the real dependency order
- **D.** Version control cannot diff files that touch more than a handful of tables at once

> **Answer:** B

### Q21. What is schema drift between environments, and what does it cause?

- **A.** Gradual performance loss on older environments as their schema files fragment slowly on disk
- **B.** The natural aging of data types, which modern databases correct during nightly runs
- **C.** A licensing state where environments exceed the schema count that the plan permits
- **D.** Environments whose structures quietly differ, so what passed staging can fail in production  ✅

> **Answer:** D

### Q22. The safest mindset for production migrations treats each one as what?

- **A.** Routine paperwork, since fear of migrations is what actually causes migration failures
- **B.** A rare event to batch quarterly, minimizing the number of risk windows per year
- **C.** A small deployment with a plan, a test, a rollback, and verification, however minor it looks  ✅
- **D.** An AI responsibility, since agents apply structural changes more calmly than humans do

> **Answer:** C

### Q23. After a migration completes, what should you direct your AI to verify immediately?

- **A.** That the migration file is deleted, so it can never accidentally run a second time
- **B.** That the app's critical paths work and data spot-checks match expectations, not just "it ran"  ✅
- **C.** That the database is rebooted, clearing caches that hold the old structure in memory
- **D.** That a summary message is posted, closing the change window with clear communication

> **Answer:** B

### Q24. Why keep a record of exactly which migrations have run in each environment?

- **A.** Storage audits require it, since migration history explains the database's size growth
- **B.** It doubles as a performance log, showing how each change affected the query speed over time
- **C.** Migration counts factor into vendor pricing tiers on most managed database platforms
- **D.** So the same change never runs twice and every environment's state is knowable at a glance  ✅

> **Answer:** D

### Q25. Which principle should govern every migration you direct?

- **A.** Change structure the way surgeons operate: prepared, incremental, reversible, and verified after  ✅
- **B.** Move fast and fix forward: rollbacks are a crutch that slows the iteration that matters
- **C.** Avoid structural change entirely: the first schema should absorb every future requirement
- **D.** Outsource migrations fully to agents: human review adds latency without adding safety

> **Answer:** A


---
_Take it in the browser: https://the-faction.mn.co/posts/105097609_
