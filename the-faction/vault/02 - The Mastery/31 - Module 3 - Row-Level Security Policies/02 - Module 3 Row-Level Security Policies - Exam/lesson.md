---
course: "The Mastery"
module: "Module 3 — Row-Level Security Policies"
lesson: "Module 3: Row-Level Security Policies — Exam"
type: "course_quiz"
post_id: 106187405
space_id: 24191170
source: "https://the-faction.mn.co/posts/106187405"
updated: "2026-08-21T15:19:57Z"
---

# Module 3: Row-Level Security Policies — Exam

> Exam for **Module 3 — Row-Level Security Policies** (The Mastery) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. Your AI scaffolds a profiles table through raw SQL and you ship it with RLS never enabled. A visitor copies the anon key from your frontend bundle. What can they do to that table through the API?

- **A.** Nothing at all, because Supabase blocks anonymous API access to any table until you publish at least one policy for it.
- **B.** Read and write every row, because a table with RLS disabled is fully open to anyone holding your anon key.  ✅
- **C.** Read rows but never modify them, since the anon key is scoped to read only access on unprotected tables.
- **D.** Only query metadata like column names, since row data always requires a signed JWT from a logged in user.

> **Answer:** B

### Q2. You direct your AI to enable RLS on every table in a migration, but it writes no policies at all. Your app's queries now come back empty. What is actually happening?

- **A.** RLS is deny by default, so with no policies every API query returns nothing, which is the safe starting point.  ✅
- **B.** Enabling RLS without policies leaves the table open, since Supabase falls back to permissive access until they exist.
- **C.** The queries error out because enabling RLS requires at least one policy per operation before requests are accepted.
- **D.** The anon key was rotated during the migration, so the client needs fresh credentials before rows return again.

> **Answer:** A

### Q3. Ten tables in your app are locked down. In week six your AI ships a notifications table and the Security Advisor flags it as exposed. Why did this happen?

- **A.** RLS has no inheritance, so every new table starts unprotected and needs RLS enabled in its own migration.  ✅
- **B.** The notifications table inherits RLS from the schema but needs its policies manually copied from another table.
- **C.** Security Advisor flags every new table by default until you dismiss the warning, so it may be a false positive.
- **D.** New tables created by AI tools default to the service_role context, which the Advisor always reports as exposed.

> **Answer:** A

### Q4. Reviewing an AI written policy set, you see USING clauses on some policies and WITH CHECK on others. What is the actual difference between the two clauses?

- **A.** USING applies to authenticated users while WITH CHECK applies only to anonymous visitor requests made with the anon key.
- **B.** USING filters which existing rows an operation can touch, while WITH CHECK validates what new or changed rows contain.  ✅
- **C.** USING is the modern syntax and WITH CHECK is deprecated, so audits should rewrite older policies to use USING.
- **D.** USING runs on the database side while WITH CHECK runs in the client library before the request is ever sent.

> **Answer:** B

### Q5. Your AI writes an INSERT policy for a tasks table but you are not sure it used the right clause. Which clause must an INSERT policy use, and why?

- **A.** USING, because inserts must first check which existing rows in the table the current user is allowed to see.
- **B.** Both USING and WITH CHECK together, since every write operation in Postgres requires the two clauses paired.
- **C.** WITH CHECK, because inserts create new rows and the policy must validate what those incoming rows contain.  ✅
- **D.** Neither clause, because INSERT permissions are handled by column grants rather than row level policy rules.

> **Answer:** C

### Q6. You spot that your AI's UPDATE policy on an invoices table has only a USING clause. A user could exploit this. Why do UPDATE policies need both USING and WITH CHECK?

- **A.** USING alone makes updates read only, so without WITH CHECK the policy silently blocks every write attempt.
- **B.** USING limits which rows can be touched, but only WITH CHECK stops a user rewriting a row into one they cannot own.  ✅
- **C.** Postgres rejects any UPDATE policy missing WITH CHECK, so the migration always fails before it ever reaches production.
- **D.** WITH CHECK adds an index on the updated columns, so leaving it out makes updates crawl once traffic scales.

> **Answer:** B

### Q7. You ask your AI to scope a journal_entries table so each logged in user sees only their own rows. What is the core policy pattern it should produce?

- **A.** A USING clause of true on SELECT, paired with frontend filtering so each user's query requests only their rows.
- **B.** A policy comparing the row's user_id to a user ID string that the client passes along with each API request.
- **C.** A policy checking auth.uid() = user_id, tying row access to the user ID inside the requester's verified JWT.  ✅
- **D.** A separate Postgres database role created per user, with table grants issued individually to each new role.

> **Answer:** C

### Q8. A tester shows they can insert rows into your notes table attributed to another user by sending a chosen user_id. Beyond WITH CHECK, how should the user_id column itself be set up?

- **A.** Make user_id nullable so spoofed values can be discarded, then backfill correct ownership with a nightly job.
- **B.** Store user_id in a separate lookup table that only the frontend writes after it has verified the session locally.
- **C.** Let the client send user_id but validate it in an Edge Function before the row ever reaches the database.
- **D.** Reference auth.users and set it by default to auth.uid() on the server, so the client never supplies the value.  ✅

> **Answer:** D

### Q9. Your 50 tenant SaaS shares one database and tenant 12 just queried tenant 31's invoices. You direct your AI to fix isolation properly. What is the correct multi tenant pattern?

- **A.** Every tenant table carries a tenant_id, and policies verify the requesting auth.uid() belongs to that tenant.  ✅
- **B.** Each tenant gets its own Supabase project, since Postgres cannot safely isolate tenants in one shared database.
- **C.** The frontend appends a tenant filter to every query, and code review ensures no query ships without it.
- **D.** A tenant column on auth.users, with the client switching accounts whenever users move between workspaces.

> **Answer:** A

### Q10. Your AI wrote a membership subquery directly inside a policy on the memberships table itself, and queries now hang. What is the recommended fix from this module?

- **A.** Move the membership check into the client, since policies should never query other tables in any situation.
- **B.** Add USING (true) to the memberships table so the recursive lookup short circuits before it loops forever.
- **C.** Wrap the membership lookup in a security definer function, which avoids recursion and keeps policies fast.  ✅
- **D.** Disable RLS on memberships only, because a table that policies depend on cannot itself be protected by RLS.

> **Answer:** C

### Q11. An AI generated admin dashboard works suspiciously well, and you find it calls Supabase with the service_role key from browser code. Why is this a critical problem?

- **A.** The service_role key bypasses RLS entirely, so anyone lifting it from the browser owns every row you store.  ✅
- **B.** The service_role key expires every 24 hours, so the dashboard will silently break for your admins the next day.
- **C.** Browsers rate limit service_role requests heavily, so the dashboard slows to a crawl as admin usage grows.
- **D.** The service_role key only works server side, so those browser calls fail and show cached, stale results.

> **Answer:** A

### Q12. Your tight user scoped policies work perfectly, but now your own admin dashboard shows zero rows for staff. What is the correct way to restore admin access?

- **A.** Disable RLS on the affected tables during admin sessions, then re enable it once each staff member logs out.
- **B.** Have admins query through the service_role key in the dashboard frontend, since that role bypasses policies.
- **C.** Drop the user scoped policies and rely on the application layer to decide which rows each role may access.
- **D.** Add explicit admin policies that branch on a role column or JWT claim, keeping RLS enabled the entire time.  ✅

> **Answer:** D

### Q13. A security sweep shows your AI enabled RLS on a private messages table but wrote a SELECT policy of USING (true). The RLS checkbox looks green. What is the real situation?

- **A.** The table is secure, because enabling RLS is the real protection and policy conditions only tune query performance.
- **B.** This is RLS theater: the enabled flag passes audits while the bare true condition grants every user every row.  ✅
- **C.** USING (true) is valid shorthand for auth.uid() = user_id, so the policy still scopes rows to their owners.
- **D.** The policy only affects the anon role, so authenticated users still fall back to deny by default behavior.

> **Answer:** B

### Q14. Your AI insists its policy set is correct, and your own account sees the right data. Before shipping, what does this module say makes a policy actually proven?

- **A.** Reading the policy SQL line by line, since careful review by the builder is stronger evidence than test runs.
- **B.** Confirming the Security Advisor shows no warnings, which certifies the policy logic is behaving correctly.
- **C.** Running the app as your own account across every page and confirming each screen loads the expected rows.
- **D.** Impersonating multiple users and proving both directions: user A sees their data and cannot touch user B's.  ✅

> **Answer:** D

### Q15. After your AI locks down a comments table, users can read comments but every attempt to post silently fails. The table has exactly one policy, a SELECT scoped by auth.uid(). Why do writes fail?

- **A.** The SELECT policy's USING clause also gates writes, and its condition evaluates false during insert attempts.
- **B.** Supabase queues writes on newly protected tables until an admin approves the policy set in the dashboard.
- **C.** The auth.uid() function is unavailable during INSERT, so any write under RLS needs a service role proxy.
- **D.** Policies grant one operation each, so with only SELECT covered, deny by default blocks every write attempt.  ✅

> **Answer:** D

### Q16. You just approved a large AI generated migration adding six tables. According to this module's toolkit, what should you check immediately afterward?

- **A.** The Postgres logs, filtering for policy evaluation errors that would show one of the new tables is misconfigured.
- **B.** The API response times on staging, since a latency spike usually reveals a table shipped without an index.
- **C.** The dashboard's Security Advisor and each table's RLS status, which flag any new table that shipped exposed.  ✅
- **D.** The frontend bundle size, since migrations that embed keys bloat the client and can leak your credentials.

> **Answer:** C

### Q17. You keep catching your AI scaffolding beautiful schemas with RLS disabled. The module prescribes a reusable habit to stop this from recurring. What is it?

- **A.** A nightly cron job that drops any table found without policies so exposure can never survive past midnight.
- **B.** Switching the AI to a mode that cannot run DDL, so every table creation goes through your hands instead.
- **C.** A database trigger that blocks table creation unless a policy for all four operations already exists first.
- **D.** A standing RLS prompt block in every AI session: enable RLS on new tables, write all four policy types.  ✅

> **Answer:** D

### Q18. A teammate panics that your Supabase anon key is visible in the shipped frontend bundle and wants an emergency rotation. What does this module say about the situation?

- **A.** It is a genuine leak: the anon key must stay server side and every exposed copy requires an immediate rotation.
- **B.** It is safe because the anon key only works from your app's registered domain and browsers enforce origin.
- **C.** The anon key is designed to ship in frontend code, and RLS policies are what stand between it and your rows.  ✅
- **D.** It only matters at scale, since Supabase throttles anon key traffic too aggressively for abuse to be viable.

> **Answer:** C

### Q19. Your AI scoped every table with auth.uid() = user_id, but in your team SaaS users complain they cannot see rows created by their own teammates. What went wrong?

- **A.** The user_id comparison fails for teammates because auth.uid() returns the team ID rather than the user's ID.
- **B.** Ownership here is per organization, so policies must check tenant membership instead of per user ownership.  ✅
- **C.** The rows were written under the service_role key, which strips user_id values that policies depend upon.
- **D.** Teammates need their own SELECT grants at the Postgres role level before any RLS policy can apply to them.

> **Answer:** B

### Q20. During review you simulate an attack: a user updates their own row but sets user_id to a victim's ID, and it succeeds. Which policy gap allows this ownership transfer trick?

- **A.** The UPDATE policy lacks a WITH CHECK clause, so nothing validates the row's new contents after the change.  ✅
- **B.** The SELECT policy is too broad, letting the attacker read the victim's user_id, which enables the takeover.
- **C.** The DELETE policy is missing, and Postgres treats an unmatched UPDATE as a delete plus a fresh insert.
- **D.** The table lacks a primary key, so RLS cannot track which row identity the update statement is changing.

> **Answer:** A

### Q21. Your AI wrote solid SELECT policies, and reads are properly scoped. Yet users can still create rows attributed to other users. Which pitfall from this module does this match?

- **A.** Recursive policy subqueries, where the insert path loops through a membership check until it times out.
- **B.** Trusting client supplied IDs on INSERT: without WITH CHECK (auth.uid() = user_id), writes go unvalidated.  ✅
- **C.** RLS theater, where a bare true condition on the SELECT policy quietly disables checks on every write path.
- **D.** Missing indexes on user_id, which lets inserts bypass policy evaluation when the planner skips the scan.

> **Answer:** B

### Q22. You want to prove tenant 12 cannot read tenant 31's rows before launch, without building a whole test harness. What does the module's toolkit recommend?

- **A.** Export both tenants' rows to a spreadsheet and manually compare the outputs of the two application accounts.
- **B.** Deploy to production behind a feature flag and watch the logs for any cross tenant reads from real traffic.
- **C.** Use the SQL editor with role impersonation, running queries as anon or specific users to verify policies.  ✅
- **D.** Temporarily disable RLS and diff the results, since equal row counts prove the policies change nothing.

> **Answer:** C

### Q23. You are about to push a Supabase backend to production after weeks of AI assisted building. Per this module, what should you run right before every deploy?

- **A.** A load test with simulated tenants, since policy correctness only shows up under realistic concurrent load.
- **B.** A full database vacuum and reindex, so policy subqueries evaluate against fresh statistics at launch time.
- **C.** A schema diff against the last known good migration, reverting any tables the AI added since the snapshot.
- **D.** The audit prompt template: a full AI driven sweep of RLS status and policy coverage across your schema.  ✅

> **Answer:** D

### Q24. Your team debates when to enable RLS on new tables: at creation, before staging, or right before launch. What timing does this module mandate, and why?

- **A.** In the same migration that creates the table, because any gap leaves it fully open to anyone with the anon key.  ✅
- **B.** Right before launch, since enabling RLS earlier slows development while the schema is still changing daily.
- **C.** Before staging, because RLS only affects hosted environments and local development ignores policies anyway.
- **D.** After the first real users sign up, since policies need actual auth.uid() values to evaluate correctly in practice.

> **Answer:** A

### Q25. Which statement best captures the governing principle of this module on Row-Level Security policies?

- **A.** Every table gets RLS enabled with tested per operation policies, because you are the security reviewer of your backend.  ✅
- **B.** Security belongs in the application layer, with the database kept simple and RLS policies treated as an optional extra fallback.
- **C.** AI generated schemas are trustworthy and safe by default, so the builder's role is limited to spot checking naming conventions.
- **D.** RLS is mainly a performance optimization feature, and its access control benefits matter only for heavily regulated industries.

> **Answer:** A


---
_Take it in the browser: https://the-faction.mn.co/posts/106187405_
