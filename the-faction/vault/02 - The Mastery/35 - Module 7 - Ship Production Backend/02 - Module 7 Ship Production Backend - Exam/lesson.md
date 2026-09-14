---
course: "The Mastery"
module: "Module 7 — Ship: Production Backend"
lesson: "Module 7: Ship: Production Backend — Exam"
type: "course_quiz"
post_id: 106187990
space_id: 24191170
source: "https://the-faction.mn.co/posts/106187990"
updated: "2026-08-21T15:20:28Z"
---

# Module 7: Ship: Production Backend — Exam

> Exam for **Module 7 — Ship: Production Backend** (The Mastery) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. You are working the go-live checklist on your 50-tenant SaaS the week before launch. Which set of items must all be verified before real users touch the system?

- **A.** RLS on user-facing tables only, auth email confirmations enabled, a public bucket for assets, and a nightly backup job
- **B.** Load testing at ten times expected traffic, a CDN in front of the API, database replication, and a public status page
- **C.** RLS on every table, auth locked to production domains, storage policies locked down, secured env vars, and pooling  ✅
- **D.** TypeScript strict mode, unit test coverage above 80 percent, linted Edge Functions, and pinned dependencies

> **Answer:** C

### Q2. Your AI reports that every table in your 50-tenant SaaS has RLS enabled with policies attached. Before launch you want proof, not a summary. What do you direct it to do?

- **A.** Open each table in the dashboard editor and confirm rows render correctly while logged in as a test tenant account
- **B.** Query pg_tables and pg_policies to list every public table, its RLS status, and each attached policy as evidence  ✅
- **C.** Re-run the schema migration files and confirm they contain enable row level security statements for each table
- **D.** Restate its audit in more detail, table by table, so you can read through the written confirmation carefully

> **Answer:** B

### Q3. During a pre-launch audit of your marketplace, you find one forgotten table, audit_logs, with RLS disabled. Why is this a launch blocker rather than a minor cleanup item?

- **A.** The anon key ships inside your frontend, so anyone can read and write that table straight from the network tab  ✅
- **B.** Supabase blocks API access to tables without RLS by default, so your own app will begin throwing permission errors
- **C.** Audit tables grow quickly, and without RLS the query planner cannot use indexes efficiently on large scans
- **D.** The Security Advisor fails the project, and Supabase support can pause API traffic until the warning is resolved

> **Answer:** A

### Q4. Reviewing auth settings before launching your client portal, you spot http://localhost:3000 still sitting in the redirect allow-list. What is the actual risk of shipping it this way?

- **A.** Users on the production site may bounce to localhost after login and hit a broken page, hurting early conversion
- **B.** An attacker can steer a real user's auth redirect toward a destination they control and capture that session  ✅
- **C.** Development tokens issued to localhost stay valid in production, letting old test accounts reach live tenant data
- **D.** The auth server rejects mixed http and https entries, so production logins will randomly fail for users

> **Answer:** B

### Q5. Your 50-tenant SaaS crawls at 100,000 rows even though staging felt instant. Queries filter by tenant_id under RLS. Where do you direct your AI to add indexes first?

- **A.** Foreign key columns, the columns RLS policies filter by such as tenant_id, and columns in frequent WHERE clauses  ✅
- **B.** Every column on every table, since Postgres ignores indexes it does not need and the storage overhead is negligible at scale
- **C.** Primary key columns across all tables, since Postgres does not create indexes on primary keys automatically
- **D.** Text and JSON columns first, because large data types slow sequential scans down far more than integers do

> **Answer:** A

### Q6. Your AI claims its new index made the slow tenant dashboard query dramatically faster. As the auditor on this launch, what evidence do you require before accepting the claim?

- **A.** EXPLAIN ANALYZE output you read yourself, showing an index scan replacing a sequential scan and lower runtime  ✅
- **B.** The AI's before and after summary of the change, since it has direct access to the database and you do not
- **C.** A screen recording of the staging app loading fast, since perceived speed is the metric users actually feel
- **D.** The migration file containing the CREATE INDEX statement, proving the index now exists on the filtered column as claimed

> **Answer:** A

### Q7. After launch, a traffic spike hits your marketplace and requests start failing with connection errors. Your Edge Functions connect straight to Postgres. What most likely happened?

- **A.** Supabase throttled your anon key after too many requests per minute, rejecting API traffic during the spike
- **B.** RLS policies executed on every row scanned during the spike, locking tables until long queries finished running
- **C.** Postgres ran out of disk IO under the burst and began refusing writes until dashboard metrics settled again
- **D.** Each invocation grabbed its own direct connection, exhausting the Postgres limit and taking the backend down  ✅

> **Answer:** D

### Q8. Your AI suggests routing your serverless frontend through Supavisor in production. What does the pooler actually do for your backend when traffic spikes?

- **A.** It caches frequent query results at the edge, so repeated reads never touch the database during traffic bursts
- **B.** It spins up extra read replicas automatically whenever connection counts climb past your plan's limits
- **C.** It multiplexes many client connections over a few database connections so spikes do not exhaust Postgres  ✅
- **D.** It queues incoming requests and retries failures, smoothing bursts by delaying queries until capacity frees up

> **Answer:** C

### Q9. A week after launch, users report your SaaS freezing at peak hours. You open Supabase to diagnose. Which signals does this module tell you to read?

- **A.** Deploy history and Edge Function cold start counts, since freezes usually trace back to the most recent release you shipped
- **B.** Auth sign-in volume and email delivery rates, since peak hour load is driven by how many users are logging in
- **C.** Database CPU, memory, disk IO, and connection counts, checked against Postgres logs for slow queries and errors  ✅
- **D.** Frontend bundle analytics and browser console errors, since perceived freezes are usually client side rendering

> **Answer:** C

### Q10. Users of your client portal report intermittent permission errors after launch, but your AI insists every policy is correct. Where does this module tell you to look for the truth?

- **A.** The frontend error tracker, since permission errors surface in the browser before they ever reach the database
- **B.** The migration history, comparing each policy file against the schema to confirm they were applied in order
- **C.** The auth settings page, since intermittent permission failures usually come from misconfigured redirect URLs
- **D.** The Postgres logs, which record policy failures and errors so you can see exactly which queries were denied  ✅

> **Answer:** D

### Q11. Launch went smoothly and your team wants to defer alert setup to next sprint. Based on this module, why is shipping with no alerts a real risk rather than a nice-to-have gap?

- **A.** Supabase deletes Postgres logs within a day on lower plans, so without alerts the evidence of failures vanishes
- **B.** Alert rules need weeks of baseline data to tune, so starting late means false alarms through your entire first quarter
- **C.** Without alerts your users become your monitoring, and you learn about outages from angry emails, not dashboards  ✅
- **D.** Unmonitored projects get flagged by the Security Advisor, which can block future deploys until alerting exists

> **Answer:** C

### Q12. Before opening file uploads on your marketplace, you review the storage bucket your AI created. What is the locked-down configuration this module expects before launch?

- **A.** A public bucket with upload size limits and file type restrictions, since validation is what stops abusive uploads at scale
- **B.** Buckets that deny by default, with owner-scoped policies explicitly granting uploads, updates, and deletes to users  ✅
- **C.** A private bucket accessed only through the service role key in frontend code, so no storage policies are required
- **D.** Signed URLs for every read and write, which replace storage policies entirely once expiry times are set short

> **Answer:** B

### Q13. Auditing secrets before go-live, you search the repo and find the service role key referenced in a React component. Why does this single finding block the launch?

- **A.** Service role keys expire every 30 days, so client code using one will silently break after rotation
- **B.** React bundlers strip env vars at build time, so the reference means auth calls are failing silently in production
- **C.** The service role key bypasses RLS entirely, and anything in frontend code ships to every visitor's browser  ✅
- **D.** Mixing anon and service keys in one codebase causes token conflicts that intermittently log users out of the app

> **Answer:** C

### Q14. Your AI just shipped a schema change to your 50-tenant SaaS that adds three new tables. Which built-in dashboard tool does this module say to run right after every change like this?

- **A.** The Security Advisor under Advisors, which flags tables without RLS, permissive policies, and exposed functions  ✅
- **B.** The SQL editor's saved query history, which shows whether the new tables have been queried by the anon role this week
- **C.** The Log Explorer's error view, which lists any policy failures the new tables have generated since the deploy
- **D.** The API docs generator, which confirms the new tables are exposed with correct column types and endpoints

> **Answer:** A

### Q15. Your AI reports all policies are in place on your client portal, and the demo works perfectly. According to this module, what does a passing demo actually prove about security?

- **A.** It proves the happy path and the security model together, since RLS failures would visibly break demo queries in production
- **B.** Almost nothing, because nothing in a passing demo reveals a missing policy, so only a direct audit counts as proof  ✅
- **C.** It proves read paths are secure but not write paths, so you only need to audit INSERT and UPDATE policies now
- **D.** It proves security for the roles exercised in the demo, so testing one user per role completes the full audit

> **Answer:** B

### Q16. Staging felt instant, so your AI wants to skip index work before launching the SaaS. What does this module say about why small tables hide the problem?

- **A.** Staging databases run on faster hardware tiers, so identical queries always benchmark better than production
- **B.** Postgres keeps small tables fully in memory and hides real plans, so EXPLAIN output is meaningless in staging environments
- **C.** Small tables let RLS policies short-circuit early, so policy cost only appears past a million rows per table
- **D.** At production row counts, unindexed RLS filter columns turn every request into a sequential scan of the table  ✅

> **Answer:** D

### Q17. You run the pre-launch audit prompt against your live project and it returns two FAIL items on storage policies. Launch is tomorrow. How does this module say to treat that output?

- **A.** As advisory input to weigh against deadline pressure, since audits are guidance and the demo is passing cleanly
- **B.** As a post-launch backlog item, since storage issues only matter once real users are uploading files
- **C.** As a signal to re-run the audit with a stronger model, since two FAILs in one section suggests a tooling error
- **D.** As a blocking gate: every failed check is a launch blocker, and you do not ship until the fixes are verified  ✅

> **Answer:** D

### Q18. EXPLAIN ANALYZE on your marketplace's order lookup shows a sequential scan joining orders to tenants on tenant_id, a foreign key. What is the module's prescribed fix?

- **A.** Index the foreign key column, since Postgres does not index foreign keys automatically and joins scan without one  ✅
- **B.** Rewrite the join as two separate queries, since RLS policies cannot use indexes across joined tables anyway
- **C.** Denormalize tenant data into the orders table, since joins are the real cost and indexes cannot fix join order problems
- **D.** Increase the connection pool size, since sequential scans are a symptom of queries queueing for connections

> **Answer:** A

### Q19. Final auth review before launching the client portal: Site URL is set and localhost entries are stripped from the allow-list. What else does the module say to confirm in auth configuration?

- **A.** That refresh token rotation is disabled in production, so long-lived sessions survive server restarts cleanly
- **B.** That the anon key was rotated after development, so tokens issued in testing can no longer be replayed
- **C.** That magic links are switched off entirely, since email-based login cannot be locked to a single domain safely
- **D.** That email templates point at production links, so auth emails do not send users to stale development URLs  ✅

> **Answer:** D

### Q20. Your AI is wiring connections for launch: Edge Functions on one side, a long-running migration script on the other. How does this module frame pooler versus direct connections?

- **A.** Everything uses direct connections in production, with the pooler reserved for local development and testing traffic only
- **B.** The app and Edge Functions route through the pooler, and you know when transaction mode applies versus direct  ✅
- **C.** Route reads through the pooler and writes direct, since transaction mode cannot safely handle write traffic
- **D.** Choose per table: high-traffic tables connect through the pooler while low-traffic tables can stay direct

> **Answer:** B

### Q21. A week before launch, you notice the uploads bucket on your marketplace allows public writes. Your AI calls it low priority. What does the module say this misconfiguration becomes?

- **A.** A storage cost spike only, since public writes are rate limited per IP and cannot affect the rest of the backend services
- **B.** A moderation queue problem, since Supabase scans public uploads and quarantines any flagged files automatically
- **C.** An RLS bypass, since files written to public buckets inherit anon access to the tables that reference them
- **D.** A free CDN for strangers, since anyone can push arbitrary files into your bucket and serve them from your project  ✅

> **Answer:** D

### Q22. Dashboard metrics on your SaaS show connection counts pinned at the plan limit while CPU sits low. Requests are timing out. What is the correct read of this data?

- **A.** CPU headroom means the database is healthy, so the timeouts must come from the frontend or network layer
- **B.** The plan limit is undersized for your schema, so the fix is upgrading tiers until counts stop hitting the cap
- **C.** Clients are exhausting direct connections, so traffic should route through the pooler rather than upgrading  ✅
- **D.** Idle sessions are being miscounted by the dashboard, so the graphs need refreshing before drawing conclusions

> **Answer:** C

### Q23. Reviewing pg_policies output from your audit, you see a write policy on the invoices table with USING (true). Why does the audit prompt flag exactly this pattern?

- **A.** It grants the operation on every row to anyone who can reach the API, gutting tenant isolation on that table  ✅
- **B.** USING (true) is invalid syntax on write policies, so Postgres is silently skipping the policy at runtime
- **C.** Boolean literals in policies bypass the query planner, forcing sequential scans on every write to the table at runtime
- **D.** It marks the policy as a temporary placeholder, which Supabase disables automatically after thirty days live

> **Answer:** A

### Q24. Your backend is live and healthy, and you are planning the operations routine for the coming month. What cadence does this module prescribe for dashboard and log checks?

- **A.** Check daily for the first week after launch, then set alerts and move to weekly checks once things are stable  ✅
- **B.** Check hourly for the first month, since most production incidents happen within the first thirty days of going live
- **C.** Check only when users report problems, since dashboards are diagnostic tools rather than routine reading
- **D.** Automate everything on day one and never check manually, since human review adds noise to alert tuning

> **Answer:** A

### Q25. What is the governing principle of Module 7, Ship: Production Backend?

- **A.** Production readiness comes from choosing the right Supabase plan tier, since limits and tooling scale with the price paid
- **B.** You are the auditor: verify every AI claim with evidence, from queries to logs, and refuse to launch until it holds  ✅
- **C.** Ship fast and iterate, because real user traffic reveals gaps faster than any pre-launch checklist ever could
- **D.** Delegate fully to AI, because modern models audit their own work more reliably than a human reviewer can

> **Answer:** B


---
_Take it in the browser: https://the-faction.mn.co/posts/106187990_
