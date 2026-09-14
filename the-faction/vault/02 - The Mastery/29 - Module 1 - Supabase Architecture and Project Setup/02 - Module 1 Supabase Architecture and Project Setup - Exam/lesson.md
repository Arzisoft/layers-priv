---
course: "The Mastery"
module: "Module 1 — Supabase Architecture and Project Setup"
lesson: "Module 1: Supabase Architecture and Project Setup — Exam"
type: "course_quiz"
post_id: 106187026
space_id: 24191170
source: "https://the-faction.mn.co/posts/106187026"
updated: "2026-08-21T15:19:43Z"
---

# Module 1: Supabase Architecture and Project Setup — Exam

> Exam for **Module 1 — Supabase Architecture and Project Setup** (The Mastery) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. A builder starting a 50 tenant SaaS asks their AI what Supabase actually is before scaffolding the backend. Which description should the builder accept as accurate?

- **A.** A proprietary managed database engine that stores data in its own closed format, which you must export and convert to leave the platform.
- **B.** A hosted document store similar to Firebase, where auth and storage are the core and the database layer is an optional add on service.
- **C.** A black box backend service that hides its data layer, exposing only an API so builders never interact with the database directly.
- **D.** Standard Postgres with auth, storage, realtime, edge functions, and an auto generated API layered around the core relational database.  ✅

> **Answer:** D

### Q2. A builder reviewing an AI built client portal sees the anon key shipped in the frontend bundle and flags it as a leak. What actually makes the anon key acceptable in client code?

- **A.** The anon key is rotated automatically by Supabase on every deploy, so any copy a visitor extracts from the bundle expires and stops working.
- **B.** The anon key only grants read access to public tables, so the worst a visitor can do is view data that was already meant to be public.
- **C.** The anon key is safe in the frontend only because Row Level Security guards the data behind it, not because the key itself is harmless.  ✅
- **D.** The anon key is encrypted inside the JavaScript bundle at build time, so visitors cannot recover a usable credential from it.

> **Answer:** C

### Q3. An AI scaffolds a marketplace with file uploads and places the service role key in a Next.js client component. Where does that key actually belong?

- **A.** On servers only, never in browser code or a committed repo, because it bypasses every security rule and grants full database access.  ✅
- **B.** In the frontend alongside the anon key, since Row Level Security policies still filter whatever queries the service role key runs.
- **C.** In any file inside the project as long as the repository is private, since private repositories cannot leak credentials to visitors.
- **D.** In the browser during development only, provided the builder swaps it for the anon key before the app finally deploys to production users.

> **Answer:** A

### Q4. A builder tests a query in the dashboard SQL editor and it returns rows, but the same query fails for logged in users of the client portal. What explains the difference?

- **A.** The SQL editor runs with elevated privileges, so the Row Level Security policies that block real users never apply to editor queries.  ✅
- **B.** The dashboard editor targets a separate replica database, so its results routinely drift from what the production app can actually see.
- **C.** The app is using the service role key, which enforces stricter policies than the anon key the SQL editor uses for its queries.
- **D.** The SQL editor caches results from earlier sessions, so the rows it displays may no longer exist by the time app users run the query.

> **Answer:** A

### Q5. A builder wants their AI to develop a client portal without touching any hosted project at all. Which CLI command runs the entire Supabase stack locally?

- **A.** supabase db push, which pulls the hosted schema down and boots a matching local database inside a managed Docker container for testing.
- **B.** supabase link, which mirrors the hosted project onto the builder's machine and keeps both copies synchronized during development.
- **C.** supabase db diff, which snapshots the hosted stack and replays it locally so changes can be tested against a copy of the data.
- **D.** supabase start, which spins up the full stack, including Postgres, auth, and storage, in Docker containers on the local machine.  ✅

> **Answer:** D

### Q6. After the AI adds tables to the local database for a 50 tenant SaaS, the builder wants those changes captured as reviewable files in the repo. Which command does that?

- **A.** supabase start, which watches the running local database and writes every schema change into a timestamped file automatically as you work.
- **B.** supabase db diff, which compares the local database against existing migrations and writes the changes out as a new migration file.  ✅
- **C.** supabase link, which exports the local schema to the hosted project so the dashboard records each change there for later review.
- **D.** supabase db push, which serializes the local schema into the repository before uploading anything to the hosted environment.

> **Answer:** B

### Q7. A builder has migrations proven locally and wants them applied to the hosted staging project for the marketplace. Which workflow applies them correctly?

- **A.** Running supabase start with the staging project ref as an argument so the local stack connects to and updates the hosted database.
- **B.** Running supabase db diff against staging, which detects the gap between environments and applies the missing changes automatically.
- **C.** Running supabase db push, which applies the versioned migration files in the repo to the linked hosted staging project's database.  ✅
- **D.** Editing the staging schema in the dashboard SQL editor, then running supabase db diff afterward to record what was changed.

> **Answer:** C

### Q8. A builder setting up environments for a role based client portal asks their AI for the standard structure. Which arrangement matches a production grade setup?

- **A.** A single hosted project with separate schemas for dev, staging, and production, so all environments share one set of keys and settings.
- **B.** Local development plus production only, with the dashboard serving as the staging layer where changes are reviewed before release.
- **C.** Local CLI development, a hosted staging project mirroring production, and a production project that receives only proven migrations.  ✅
- **D.** Three hosted projects that all point at the same underlying Postgres instance, separated by environment variables in the frontend.

> **Answer:** C

### Q9. A builder is tempted to let AI apply schema experiments straight to the live 50 tenant SaaS database to move faster. What is the core reason to refuse?

- **A.** Schema changes should never be tested on live data, because a bad change becomes a live fire incident affecting every tenant at once.  ✅
- **B.** Supabase blocks schema changes on production projects by default, so the AI's experiments would silently fail to apply anyway.
- **C.** Production databases run a hardened Postgres build where DDL statements execute slowly, so experiments would degrade performance for users.
- **D.** The dashboard only permits schema edits on staging projects, so experiments must first be routed through the SQL editor there.

> **Answer:** A

### Q10. Reviewing an AI scaffolded marketplace, a builder finds the production URL and keys pasted directly into the config file. What should the setup look like instead?

- **A.** Keys committed to the repo but wrapped in an encrypted config file that the deployment pipeline decrypts automatically at release time.
- **B.** A single shared .env file checked into the repo so every environment and every teammate reads identical connection settings.
- **C.** A gitignored .env file per environment holding that environment's URL and keys, loaded through environment variables at runtime.  ✅
- **D.** Keys stored only in the dashboard settings page, with the app fetching them from the Supabase management API on every startup.

> **Answer:** C

### Q11. A builder asks where the real definition of their SaaS schema should live so any environment can be rebuilt and AI changes reviewed. What is the answer?

- **A.** In the production database itself, since it is the live environment and every other environment should be cloned directly from it.
- **B.** In the dashboard table editor, which keeps a visual history of edits that the team can consult when rebuilding an environment.
- **C.** In a shared SQL document the AI updates after each change, kept alongside the code as an informal record of schema decisions.
- **D.** In versioned migration files committed to the repository; a schema change that is not captured in a migration does not really exist.  ✅

> **Answer:** D

### Q12. Before building on an AI scaffolded Supabase project, a builder runs a structural review. Which finding should make the builder stop and fix the setup first?

- **A.** The .env files are listed in .gitignore, forcing teammates to obtain the URL and keys through a channel outside the repository.
- **B.** The service role key appears in a client side file, and the schema exists only in the hosted dashboard with no migration files.  ✅
- **C.** The scaffold created three separate hosted projects, which triples the surfaces the builder must keep configured and in sync.
- **D.** The AI generated migration files carry timestamps in their names, making the folder harder to scan than plainly named files.

> **Answer:** B

### Q13. To save setup time, a builder has one Supabase project serving as dev, staging, and production for their client portal. What is the concrete risk?

- **A.** Supabase throttles projects that mix workloads, so combined traffic from testing and real users will hit rate limits much sooner.
- **B.** A bad migration or experiment lands directly on real users with zero warning, because there is no safe place to test changes.  ✅
- **C.** The anon key and service role key cannot be separated within one project, so client code is forced to use elevated credentials.
- **D.** Dashboard logs mingle test and production events, which mostly creates noise but does not put any live user data in danger.

> **Answer:** B

### Q14. A builder asks how the dashboard should fit into a professional workflow for the 50 tenant SaaS. What is the right role for it?

- **A.** An admin console for inspecting settings, data, and logs, treated as read mostly, with schema changes made through migrations instead.  ✅
- **B.** The primary development surface, since its table editor and SQL editor are faster than writing migration files through the CLI workflow.
- **C.** A deployment tool, where reviewed schema changes are applied to each environment by hand after being tested locally in Docker.
- **D.** A staging replacement, since its elevated privileges let builders preview exactly what real users will see once RLS is enabled.

> **Answer:** A

### Q15. A builder discovers their AI committed the service role key to a public repo for the marketplace app two days ago. What is the right response?

- **A.** Delete the commit from history and force push, since removing the file from the repository also invalidates any copies already made.
- **B.** Leave it in place but enable Row Level Security, since RLS policies will now filter whatever the exposed key tries to access.
- **C.** Rotate the key immediately, move the new key into server side environment variables, and confirm every .env file is gitignored.  ✅
- **D.** Switch the app to the anon key going forward and keep the old service role key active so existing integrations do not break.

> **Answer:** C

### Q16. A builder's AI needs to run migrations and connect serious database tooling to the staging project. Which access surface is meant for that job?

- **A.** Direct Postgres access through the project's connection string, the surface that migrations and external tooling are meant to use.  ✅
- **B.** The dashboard SQL editor, since it already runs with elevated privileges and can execute any statement the tooling would send.
- **C.** The auto generated REST API called with the service role key, which exposes every table that the migration tooling needs to modify.
- **D.** The realtime layer, which streams schema changes to connected tools so they can apply migrations as change events arrive live.

> **Answer:** A

### Q17. A builder ships a marketplace fast by letting AI write everything against the production database from day one. What has this setup actually created?

- **A.** A situation where every experiment risks live data, and once real users arrive there is no longer any safe place to test anything.  ✅
- **B.** A lean architecture that stays valid until launch day, when a staging project can be cloned from production in a single click.
- **C.** A minor tooling gap, since the dashboard's built in rollback feature can undo any schema change that goes wrong in production.
- **D.** An acceptable tradeoff, because Supabase automatically snapshots production before every schema change the AI applies to it.

> **Answer:** A

### Q18. A client asks a builder whether choosing Supabase locks their portal's data into a proprietary platform. What should the builder answer?

- **A.** The data is stored in a custom engine, but Supabase provides an official export tool that converts it to Postgres format on demand.
- **B.** The database is standard Postgres, so the data stays portable and standard Postgres skills and tooling carry over to it directly.  ✅
- **C.** Only the auth and storage layers are proprietary; the database is open but its auto generated API cannot be replicated elsewhere.
- **D.** Lock in is avoided only if the builder skips Supabase auth, storage, and realtime and uses the platform purely as hosted Postgres.

> **Answer:** B

### Q19. A builder inherits an AI scaffolded SaaS project and runs an audit prompt against it. How should that audit be structured to be safe and useful?

- **A.** The AI reports findings first, marked PASS, WARN, or FAIL with one line fixes, and waits for approval before changing anything.  ✅
- **B.** The AI fixes every issue it finds immediately and then summarizes what changed, so the project is clean by the end of one pass.
- **C.** The AI limits itself to the dashboard settings pages, since codebase level checks require production credentials to complete.
- **D.** The AI regenerates the scaffold from scratch, since auditing an existing setup takes longer than rebuilding it correctly would.

> **Answer:** A

### Q20. During review, a builder finds a table on staging that was added through the dashboard and appears in no migration file. How should this be handled?

- **A.** Leave it alone, since staging exists for experiments and the table will be recreated naturally whenever production needs it.
- **B.** Copy the table to production through the dashboard as well, so at least the two hosted environments stay consistent with each other.
- **C.** Capture it as a versioned migration file in the repo, because a schema change that is not in a migration does not really exist.  ✅
- **D.** Delete the table immediately, since anything created outside the CLI is untrusted and cannot be incorporated into the workflow.

> **Answer:** C

### Q21. A builder skips installing the Supabase CLI and lets AI make all database changes against hosted projects. What does this cost the builder?

- **A.** Nothing significant, because the dashboard records a full history of schema changes that can be replayed into any environment later.
- **B.** The AI's database changes become invisible until they hit a live environment, with no local run and no migration files to review.  ✅
- **C.** Access to edge functions and realtime, since those layers of the platform can only be enabled through the local CLI tooling.
- **D.** Only speed, since hosted projects apply schema changes more slowly than a local Docker stack running on the builder's machine.

> **Answer:** B

### Q22. A builder has the local stack running and migrations written, and now wants push commands to target the hosted staging project. What connects the two?

- **A.** Copying the staging connection string into the frontend .env file, which the CLI reads to decide where migrations are sent.
- **B.** Running supabase start with the staging URL, which registers the hosted project as the destination for all future pushes.
- **C.** Exporting the local schema from Docker and importing it through the staging dashboard, which pairs the projects automatically.
- **D.** Running supabase link with the staging project ref, which ties the local project to that hosted environment for CLI commands.  ✅

> **Answer:** D

### Q23. A builder wonders why the course insists every AI schema change become a migration file when dashboard edits feel faster. What do migrations make possible?

- **A.** They let Supabase bill more accurately, since hosted projects meter schema operations differently when applied through the CLI.
- **B.** They make the dashboard read only, which prevents teammates from making any further changes to hosted environments by hand.
- **C.** They speed up queries, because Postgres optimizes tables that were created through migration files rather than the table editor.
- **D.** They let you rebuild any environment from scratch, review the AI's database changes like code, and roll changes forward safely.  ✅

> **Answer:** D

### Q24. A builder is writing a reusable scaffolding prompt so their AI structures every new Supabase project correctly. What should the prompt demand?

- **A.** Dashboard first setup, a single hosted project to keep costs down, and keys stored in a shared config file in the repository.
- **B.** CLI first setup, migrations committed to the repo, three separate environments, and all keys loaded from environment variables.  ✅
- **C.** Production first setup, so real infrastructure exists from day one, with staging and local copies cloned after the launch succeeds.
- **D.** Frontend first setup, deferring all backend structure until the UI is proven, with the AI free to choose keys and environments.

> **Answer:** B

### Q25. Which statement best captures the governing principle of Module 1, Supabase Architecture and Project Setup?

- **A.** Speed is the point of Supabase, so a builder should ship on the hosted dashboard first and add structure once users complain.
- **B.** Security comes entirely from hiding keys, so a builder who never leaks credentials can safely skip environments and migration files.
- **C.** AI makes setup decisions better than builders do, so the correct posture is to accept scaffolds as generated and review them later.
- **D.** Understand the architecture and impose disciplined environments, keys, and migrations early, so speed never breaks the app later.  ✅

> **Answer:** D


---
_Take it in the browser: https://the-faction.mn.co/posts/106187026_
