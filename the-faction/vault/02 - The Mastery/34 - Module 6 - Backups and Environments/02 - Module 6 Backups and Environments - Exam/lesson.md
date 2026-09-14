---
course: "The Mastery"
module: "Module 6 — Backups and Environments"
lesson: "Module 6: Backups and Environments — Exam"
type: "course_quiz"
post_id: 106187857
space_id: 24191170
source: "https://the-faction.mn.co/posts/106187857"
updated: "2026-08-21T15:20:21Z"
---

# Module 6: Backups and Environments — Exam

> Exam for **Module 6 — Backups and Environments** (The Mastery) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. A builder lets their AI run an untested migration directly on the production project, and it drops a column of live customer data. What deployment process should have been in place?

- **A.** Have the AI paste the SQL into the production dashboard editor so every change is logged in the project's own history.
- **B.** Run the migration on production during low traffic hours so fewer customers are affected if something goes wrong.
- **C.** Keep a second production project as a mirror and run every new migration there at the same moment as production.
- **D.** Write the migration as a versioned file, test it locally, apply it to staging, verify, then promote it to production.  ✅

> **Answer:** D

### Q2. A builder's AI ran a careless UPDATE without a WHERE clause at 4:12 p.m. They want to restore the database to 4:11 p.m., one minute before the mistake. What Supabase feature makes this possible, and where is it offered?

- **A.** Point-in-time recovery, an add-on on the Pro plan and above, which continuously archives write-ahead logs for replay.  ✅
- **B.** Automatic daily backups, included with every paid project, which snapshot the entire database once in every 24 hour window.
- **C.** Supabase branching, which keeps a temporary preview database per Git branch that can be swapped in as a rollback.
- **D.** A scheduled pg_dump stored in S3, which lets you restore the most recent off-platform copy from earlier that day.

> **Answer:** A

### Q3. After restoring a daily backup to recover from bad data, a builder finds their marketplace's uploaded files are still missing. Why did the restore not bring them back?

- **A.** The restore used the wrong snapshot, and choosing the previous day's backup would have recovered the files as well.
- **B.** Storage files are only included in backups once PITR is enabled, so the plan tier caused the files to be skipped.
- **C.** The files still exist, but their signed URLs expired during the restore, so regenerating links will recover them.
- **D.** Automatic backups cover the database only, so Storage objects need their own separate backup strategy and path.  ✅

> **Answer:** D

### Q4. A builder has one Supabase project that serves as everything: they prototype on it, test on it, and serve real users from it. What environment chain should they direct their AI to set up instead?

- **A.** A single production project with branching enabled, since preview branches replace the need for any separate environments.
- **B.** Two production projects kept in sync, so one serves live traffic while the other absorbs experimental changes.
- **C.** Local via the Supabase CLI running the full stack in Docker, a separate staging project with fake data, and production.  ✅
- **D.** A local Docker stack alone, since staging projects cost money and local testing catches every migration problem.

> **Answer:** C

### Q5. A builder wants a copy of their data that they control even if their Supabase account is suspended or their plan changes. What should they direct their AI to set up?

- **A.** A scheduled pg_dump script that stores dumps somewhere separate like S3, with the restore procedure tested at least once.  ✅
- **B.** PITR configured with the maximum retention window, since write-ahead log archives count as an independent off-platform copy.
- **C.** Daily backups plus a staging project, since the staging database doubles as an external copy of production data.
- **D.** Supabase branching, since each preview branch keeps a full copy of the data outside the production project itself.

> **Answer:** A

### Q6. A builder's migration passed local testing and was verified on staging. Their AI now needs to apply the versioned migration files to the linked production project. Which Supabase CLI command does that?

- **A.** supabase db reset, which rebuilds the linked remote schema from your migrations directory and reapplies seed data.
- **B.** supabase db diff, which computes the schema change and writes it straight to the remote project in a single step.
- **C.** supabase db push, which applies the repo's tracked migration files in order against the linked remote project.  ✅
- **D.** supabase start, which boots the production stack and replays every migration file committed to the repository.

> **Answer:** C

### Q7. A builder made a schema tweak in the local studio UI and wants it captured as a versioned migration file before environments drift. Which CLI workflow accomplishes this?

- **A.** Run supabase db diff to generate SQL for the change, then save it as a new timestamped migration file in the repo.  ✅
- **B.** Run supabase db push, which detects unversioned changes on the local stack and writes them back into the repository.
- **C.** Run supabase db reset, which snapshots the current local schema into a migration before rebuilding the database.
- **D.** Export the schema from the dashboard as SQL and paste it over the newest migration file already in the repository.

> **Answer:** A

### Q8. A team opens several pull requests at once, each changing the schema differently. They enable Supabase branching. What does branching give each pull request?

- **A.** A read-only replica of production, so each PR can be validated against live customer data without writing to it.
- **B.** A temporary preview database spun up for its Git branch, so each PR tests its schema changes in full isolation.  ✅
- **C.** A shared staging database where all open PRs apply their migrations together to surface conflicts early on merge.
- **D.** An automatic daily backup taken before each merge, so any PR that breaks the schema can be rolled back instantly.

> **Answer:** B

### Q9. A builder's staging project has empty tables, and every migration and RLS check passes instantly. Before trusting those results, what should they direct their AI to build?

- **A.** A script that copies the entire production database into staging nightly so tests always run against genuine customer records.
- **B.** A load-testing harness that inserts millions of random rows, since raw volume is what exposes broken policies.
- **C.** A version-controlled seed file loading realistic multi-tenant data: fake tenants, users in several roles, sample uploads.  ✅
- **D.** A nightly pg_dump of staging itself, so the empty schema is at least recoverable if a migration corrupts it later.

> **Answer:** C

### Q10. A builder gives their AI agent the production connection string so it can fix issues fast. According to this module, what is the safer setup for an agent working on the backend?

- **A.** Give the AI production access but require it to wrap every statement in a transaction it can roll back on error.
- **B.** Give the AI read-only production access plus staging write access, since read queries cannot damage the live data.
- **C.** Give the AI local and staging access only, and gate every production change behind the builder's own review step.  ✅
- **D.** Give the AI full access but enable PITR first, since point-in-time recovery makes any mistake fully reversible.

> **Answer:** C

### Q11. A builder on the free tier assumes Supabase is quietly backing up their database every night. When a restore is needed, what will they discover, per this module?

- **A.** Every project gets daily backups regardless of tier, but free tier restores must go through a support ticket queue.
- **B.** Automatic daily backups come with paid projects, with plan-dependent retention, so their tier may have nothing to restore.  ✅
- **C.** Free projects get weekly rather than daily snapshots, so they can restore but may lose up to seven days of data.
- **D.** Backups exist on every tier but are kept for one day only, so only same-day incidents can ever be recovered on free plans.

> **Answer:** B

### Q12. A builder's AI applies some schema changes via migrations while the builder makes others by hand in the production dashboard. Months later, migrations start failing unpredictably on staging. What went wrong?

- **A.** Dashboard edits leave no versioned record, so environments drifted apart and the migration history stopped matching.  ✅
- **B.** The staging project sits on a different Supabase plan tier, and migrations behave differently across the plan tiers.
- **C.** The migration files were applied out of order, since the CLI runs them alphabetically instead of strictly by timestamp order.
- **D.** The seed data grew stale after the schema changed, and stale seed rows make migrations fail their validation checks.

> **Answer:** A

### Q13. A builder's local database is cluttered with abandoned experiments and no longer matches the migration history. They want a clean local rebuild from the versioned files plus seed data. Which command should the AI run?

- **A.** supabase db reset, which rebuilds the local database from the migrations directory and reapplies the seed file.  ✅
- **B.** supabase db push, which forces the local schema to match whatever the linked remote production project contains.
- **C.** supabase start, which wipes the local stack on every boot and replays all migrations against a fresh database.
- **D.** supabase migration new, which regenerates the local schema and writes the corrected state into a fresh file.

> **Answer:** A

### Q14. A bad migration corrupts data at 4 p.m. One builder has only automatic daily backups; another enabled PITR. How do their recovery outcomes differ?

- **A.** Both restore to the same point, but PITR restores finish faster because write-ahead logs replay quicker than snapshots.
- **B.** The daily backup builder loses the whole day back to the last snapshot; the PITR builder can roll back to 3:59 p.m.  ✅
- **C.** The daily backup builder loses nothing if they restore before midnight; PITR only helps after the snapshot rotates.
- **D.** The PITR builder loses less data but must rebuild Storage manually, while daily backups include Storage objects too.

> **Answer:** B

### Q15. A builder's app needs to point at local, staging, or production depending on where it runs. Per this module, how should the app switch between environments?

- **A.** Through a code branch per environment, so the staging branch hardcodes the staging keys and merging promotes them onward.
- **B.** Through a runtime check on the request domain, so the app selects the right Supabase project from the incoming URL.
- **C.** Through one shared set of API keys across all three projects, so the app connects wherever the CLI last linked it.
- **D.** Through configuration: each environment has its own project, API keys, and env vars, and code is never edited to switch.  ✅

> **Answer:** D

### Q16. A builder asks why their AI keeps writing schema changes as timestamped SQL files in the repo instead of just applying them directly. What do those migration files actually provide?

- **A.** They are required by Supabase before any remote change is allowed, since the dashboard rejects unversioned SQL edits on principle.
- **B.** They serve as documentation for human reviewers only, since the CLI applies schema changes from its own saved state.
- **C.** They are automatic backups of the schema, letting you restore database contents from any point in the file history.
- **D.** Each one is a versioned SQL file describing one schema change, applied in order so every environment rebuilds identically.  ✅

> **Answer:** D

### Q17. Before onboarding real tenants, a builder wants proof that the RLS policies from Module 3 actually isolate tenants from each other. What makes a staging project able to provide that proof?

- **A.** Seed data with dozens of fake tenants and users in multiple roles, so cross-tenant access gets exercised against policies.  ✅
- **B.** Enabling PITR on staging, since the recovery log records any query that crosses a tenant boundary during the tests.
- **C.** Running supabase db diff on staging, which reports every policy that fails to reference the tenant id column properly.
- **D.** Copying production API keys into staging, since RLS policies only evaluate correctly under production credentials.

> **Answer:** A

### Q18. A builder shipping to real users has never opened the Backups section of the Supabase dashboard. According to this module, when and why should they check it?

- **A.** During an incident, since backup status only matters at restore time and the dashboard always lists live snapshots.
- **B.** Only after upgrading plans, since backup settings reset on tier changes and need reconfiguring after each upgrade.
- **C.** Now, before any incident: confirm daily backups exist, enable PITR when needed, and learn where restores are triggered.  ✅
- **D.** Never, since backups are fully automatic on all tiers and the CLI is the supported path for triggering any restore.

> **Answer:** C

### Q19. A builder's AI wrote a migration, tested it locally, and applied it to staging. Before promoting the change to production, what does the module's four-step workflow require?

- **A.** Take a manual pg_dump of staging, since that staging snapshot is what actually gets promoted into production.
- **B.** Reset the local stack, since local and staging must be rebuilt together before production accepts the change.
- **C.** Open a Git branch so branching can spin up a preview database of production for one final full rehearsal.
- **D.** Verify the migration behaved correctly on staging against realistic data, then promote it to production.  ✅

> **Answer:** D

### Q20. A builder wants to run destructive schema experiments with zero risk to any remote project or customer data. Which setup does the module recommend for this kind of work?

- **A.** The staging project, since it is the designated experiment space and remote projects restore instantly from snapshots.
- **B.** The local environment: supabase start runs the full stack in Docker on their machine, away from every remote project.  ✅
- **C.** A second production project kept unlinked from the CLI, so destructive statements cannot reach the linked project.
- **D.** Branching on the production project, since preview branches absorb destructive changes without touching live rows.

> **Answer:** B

### Q21. A builder's AI scripted a nightly pg_dump to S3 six months ago, but nobody has ever attempted a restore from those dumps. What does the module say about this setup?

- **A.** Test a restore at least once, since an unverified dump may prove unusable exactly when the business depends on it.  ✅
- **B.** The setup is complete, since pg_dump output is standard Postgres and restores are guaranteed to work when needed.
- **C.** Switch to daily dashboard backups instead, since manual dumps become redundant once a project reaches the Pro plan.
- **D.** Reduce the dumps to weekly, since nightly copies of a growing database will quickly exhaust an S3 storage budget.

> **Answer:** A

### Q22. A builder prototyped straight on production with zero users and nothing bad happened. Now the same app serves 50 paying tenants. Why does the module call that same habit reckless now?

- **A.** Supabase throttles schema changes on projects with heavy traffic, so production migrations start timing out badly.
- **B.** Every experiment now happens on live customer data, so the first serious mistake becomes a customer-facing incident.  ✅
- **C.** RLS policies stop applying while schema changes run, so every migration briefly exposes data across all the tenants.
- **D.** Plan limits cap the number of migrations per day on busy projects, so untested changes burn through scarce deploys.

> **Answer:** B

### Q23. A builder is starting a schema change and wants their AI to create the versioned file first, before any SQL touches a live database. Which CLI command begins this workflow?

- **A.** supabase db push, which opens an editable buffer of remote schema changes and saves it as a migration on exit.
- **B.** supabase start, which prompts for a migration name and scaffolds the file before booting the local Docker stack.
- **C.** supabase db reset, which rolls the schema forward and records the resulting difference as a new migration file.
- **D.** supabase migration new, which creates a fresh timestamped migration file in the repo for the change to live in.  ✅

> **Answer:** D

### Q24. A builder's schema has changed heavily since Module 3, but staging still loads the original seed.sql and tests keep passing suspiciously easily. What does the module advise about the seed file?

- **A.** Freeze the seed file permanently, since a stable baseline is what keeps test results comparable across releases.
- **B.** Delete the seed file and test on empty tables, since passing with no data proves the schema itself remains sound.
- **C.** Rebuild the seed file whenever the schema changes, so staging keeps exercising realistic data and tests stay honest.  ✅
- **D.** Replace seeding with a nightly copy of production records, since real data is the only trustworthy test input.

> **Answer:** C

### Q25. Which statement best captures the governing principle of Module 6, Backups and Environments?

- **A.** Production incidents are unavoidable at scale, so the goal is fast incident response rather than prevention up front.
- **B.** Protection is built before the disaster: untested SQL stays away from live data, and recovery is in place in advance.  ✅
- **C.** AI agents can be trusted with production access once their migrations have passed a single successful staging run.
- **D.** Backups make environment separation optional, since any mistake on production can simply be restored afterward.

> **Answer:** B


---
_Take it in the browser: https://the-faction.mn.co/posts/106187857_
