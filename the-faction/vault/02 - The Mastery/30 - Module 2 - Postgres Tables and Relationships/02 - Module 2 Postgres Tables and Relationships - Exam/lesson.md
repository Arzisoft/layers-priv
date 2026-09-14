---
course: "The Mastery"
module: "Module 2 — Postgres Tables and Relationships"
lesson: "Module 2: Postgres Tables and Relationships — Exam"
type: "course_quiz"
post_id: 106187203
space_id: 24191170
source: "https://the-faction.mn.co/posts/106187203"
updated: "2026-08-21T15:19:50Z"
---

# Module 2: Postgres Tables and Relationships — Exam

> Exam for **Module 2 — Postgres Tables and Relationships** (The Mastery) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. You are reviewing an AI-built schema for your 50-tenant SaaS and notice the invoices table has no tenant_id foreign key. Why is this the most dangerous omission in the schema?

- **A.** The invoices table will fail to join with the tenants table, so every dashboard query returns an error immediately
- **B.** Module 3's row level security policies will have no column to filter on, leaving every tenant's invoices exposed  ✅
- **C.** Postgres will reject all inserts into invoices, because every table is required to declare at least one foreign key
- **D.** Billing totals will be calculated incorrectly because invoice rows cannot be grouped without a tenant reference

> **Answer:** B

### Q2. Reviewing an AI-generated schema for your marketplace, you see listings.price stored as float8 and created_at stored as text. What do you direct AI to change?

- **A.** Use numeric for price and timestamptz for the timestamp, since floats drift on money and text blocks time queries  ✅
- **B.** Keep float8 for price since Postgres handles rounding automatically, but change created_at to a plain date column
- **C.** Use integer cents for price and keep the text timestamps, because string dates are easier for app code to parse
- **D.** Use jsonb for both fields so the schema stays flexible while the app decides how to format prices and dates at render time

> **Answer:** A

### Q3. Your AI proposes sequential integer IDs for a client-facing bookings table. Per the module, why is the Supabase standard a uuid primary key defaulting to gen_random_uuid()?

- **A.** Sequential integers run out of values quickly at scale, while uuid columns store an effectively unlimited range of keys
- **B.** uuid primary keys are indexed much faster than integers, so lookups on client-facing tables return in less time
- **C.** Postgres cannot enforce foreign keys against integer primary keys once tables pass a few million rows in size
- **D.** Sequential IDs are guessable, letting users enumerate other records, while random uuids stay unguessable to clients  ✅

> **Answer:** D

### Q4. Auditing an AI schema for your marketplace, you find listings.seller_id is a nullable text column instead of a NOT NULL foreign key to sellers(id). What is the actual risk?

- **A.** Queries joining listings to sellers will run far slower, since text-based joins are never supported by Postgres indexes
- **B.** The table editor will refuse to display the listings table because it cannot resolve the seller relationship visually
- **C.** The database happily accepts orphaned listings pointing at sellers that do not exist, since nothing enforces the link  ✅
- **D.** AI-generated app code will crash on every insert because Supabase client libraries require typed foreign key columns

> **Answer:** C

### Q5. Your SaaS must keep invoice history even after a tenant account is removed, for compliance review. AI wrote invoices.tenant_id with on delete cascade. What do you direct?

- **A.** Change it to on delete restrict so a tenant with invoices cannot be deleted until the records are handled deliberately  ✅
- **B.** Keep cascade but add a trigger that copies deleted invoices into a jsonb archive column on the tenants table itself
- **C.** Remove the foreign key entirely so invoice rows always survive tenant deletion without Postgres blocking anything
- **D.** Switch the column to nullable text so deletions succeed and the app decides later how to handle the old invoices

> **Answer:** A

### Q6. Your client portal's memberships table stores role as free text. You worry that six months in you will find Admin, admin, and ADMIN mixed together. What do you direct AI to add?

- **A.** A jsonb roles column with a documented list of allowed values that AI-generated app code validates before insert
- **B.** A check constraint like check (role in ('admin', 'member', 'viewer')) so the database rejects invented role values  ✅
- **C.** A separate audit table logging every role change so inconsistent values can be found and cleaned in a nightly job
- **D.** Client-side validation in the signup form, since role values only enter the system through the app's own screens

> **Answer:** B

### Q7. You direct AI to model one tenant having many projects in your 50-tenant SaaS. Where does the foreign key belong in this one-to-many relationship?

- **A.** On tenants, as a projects_id column referencing the projects table so each tenant row points at its own projects
- **B.** On both tables, so tenants and projects each reference the other and the relationship works from either direction
- **C.** In a junction table named tenant_projects, since Postgres requires a separate table whenever two entities relate
- **D.** On projects, as a tenant_id column referencing tenants(id), because the foreign key lives on the many side  ✅

> **Answer:** D

### Q8. Your marketplace needs listings in multiple categories and categories holding many listings. AI proposes a category_ids uuid array on listings. What do you direct instead?

- **A.** A listing_categories junction table with listing_id and category_id and a composite unique constraint on the pair  ✅
- **B.** Keep the array but add a check constraint limiting its length, since bounded arrays act like junction tables
- **C.** A categories jsonb column on listings so category data stays flexible and avoids the cost of an extra join
- **D.** A category_id foreign key on listings plus a listing_id foreign key on categories to cover both sides of the relationship

> **Answer:** A

### Q9. A teammate asks why the AI's uuid array approach to listing categories is a red flag when it looks simpler than a junction table. What is the core problem?

- **A.** Postgres arrays are capped at a small fixed number of elements, so popular listings would eventually hit the limit
- **B.** Array columns cannot be read by Supabase client libraries, so the frontend would never receive the category data
- **C.** Arrays force every category lookup through a sequential scan, and Postgres has no way to index array contents
- **D.** Arrays skip referential integrity and break the indexing and row level security patterns later modules depend on  ✅

> **Answer:** D

### Q10. Marketplace search is slow because every result joins thousands of reviews just to show a count. When is caching review_count on listings the right call, per the module?

- **A.** Never, because normalized schemas are always correct and any denormalized column will corrupt production data
- **B.** Only after moving reviews into a jsonb column on listings, so the count and raw data live in the very same row
- **C.** Now, because a real hot query demands it, and the duplication should be documented as a deliberate choice  ✅
- **D.** At the start of every project, since duplicating counts early avoids the need for painful migrations later on

> **Answer:** C

### Q11. Reviewing an AI schema, you notice customer email duplicated across orders, invoices, and tickets before any query has ever run slow. What is the problem here?

- **A.** This is premature denormalization: each duplicate copy is a future inconsistency with no hot query to justify it  ✅
- **B.** Nothing yet, since duplicating small text fields is standard and only large columns cause update anomalies
- **C.** Emails should be duplicated but stored as jsonb, so one update can patch every copy across the three tables
- **D.** The duplication is fine, but the columns must share a unique constraint so Postgres keeps the copies in sync

> **Answer:** A

### Q12. A teammate hotfixes a production column by clicking it into the Supabase table editor. Staging now behaves differently. Why does the module call this the wrong move?

- **A.** Editor changes live untracked in one project's database, so they cannot be reviewed, replayed on staging, or rolled back  ✅
- **B.** The table editor writes weaker column types than SQL does, so dashboard-created columns underperform in production
- **C.** Editor changes bypass Postgres constraints entirely, so the new column silently accepts data violating the rules
- **D.** Supabase locks any table edited through the dashboard, so future migration files will fail until support manually unlocks them

> **Answer:** A

### Q13. You are prototyping a feature idea in a scratch Supabase project before committing to anything. What is the table editor's proper role in your workflow?

- **A.** It is your system of record: production schemas should live in the dashboard where every teammate can view them
- **B.** Prototyping and inspection: sanity check what exists there, while every change that matters ships as a migration  ✅
- **C.** It should never be opened at all, since the module requires every database interaction to go through the CLI
- **D.** Emergencies only: use it when a production incident demands a schema change faster than a migration file allows

> **Answer:** B

### Q14. Your AI has drafted DDL for three new tables, and you want the schema reproducible across staging and production. Per the module toolkit, what is the right workflow?

- **A.** Paste the DDL into the table editor on each environment in turn, checking the schema visualizer carefully after every paste
- **B.** Run the DDL once in production's SQL editor, then export a database backup that staging can restore from later
- **C.** Run the DDL in the SQL editor, then persist it as migration files with supabase migration new and supabase db push  ✅
- **D.** Store the DDL in a shared document so any teammate can re-run it by hand whenever a new environment spins up

> **Answer:** C

### Q15. After AI adds several tables, you open Supabase's schema visualizer and see no line connecting orders to customers. Per the module, what does that missing line mean?

- **A.** A rendering quirk: the visualizer only draws lines for one-to-many links created through the table editor itself
- **B.** A missing constraint: the foreign key you expected was never created, so the relationship is not being enforced  ✅
- **C.** A performance safeguard: Supabase hides foreign key lines on tables that have not yet received any row inserts
- **D.** A naming issue: the visualizer needs both columns to share the exact same name before it draws the connection

> **Answer:** B

### Q16. Before approving AI's schema for your SaaS, you want to run the review practice the module recommends. What does query-first review actually involve?

- **A.** Asking AI to generate an entity relationship diagram and confirming every table from the spec appears somewhere on the diagram
- **B.** Running the schema on staging for a week of synthetic traffic and approving it if no query exceeds latency budgets
- **C.** Listing your app's five most common queries and walking each through the tables, failing any missing join path or column  ✅
- **D.** Counting foreign keys per table against a checklist, since a well-linked schema serves whatever queries arrive later

> **Answer:** C

### Q17. AI hands you a clean entity diagram for your SaaS and the schema looks complete. Why does the module warn against approving on that basis alone?

- **A.** Diagrams age quickly: any schema change made after approval invalidates the diagram and the review along with it
- **B.** A diagram shows what exists, not what gets queried: a model that cannot serve real access patterns still fails  ✅
- **C.** Entity diagrams hide data types, and type errors are the only schema mistakes that truly matter in production
- **D.** AI-generated diagrams routinely omit tables at random, so a complete-looking diagram is evidence of hidden gaps

> **Answer:** B

### Q18. You are coaching a new builder who assumes AI's Supabase schemas are correct because they run without errors. What is the module's core warning?

- **A.** AI generates plausible schemas by default, not correct ones, so your review is the quality gate before shipping  ✅
- **B.** AI schemas fail only on data types, so a quick scan of the column types is enough to certify a generated model
- **C.** AI cannot create foreign keys at all, so every relationship must be added by hand after generation completes
- **D.** Schemas that run are correct by definition, but AI often produces SQL syntax errors that must be caught first

> **Answer:** A

### Q19. A founder wants to skip schema review and fix any problems later once the app has traction. Per the module, what does fixing schema after real user data actually cost?

- **A.** Nothing significant, since Postgres migrations apply instantly and existing rows are rewritten automatically in place
- **B.** A full rebuild, because Supabase projects cannot alter tables once production rows have been written into them
- **C.** Only downtime, since the data itself is unaffected and the fix is the same one prompt it costs when caught in review today
- **D.** Migrations under pressure and backfill scripts, versus the single prompt it costs when caught in review today  ✅

> **Answer:** D

### Q20. Your client portal lets users join client workspaces. AI's memberships table has user_id and client_id, but users keep getting added to the same client twice. What is missing?

- **A.** A uuid primary key on memberships, since duplicate rows only occur in tables lacking a proper primary key column
- **B.** A composite unique constraint on (user_id, client_id) so the database rejects a second membership for the pair  ✅
- **C.** A check constraint on user_id verifying the value exists in users, which also blocks duplicate rows appearing
- **D.** Application-level deduplication in the signup flow, since two-column uniqueness must be enforced in app code

> **Answer:** B

### Q21. AI-built app code has a bug that sometimes inserts orders without an amount. You want protection that holds even when generated code misbehaves. What does the module recommend?

- **A.** Constraints like NOT NULL run inside the database itself, so they reject bad rows even when app code has bugs  ✅
- **B.** More thorough AI code review, since database constraints only fire when queries come through the SQL editor
- **C.** A nightly cleanup job that finds null amounts and backfills them from logs before reports run each morning
- **D.** Wrapping every insert in a try catch block so failed writes retry until the amount field arrives populated

> **Answer:** A

### Q22. Your app stores per-listing metadata that varies wildly by category: dimensions for furniture, sizes for clothing. AI proposes twenty nullable columns. What do you direct?

- **A.** Create a separate table per category so each metadata shape gets its own strictly typed set of dedicated columns
- **B.** Keep the nullable columns, since sparse columns cost nothing and keep every attribute individually constrainable
- **C.** Use a jsonb metadata column, the module's type for flexible data whose shape varies too much for fixed columns  ✅
- **D.** Store the metadata as a delimited text blob the app parses, keeping schema small and parsing logic in the code

> **Answer:** C

### Q23. In your SaaS, comments belong to projects and are worthless once the parent project is gone. What delete behavior do you direct AI to set on comments.project_id?

- **A.** on delete restrict, since the module says restrict is always the safe default and cascade should never ship
- **B.** No foreign key action at all, letting orphaned comments accumulate harmlessly since nothing will query them
- **C.** on delete restrict, plus a scheduled job that finds comments whose projects are missing and removes them weekly
- **D.** on delete cascade, chosen deliberately because dependent comments should be removed with their parent project  ✅

> **Answer:** D

### Q24. Planning your build order, a teammate suggests treating schema design as a low-stakes step you can revisit anytime. Why does the module rank schema mistakes as the most expensive?

- **A.** Schema work takes the most engineering hours of any module, so mistakes there waste more time than any others
- **B.** Postgres charges more compute for altered tables, so late schema changes raise the project's hosting bill sharply
- **C.** Supabase support must approve schema rollbacks, so late fixes wait on an external team before they can ship
- **D.** Everything else in the stack depends on schema: row level security, auth, and storage all sit on these decisions  ✅

> **Answer:** D

### Q25. Which statement best captures the governing principle of Module 2, Postgres Tables and Relationships?

- **A.** Let AI own the data model end to end, since modern models produce production schemas that rarely need review
- **B.** Hand-write all SQL yourself, because schema design is the one layer where AI assistance cannot be trusted at all
- **C.** Direct AI toward a model serving your app's real queries, then verify constraints enforce it at the database layer  ✅
- **D.** Prioritize a clean entity diagram above all, since a complete-looking diagram proves the schema will hold up in production

> **Answer:** C


---
_Take it in the browser: https://the-faction.mn.co/posts/106187203_
