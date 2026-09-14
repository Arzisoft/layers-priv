---
course: "The Mastery"
module: "Module 5: Seeding, Backups and Restores"
lesson: "Module 5: Seeding, Backups and Restores — Exam"
type: "course_quiz"
post_id: 105097801
space_id: 24191170
source: "https://the-faction.mn.co/posts/105097801"
updated: "2026-08-10T20:44:09Z"
---

# Module 5: Seeding, Backups and Restores — Exam

> Exam for **Module 5: Seeding, Backups and Restores** (The Mastery) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. What is seed data for in an AI-built app?

- **A.** Live customer data imported early so the app launches with a realistic-looking user base
- **B.** Known starter records, like categories and admin accounts, the app needs to work from day one  ✅
- **C.** Encrypted filler rows that hide the real records from anyone browsing the live database directly
- **D.** Placeholder rows the database engine requires before it will accept any real writes at all

> **Answer:** B

### Q2. Why keep seed scripts separate from migrations?

- **A.** Combined files exceed most databases' script size limits once seeds grow past a few rows
- **B.** Seeds run faster alone, and mixing them makes migration timing impossible to measure
- **C.** Vendors charge separately for data changes and structure changes on managed plans
- **D.** Structure and data change for different reasons; mixing them makes both harder to rerun safely  ✅

> **Answer:** D

### Q3. Your AI seeded the dev environment with realistic fake data. Why is fake better than a copy of production here?

- **A.** No real customer information sits in a weaker environment, and the shape still tests the app  ✅
- **B.** Fake data compresses better, keeping the development database inside the vendor's free pricing tier
- **C.** Production copies are watermarked by the vendor and can trigger licensing audits later
- **D.** Fake rows load faster, since generated values skip the validation that real data requires

> **Answer:** A

### Q4. What makes a backup schedule adequate rather than merely present?

- **A.** It runs at midnight, the industry-standard hour when backup integrity is at its highest
- **B.** It emails a confirmation to the founder, creating the paper trail that auditors ask for
- **C.** Its frequency matches how much data you can afford to lose, your real recovery point  ✅
- **D.** It keeps exactly seven copies, the retention count that most frameworks recommend

> **Answer:** C

### Q5. What is point-in-time recovery, and when do you need it?

- **A.** Restoring the database to a specific moment, vital when bad data arrived at a known time  ✅
- **B.** Restoring only the newest rows, useful when a table's history is too large to fully reload
- **C.** Rolling the app's code and data back together, needed after any failed deployment
- **D.** A vendor service that pauses billing during outages, needed for cost recovery claims

> **Answer:** A

### Q6. A restore drill means what, concretely?

- **A.** Rehearsing the incident call script so stakeholders hear a calm voice during real outages
- **B.** Actually restoring a backup into a test environment and verifying the app runs against it  ✅
- **C.** Deleting a production table on purpose quarterly to keep the team's reflexes sharpened
- **D.** Timing how long the backup file takes to download from cloud storage down to a local machine

> **Answer:** B

### Q7. The backup job has reported success for six months straight. What does that actually prove?

- **A.** The data is safe, since a successful backup job is the definition of recoverability
- **B.** Retention is working, since success messages only fire when the old copies rotate out
- **C.** The database is healthy, since backups fail first when corruption starts to spread
- **D.** Only that a job ran; whether the copies can restore your app is unknown until tested  ✅

> **Answer:** D

### Q8. Where should backups live relative to the database they protect?

- **A.** On the same server for speed, since restore time is the metric that matters the most
- **B.** Inside the database itself as a compressed table, keeping everything in one place
- **C.** Somewhere separate, so the failure or breach that takes the database can't take them too  ✅
- **D.** On the founder's laptop, the one location the operations team can always reliably reach quickly

> **Answer:** C

### Q9. Your AI proposes seeding production with test accounts to demo features to a prospect. What is the risk?

- **A.** Demo accounts consume licensed seats, raising the monthly bill for every real user
- **B.** Test data mixes into real data, polluting metrics and risking exposure to actual customers  ✅
- **C.** Seeding locks the users table for hours, logging out every customer mid-session
- **D.** Prospects can legally claim ownership of any account created for their demonstration

> **Answer:** B

### Q10. How long should backups be kept?

- **A.** Per a retention policy balancing recovery needs, storage cost, and any legal duties  ✅
- **B.** Forever, since deleted backups are the leading cause of unrecoverable incidents
- **C.** One week, since data older than that no longer reflects the current live application state
- **D.** Until the next successful backup, since only the latest copy is ever restorable

> **Answer:** A

### Q11. A bug wrote garbage into one table for three hours yesterday. What does a good setup let you do?

- **A.** Undo the bug by running the code in reverse, replaying yesterday's traffic backward
- **B.** Blame isolation: identify which agent wrote the rows so the responsible tool can be retired
- **C.** Restore that table to just before the bug from backups, without losing the rest of the day  ✅
- **D.** Nothing targeted; any restore replaces the entire database at whole-day granularity

> **Answer:** C

### Q12. What should be true of the credentials and keys needed to restore from backup?

- **A.** Only the AI agent holds them, since automation must never wait on human availability
- **B.** They rotate hourly, so leaked restore credentials expire before they can be misused
- **C.** They live in the same vault as the backups, keeping the recovery kit all in one convenient place
- **D.** More than one trusted person can reach them; recovery can't depend on a single individual  ✅

> **Answer:** D

### Q13. Recovery time objective, or RTO, asks which question?

- **A.** How long the business can be down while you restore, from failure to working again  ✅
- **B.** How many backup copies exist at any moment across all of the different storage locations
- **C.** How old the database engine can be before the vendor stops supporting restores
- **D.** How many people must approve a restore before it is permitted to begin running

> **Answer:** A

### Q14. Your AI-built app added three new tables last month. What backup question must you ask?

- **A.** Whether the new tables slowed the backup job beyond its scheduled completion window
- **B.** Whether they're actually included in the backups, since coverage doesn't extend itself  ✅
- **C.** Whether the vendor's per-table backup fees have pushed the plan into a higher tier
- **D.** Whether the tables' names sort correctly, since backups process all tables alphabetically

> **Answer:** B

### Q15. What belongs in the runbook for a database restore?

- **A.** Exact steps, locations, credentials, and verification checks, written for use under stress  ✅
- **B.** A motivational preamble, since restores fail most often from low team morale levels
- **C.** The history of every past incident, so responders can study patterns mid-restore
- **D.** Legal disclaimers protecting the person performing the restore from later liability

> **Answer:** A

### Q16. Why test that seed data still works after schema changes?

- **A.** Stale seeds inflate storage costs, since failed inserts are retained in the error log
- **B.** Vendors flag failing seed scripts as abuse of the platform's automation limits
- **C.** Broken seeds block fresh environments, and you find out at the worst time: setup or recovery  ✅
- **D.** Seed failures corrupt existing data, overwriting live rows with the outdated values

> **Answer:** C

### Q17. A teammate needs a copy of production data for debugging. What is the disciplined response?

- **A.** Send the latest backup file directly, since backups exist precisely for this exact purpose
- **B.** Grant them live production access instead, avoiding any data duplication entirely
- **C.** Decline always, since production data can never legitimately leave production
- **D.** Provide a masked or minimized copy that keeps the bug visible but strips sensitive fields  ✅

> **Answer:** D

### Q18. What is the danger of backups that require the original app to be running to restore?

- **A.** Restore speed halves, since the app and the restore compete for the same resources
- **B.** Circular dependency: the disaster that took the app down also takes your recovery path  ✅
- **C.** Licensing conflicts, since one key can't validate the app and restore it simultaneously
- **D.** None; app-assisted restores are safer since the app validates each row it accepts

> **Answer:** B

### Q19. After completing a restore, what confirms the recovery actually succeeded?

- **A.** The restore command exiting without errors, the definitive signal recovery tools provide
- **B.** The database's file size matching the backup's size within a small tolerance band
- **C.** The app's critical paths working and spot-checked data matching what you expect to see  ✅
- **D.** A full week without customer complaints about anything that looks like missing data

> **Answer:** C

### Q20. How often should restore drills happen?

- **A.** On a recurring schedule, and after major changes, so the procedure never rots quietly  ✅
- **B.** Once at launch, since a proven procedure remains proven for the entire life of the system
- **C.** Only after real incidents, since drills without stakes teach nothing that transfers
- **D.** Daily, since anything less frequent leaves unacceptable gaps in operational readiness

> **Answer:** A

### Q21. Your AI suggests automating backups but leaving restores manual. Why does that stand up?

- **A.** It doesn't; restores must be automated too or the backup automation is essentially meaningless
- **B.** Manual restores are legally required, since automation cannot accept the liability
- **C.** Restore automation is impossible, since every incident differs too much to script
- **D.** Backups are routine to automate; restores are rare, high-stakes, and deserve a human call  ✅

> **Answer:** D

### Q22. The staging environment restores last night's production backup every morning. What does this practice quietly give you?

- **A.** Free storage, since restored staging data doesn't count against the backup quota
- **B.** A daily proof that backups actually restore, plus realistic staging data, at no extra effort  ✅
- **C.** Compliance certification, since regulators accept staging restores as full audits
- **D.** Faster production queries, since the morning restore warms the shared cache layers

> **Answer:** B

### Q23. What is the recovery point objective, or RPO, in plain terms?

- **A.** The point in the runbook where responsibility passes from the AI to the human on call
- **B.** The number of restore attempts permitted before the vendor's support must be engaged
- **C.** How much recent data you're willing to lose, which sets how often backups must run  ✅
- **D.** The moment during recovery when stakeholders are first notified about the incident

> **Answer:** C

### Q24. What single failure makes every other part of a backup strategy worthless?

- **A.** Backups running an hour late, since stale copies are legally the same as no copies
- **B.** Storing backups in more than two regions, which fragments the recovery process
- **C.** Naming backups inconsistently, since restore tools locate copies strictly by their name
- **D.** Never testing a restore, since an unrestorable backup is indistinguishable from none  ✅

> **Answer:** D

### Q25. Which principle should govern seeding, backups, and restores in every build you direct?

- **A.** A backup only counts once it has restored; design for the day you need it, not the day you take it  ✅
- **B.** Volume wins: the more copies in more places, the safer, whatever the cost or process
- **C.** Backups are the host's job: managed platforms make customer-side recovery redundant
- **D.** Seed everything from production: real data is the only trustworthy test material there is

> **Answer:** A


---
_Take it in the browser: https://the-faction.mn.co/posts/105097801_
