---
course: "The Mastery"
module: "Module 3 — Multi-Tenant Architecture"
lesson: "Module 03: Multi-Tenant Data Architecture — Exam"
type: "course_quiz"
post_id: 103821120
space_id: 24191170
source: "https://the-faction.mn.co/posts/103821120"
updated: "2026-08-21T01:21:34Z"
---

# Module 03: Multi-Tenant Data Architecture — Exam

> Exam for **Module 3 — Multi-Tenant Architecture** (The Mastery) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. Your AI tool created a SaaS app with a 'projects' table. You notice there's no tenant_id column — any query returns projects from all customers. What's the immediate risk?

- **A.** No risk — the app automatically filters results by logged-in user without needing tenant isolation
- **B.** Customer A can see Customer B's projects — there's no data isolation between tenants at all  ✅
- **C.** The table will eventually be too large to query quickly as more tenants add projects
- **D.** Projects don't need tenant isolation because they're considered public data by default in SaaS

> **Answer:** B

### Q2. You enable Row-Level Security on your Supabase database. But when a new developer joins and creates a 'comments' table, they forget to add an RLS policy. What happens to data in that table?

- **A.** RLS automatically applies to new tables so there's no need to configure anything manually
- **B.** The comments table has no access restrictions — anyone can read all comments from all tenants  ✅
- **C.** Supabase blocks all access to any table without RLS policies to prevent unauthorized data access
- **D.** The table inherits its RLS policies from the parent schema so it's already properly protected

> **Answer:** B

### Q3. Your usage table logs API calls per tenant. At month end you count rows for billing but 12 million rows make the query take 45 seconds. What is the fix?

- **A.** Upgrade to a faster database server that can handle the volume of counting queries more efficiently
- **B.** Delete old usage rows regularly to keep the table small enough for fast aggregate queries
- **C.** Maintain a running counter per tenant per billing period — increment on each call instead of counting rows  ✅
- **D.** Run the count query overnight during low-traffic hours when the database has more capacity available

> **Answer:** C

### Q4. You store uploaded files as binary in PostgreSQL. With 500 customers uploading files your database is 85GB and backups take 3 hours. What should change?

- **A.** Upgrade to a larger database instance that can handle the volume of file storage much more effectively
- **B.** Compress the binary data before storing it in the database to reduce the overall storage requirements
- **C.** Store files in a dedicated storage service and keep only the file URL reference in the database  ✅
- **D.** Limit the maximum upload size per tenant to control database growth and storage consumption

> **Answer:** C

### Q5. A customer cancels. Your system runs DELETE WHERE tenant_id and removes all their data. Two days later they want to reactivate but their data is gone. What should you have done?

- **A.** Use soft deletes — mark records as deleted with a timestamp but retain the data for a recovery window  ✅
- **B.** Permanent deletion of all data on cancellation is standard practice and users should expect this
- **C.** Back up the tenant's dataset to a separate archive before permanently deleting their records
- **D.** Deleted data can be recovered from database logs so there's no need for a soft delete mechanism

> **Answer:** A

### Q6. Your projects table has 200,000 rows across 400 tenants. Every query includes WHERE tenant_id but there is no index on that column. Queries slow as data grows. What do you need?

- **A.** The database automatically optimizes frequently used filter patterns without needing manual indexes
- **B.** Index every column in the table to ensure all possible query patterns are covered automatically now
- **C.** Separate each tenant's data into its own database table to avoid the need for any indexes
- **D.** Add a composite index on tenant_id plus the filtered column so queries only scan one tenant's rows  ✅

> **Answer:** D

### Q7. Your RLS policy checks auth.uid() to filter rows. But your API uses a service role key that bypasses RLS for all operations. What is the security impact?

- **A.** Every API request runs with full tenant access — one bug can expose every tenant's data  ✅
- **B.** The service role key is safe to use everywhere because it stays hidden on backend servers
- **C.** RLS still applies to service role queries as long as policies stay enabled on every table
- **D.** There is no impact since the API validates each user's session before running queries

> **Answer:** A

### Q8. Your database migration adds a NOT NULL constraint to an existing column that currently has 3,000 rows with null values. You run the migration in production. What happens?

- **A.** The database automatically fills null values with a sensible default when a constraint is applied
- **B.** The migration fails because existing null values violate the new constraint — backfill data first  ✅
- **C.** NOT NULL constraints only apply to newly inserted rows and do not affect existing data in the table
- **D.** Null values are automatically converted to empty strings when the constraint is added

> **Answer:** B

### Q9. Your tasks table has tenant_id but your comments table only links to tasks via task_id with no tenant_id. Can comments leak across tenants?

- **A.** No — comments automatically inherit tenant isolation from their parent project's security policies
- **B.** Comments are low-risk data that doesn't require the same level of tenant isolation as project data
- **C.** Comments need their own tenant_id column and RLS policy — the join to projects won't protect them  ✅
- **D.** The foreign key relationship to projects provides sufficient isolation for comment records

> **Answer:** C

### Q10. A developer runs ALTER TABLE users ADD COLUMN phone_number TEXT directly on the production database from a SQL console. What is the risk?

- **A.** No risk — adding a nullable column to a production database is a completely safe operation
- **B.** Direct production changes bypass version control, can't be easily rolled back — use migration files  ✅
- **C.** The ALTER TABLE command will lock the table and cause downtime during the entire schema change process
- **D.** Adding columns directly to production is faster and more reliable than using migration file workflows

> **Answer:** B

### Q11. Your backup runs daily at 2am. At 1pm a deployment bug corrupts 6 hours of data. You restore the 2am backup. What happened to data created between 2am and 1pm?

- **A.** Everything written between 2am and 1pm is gone — daily backups alone cannot cover the gap  ✅
- **B.** The restore merges the backup with current data so the morning's records are never lost
- **C.** The database replays its own logs automatically so the morning's data returns after restore
- **D.** Only corrupted rows are lost — the restore keeps every healthy record from that same morning

> **Answer:** A

### Q12. Your test DB has 1 tenant with 20 records and works. After launch 50 tenants with 5,000 records each cause queries to jump from 10ms to 4 seconds. What testing gap caused this?

- **A.** The launch traffic was just too high — no amount of pre-launch testing could catch that
- **B.** The test environment ran a different database engine, which made query plans incomparable
- **C.** Automated unit tests should have caught the slowdown without needing realistic data volumes
- **D.** No load testing with production-scale data — seed realistic tenant volumes before launch  ✅

> **Answer:** D

### Q13. Your schema stores subscription plan as a string in the users table. When you rename basic to starter you must update every row. What schema design avoids this?

- **A.** A plans reference table — users point to a plan row by ID, so a rename touches one record  ✅
- **B.** A database trigger that rewrites old plan names to new ones whenever any row is updated
- **C.** Storing plan names in uppercase so renames become simple find-and-replace operations later
- **D.** Keeping both old and new plan names valid at once so no rows ever actually need updating

> **Answer:** A

### Q14. Your admin panel bypasses RLS so support can view any tenant. A support agent queries the wrong tenant and modifies data. What safeguard is missing?

- **A.** Admin access should not bypass RLS under any circumstances regardless of the use case or situation
- **B.** Admin panels should be built as a separate application with its own dedicated database server
- **C.** Only engineering team members should have any kind of admin access to the production database system
- **D.** Admin queries should log the tenant being accessed, require explicit selection, and be read-only  ✅

> **Answer:** D

### Q15. You store customer billing addresses in your database without encryption. A data breach exposes addresses for all tenants. What should have been in place?

- **A.** Billing addresses aren't sensitive enough to encrypt — they're just standard mailing info
- **B.** Encrypt sensitive fields at the application layer so a database breach doesn't expose tenant data  ✅
- **C.** Database-level encryption handles everything — no need for additional application-layer protections
- **D.** Only encrypt data if you've experienced a breach before — proactive encryption is overly cautious

> **Answer:** B

### Q16. You add a new required column to your tenants table as NOT NULL with no default value. The migration fails on your 500-tenant database. What is the fix?

- **A.** Run the migration again with the --force flag to override the constraint violation and push it through
- **B.** Delete the table and recreate it with the new column included in the original schema definition file
- **C.** Add the column as nullable first, backfill existing rows with valid data, then alter to NOT NULL  ✅
- **D.** NOT NULL columns can't ever be added to tables that already contain existing data rows

> **Answer:** C

### Q17. Your SaaS stores data in the US. A European customer asks about GDPR data residency. You cannot answer because you never planned for data location. What should you have done?

- **A.** Data residency requirements — knowing where data is stored and offering region-specific hosting  ✅
- **B.** GDPR doesn't apply to US companies so data residency isn't a concern for American builders
- **C.** All data should be stored in the EU regardless of customer location to be safe from any regulations now
- **D.** Ask the customer to sign a waiver releasing your platform from any data residency compliance obligations

> **Answer:** A

### Q18. You query SELECT COUNT(*) FROM subscriptions WHERE status = active and get 487. But Stripe shows 502 active subscriptions. What is causing the mismatch?

- **A.** Stripe's subscriber count includes test subscriptions which inflates the number beyond what's accurate
- **B.** The query should count all subscription statuses, not just active ones, to match Stripe's total count
- **C.** Database counts are approximate and aren't meant to be exact matches with external systems
- **D.** Your webhook handler missed some subscription events — your local database is out of sync with Stripe  ✅

> **Answer:** D

### Q19. Your notifications table has no tenant_id — it links to users via user_id. A reporting query joins notifications directly without going through users. What data could leak?

- **A.** No leak — the join through users table enforces tenant isolation on the notifications data automatically
- **B.** Notifications don't contain sensitive data so tenant isolation isn't a concern for that particular table
- **C.** Direct queries on notifications bypass tenant isolation — reports without a user join expose data  ✅
- **D.** The foreign key to users provides sufficient tenant isolation for stored notification records

> **Answer:** C

### Q20. Your schema has grown to 45 tables with no documentation mapping tables to features and no ER diagram. New developers cannot tell which tables are related. What should you create?

- **A.** A weekly walkthrough meeting where senior developers explain the schema to each new hire
- **B.** Schema documentation and an ER diagram mapping tables to features, kept current as it changes  ✅
- **C.** A stricter naming convention alone — well-named tables make extra documentation unnecessary
- **D.** A migration freeze so the schema stops changing while new developers learn the current layouts

> **Answer:** B

### Q21. Your database tracks subscriptions with tenant_id, plan, status, and created_at. A customer upgrades Basic to Pro but you only store the current plan and cannot see history. What is missing?

- **A.** A subscription history or audit log table that records every plan change with accurate timestamps  ✅
- **B.** Historical plan data isn't necessary for a SaaS product and adds unnecessary database complexity
- **C.** Store all historical subscription data in Stripe and query it from their API whenever it's needed
- **D.** Add a 'previous_plan' column to the subscriptions table to track the most recent plan change

> **Answer:** A

### Q22. Your app uses one users table for user data and org membership. A user in two organizations has two rows with the same email but different tenant_ids. What problem does this create?

- **A.** This is the correct architecture — one row per user per org is a standard multi-tenant data pattern
- **B.** The email column should not have a unique constraint because it prevents multi-org participation
- **C.** Users shouldn't be allowed to join multiple organizations so the current structure works correctly
- **D.** Duplicate user records break login, password reset, and profile — separate users and org membership  ✅

> **Answer:** D

### Q23. All tenants share one database. An enterprise customer requires physical data isolation for compliance. Your schema cannot do this. What is the architectural decision?

- **A.** Tell the customer that shared tenancy is secure enough and there's no need for dedicated resources
- **B.** Move all customers to isolated databases to guarantee maximum security for every single tenant
- **C.** Support both shared and isolated tenancy — shared for standard, dedicated database for enterprise  ✅
- **D.** Use schema-level separation within the same database instance to simulate tenant isolation cheaply

> **Answer:** C

### Q24. Your subscription status column accepts any string. In production you find active, Active, ACTIVE, actve (typo), and trail (typo for trial). What database feature prevents this?

- **A.** Application-level validation is sufficient for restricting status values and keeping data consistent
- **B.** String normalization in the API layer before saving the data to the database handles this cleanly
- **C.** A unique constraint on the status column so that each status value can only appear one time total
- **D.** An enum type or check constraint that restricts the column to a defined set of valid status values  ✅

> **Answer:** D

### Q25. Your customer table uses soft deletes with is_deleted flag. Your dashboard query returns both active and deleted customers in the list. What is wrong?

- **A.** The dashboard query is missing a deleted-rows filter — add it or query a filtered view  ✅
- **B.** Soft-deleted customers should stay in every list so staff remember the records still exist
- **C.** The is_deleted flag should be replaced with hard deletes to keep dashboard queries simple
- **D.** The dashboard should show deleted customers in gray instead of filtering them away

> **Answer:** A


---
_Take it in the browser: https://the-faction.mn.co/posts/103821120_
