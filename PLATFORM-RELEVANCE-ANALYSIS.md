# Matt Murphy 13-Layer Stack — Relevance to PiWheel AMC Platform
**Prepared for Mahmoud Baassiri | piwheel.com**
*Date: 2026-06-25 | Tier 2 (Growth) rollup added 2026-07-10*

---

## The platform we're building against

| Layer | Reality |
|---|---|
| Hosting | AWS EC2 (existing) |
| Backend | Laravel (PHP) — Tamana owns |
| Frontend | React — team owns |
| Database | AWS RDS Postgres (migrating from Supabase) |
| CI/CD | GitHub → EC2 auto-deploy |
| Mahmoud's scope | AMC data layer: query logic, result schemas, ML pipeline, analysis |
| Scaffold | Next.js/Prisma spec in `projects/amcp-platform/` — design reference only, not what deploys |

---

## Layer-by-layer relevance

### Layer 1 — Frontend Foundations
**Relevance: HIGH** | Team owns the React shell in-house (Sam's design was rejected 2026-06-30)

Since Sam's frontend design was rejected, the team designs and builds the amcp UI in-house — Layer 1 now applies directly, not just to your data contracts. Lina set the bar at analytics/banking-grade, zero AI/shadcn-generic slop, and her IA stays fixed. Every chart still needs a clear data contract (JSON shape, field names) on top of the UI work.

**Tier 2 adds:** a real design system (brand colors, spacing, component rules in one place) so every screen matches Lina's bar instead of drifting session to session; Storybook or equivalent to build/test chart components in isolation before wiring them to live data; Core Web Vitals monitoring once client-facing dashboards are live.

**Your action:** Define response shapes for each chart query in `src/lib/queries/registry.ts`. Establish the amcp design system (tokens, component rules) as its own artifact so the in-house build stays consistent across sessions.

---

### Layer 2 — APIs & Backend Logic
**Relevance: HIGH** | You define what the API returns; Tamana builds the route

AMC data flows: async AMC job → warehouse (RDS) → API endpoint → React chart. You own steps 1-2-3. Every endpoint that serves dashboard data needs:
- A consistent response shape
- The right HTTP status codes (200 for success, 404 for "no data for this period", 500 for AMC failures)
- Never return raw AMC data; always return warehouse data

**Tier 2 adds:** background jobs (AMC workflows already are one — submit, poll, return) and the webhook pattern of notifying instead of polling. Right now nothing pushes a notification when an AMC workflow finishes or fails; that gap is really Layer 12's alerting problem showing up here too.

**Your action:** Define the API contracts for each dashboard endpoint before Tamana builds the routes. The scaffold's `src/app/api/` is the spec.

---

### Layer 3 — Database & Storage
**Relevance: CRITICAL** | This is the core of your work

New tables go into the existing RDS instance (not a new DB, not Neon). Everything Matt teaches here applies directly:
- Schema design for multi-tenant time-series data (`clientId`, `capturedAt` on every table)
- Migrations — no manual schema edits ever
- Indexes on `clientId`, `queryId`, `capturedAt` — the columns you filter by constantly
- The warehouse IS the historical store; AMC only has ~12.5 months, your RDS keeps years

**Critical rule:** All query results are immutable snapshots. Never mutate a `QueryResult`; insert a new one. This is Layer 3 + Layer 13 (recovery) combined.

**Tier 2 adds:** backups that are actually tested (not just enabled) and indexes verified under real data volume, not just the dev sample. Same discipline as Layer 13's "an untested backup is a backup you hope works."

**Your action:** Design the `QueryResult` table schema. Add `clientId` + `capturedAt` indexes. All schema changes via Prisma migrations.

---

### Layer 4 — Auth & Permissions
**Relevance: HIGH** | Multi-tenancy = data isolation is everything

The AMC platform is multi-tenant. Brand A (Swiss Arabian) must never see Brand B's data. Matt's RLS + auth concepts map directly:
- Row-level filtering by `clientId` on every query (even if done in Laravel middleware, not Postgres RLS directly)
- Admin users can see all clients; brand users see only their own
- JWT tokens scoped to a tenant
- The platform will handle auth (Sam/Tamana), but you must ensure every data query you write is `WHERE client_id = :clientId`

**Tier 2 adds:** role-based access (admin vs. brand user) and team-scoped access as more clients onboard beyond Swiss Arabian. This is largely done: RLS Wall 3 is built and proven (FORCE RLS on the 5 tenant tables via a `withTenant` GUC, fail-closed) — the remaining caveat is that production must run as a non-superuser Postgres role for FORCE RLS to actually bind (Neon's default role should be fine, but verify before the next client).

**Your action:** Add `clientId` to the WHERE clause of every SQL template in the query registry. Never return cross-tenant data. Confirm the prod DB role is non-superuser before onboarding client #2.

---

### Layer 5 — Hosting & Deployment
**Relevance: MEDIUM** | Team owns this; you need to know enough to not break it

EC2 + GitHub CI/CD is already running. You don't configure it, but you need to:
- Know the staging URL pattern (ask Sam) before shipping any data layer changes
- Never push directly to main without staging verification
- Your `.env` equivalent: credentials live on the EC2 server, accessed via SSH only — never through Claude Code chat

**Tier 2 adds:** preview deployments and a real rollback path. Confirm the EC2/GitHub pipeline actually supports a one-click revert — Layer 13's recovery runbooks assume this works, don't assume it does until it's been tested.

**Your action:** Get added to the new 2026 AMC repo (ask Sam). Understand the staging deploy pattern before your first code push. Test the rollback path once, don't wait for a bad deploy to find out.

---

### Layer 6 — Cloud & Compute
**Relevance: HIGH** | AMC queries run on AWS compute; costs are real

AMC is async: you submit a SQL workflow, AWS runs it (compute cost), you poll for results. Billing implications:
- Set AWS billing alerts before running production-scale queries
- Don't run full-history re-queries repeatedly — warehouse the result once, read from Postgres after
- AMC Audiences API (when enabled by Rohit/Sai): each audience materialization costs compute
- Dev and prod use different AMC instances (you run AMC/AWS yourself)

**Tier 2 adds:** active cost management, not just alerts — knowing which AMC workflows are the expensive ones and right-sizing how often they re-run as more clients get added.

**Your action:** Set a CloudWatch billing alert on the AWS account. Add a `capturedAt` check before re-running any AMC query ("do we already have data for this period?").

---

### Layer 7 — CI/CD & Version Control
**Relevance: HIGH** | The golden rule: commit before every AI-assisted change

The existing GitHub → EC2 pipeline covers deployment. Your job:
- Commit before any large AI-generated code change (ML pipeline, query registry, schema migrations)
- Feature branches for new AMC query templates; merge to main only after staging verification
- AMC SQL lives in `skills/` and the query registry — this IS your codebase, treat it like one

**Tier 2 adds:** real branch/PR discipline and at least one automated check (test/lint/build) as more people (you, Tamana, Sam) touch the same repo — the informal "commit before AI changes" habit needs to become an enforced branch protection rule once it's not just you.

**Your action:** Get added to the new 2026 AMC repo. Branch-per-feature even for SQL template additions.

---

### Layer 8 — Security & RLS
**Relevance: CRITICAL** | Client data isolation + credential hygiene

Two non-negotiables for the AMC platform:
1. **Tenant isolation** — every SQL query must be `WHERE client_id = :clientId`. Multi-tenant breach = clients seeing each other's purchase data. Legal exposure.
2. **Credential hygiene** — AMC API keys, RDS credentials live on the EC2 `.env` file. Never pass through Claude Code chat. Never commit to GitHub. Sam confirmed: "As long as Claude doesn't have credentials on it."

Also: `user_id` (AMC's internal user identifier) must never appear in any output — AMC clean room rules. Join-only, never surfaced.

**Tier 2 adds:** defense-in-depth and role-based access, not just tenant isolation. This is largely closed already — RLS Wall 3 is built and proven (FORCE RLS, fail-closed via the `withTenant` GUC on all 5 tenant tables), which is the database-layer half of defense-in-depth. The remaining half is making sure the API and frontend layers also check permissions, not just relying on RLS alone.

**Your action:** Audit every SQL template for `WHERE client_id` filter. Verify `.env` is in `.gitignore`. Never put AMC credentials in any prompt or chat.

---

### Layer 9 — Rate Limiting
**Relevance: HIGH** | AMC throttles; AWS bills per execution

AMC has its own rate limits on workflow submission. If the platform lets users trigger re-queries from the dashboard:
- Debounce filter changes (don't re-query AMC on every period selector click — query the warehouse first)
- Rate limit the "run fresh AMC query" button per tenant per day
- Dashboard filters on period/market/segment → query the warehouse, not AMC
- The warehouse-first architecture Matt doesn't teach explicitly, but it's the same principle: check the cache before calling the expensive API

**Tier 2 adds:** quota management across multiple paid services (AMC/AWS compute, any email/monitoring tools added later) as a unified view, not separate silos, once there's more than one client's workflows to track.

**Your action:** The scaffold's architecture already handles this correctly — AMC queries are async jobs, not triggered per page load. Maintain this discipline.

---

### Layer 10 — Caching & CDN
**Relevance: MEDIUM** | Warehouse = your cache layer

The AMC platform's caching model is unusual:
- Static assets (React frontend) → CDN via EC2/Nginx (already handled)
- Dashboard data → NOT cacheable in the traditional sense; data is per-tenant, per-period
- BUT: the warehouse IS the cache. If `capturedAt` data exists for this period: serve from Postgres. Only hit AMC for missing or stale periods.

The `QueryResult` immutable snapshot pattern from the CLAUDE.md is Layer 10 applied to data.

**Tier 2 adds:** tracking cache hit rate on the warehouse-as-cache pattern — how often is a dashboard request actually served from Postgres vs. forced to wait on a fresh AMC workflow. Low hit rate would mean the freshness check isn't working as designed.

**Your action:** Add a "data freshness" check before triggering any AMC workflow: if fresh data exists in the warehouse for the requested period/market, skip AMC and return the warehouse result.

---

### Layer 11 — Load Balancing & Scaling
**Relevance: LOW-MEDIUM now; revisit at 5+ clients**

Single EC2 instance handles current load fine. Things to watch as you grow:
- RDS connection pooling — multiple Laravel workers hitting the same Postgres instance
- AMC async jobs are naturally queue-based (already handling load gracefully)
- When at 5+ concurrent clients running dashboard queries: consider RDS read replica for dashboard reads vs. write path for new query results

**Tier 2 concrete tools for when this comes due:** PgBouncer (or Supabase's pooler) for connection pooling, an RDS read replica for dashboard reads, and health-check-based routing if the platform ever runs more than one app server.

**Your action:** Nothing now. Flag this at client 5. When you do: RDS read replica + connection pooler (PgBouncer).

---

### Layer 12 — Error Tracking & Logs
**Relevance: CRITICAL** | AMC workflows fail silently; you need to know

AMC workflow failures are async and silent by default: you submit a job, poll for "SUCCEEDED" or "FAILED", and if FAILED you get an error code but no notification unless you build one. Without error tracking:
- Client dashboard shows no data; nobody knows why
- Query failed 3 days ago; client has been looking at stale data

You need:
- Structured logs: `clientId`, `queryId`, `workflowId`, `status`, `error`, `timestamp` for every AMC job
- Alerting: if `status = FAILED` on any query, you need a notification — not a user complaint
- Error boundaries in the React dashboard: "Data unavailable for this period" > blank chart

**Tier 2 adds — this is the actual current gap:** structured logging with severity levels, alerting rules that distinguish critical from routine, and (per the support-system build) alerts that actually reach a human. The health monitor was built 2026-07-10, but `MAIL_MODE=mock` means alerts are inert — nothing outside the box is actually watching the box. That's precisely the Tier 2 "alert fatigue vs. silent failure" problem, except right now it's silent failure by default: a critical error would generate a log entry nobody sees. Two corollaries worth keeping in view: a monitor can't depend on what it monitors (a DB-backed monitor can't record that the DB is down), and a monitor running on the box can't tell you the box died.

**Your action:** Wire `MAIL_MODE` to a real channel (email/Slack) before this counts as done, not just built. Define severity levels (critical = client-facing data missing; warning = degraded but working) so alerts don't fire on every routine AMC retry. Add an external, off-box check (uptime ping from outside EC2) so a dead box gets noticed even if its own monitor can't report.

---

### Layer 13 — Availability & Recovery
**Relevance: HIGH** | The warehouse holds months of client data

The RDS instance holds every AMC query result ever captured. If it goes down without backups: months of historical data that cannot be re-fetched (AMC only has ~12.5 months). AWS RDS Automated Backups exist — verify they're enabled, test a restore.

Also:
- EC2 rollback: GitHub history gives you point-in-time rollback via the CI/CD pipeline
- Health check endpoint: `/api/health` that checks DB connectivity + AMC API reachability
- Recovery time for an AMC failure: warehouse still works → dashboard can serve historical data even if live AMC is down

**Tier 2 adds:** tested recovery drills and status-page-style communication, on top of the runbooks that already exist. Runbooks R1-R7 are written (including the IP-keyed lockout gotcha as a known scenario), but a runbook nobody has drilled is the same untested-backup problem as Layer 3 — you find the gaps during a drill or during a real 2am outage, and one of those is much worse. There's also no status page or communication plan yet for "Swiss Arabian's dashboard is down, here's what's happening."

**Your action:** Verify RDS Automated Backups are enabled (daily minimum). Add `/api/health` endpoint that checks Postgres connectivity. Run one actual recovery drill against R1-R7 (not just read them) now that the health monitor exists to observe it. Decide who gets notified and how during an incident, before the first real one.

---

## Priority matrix for the piwheel AMC platform

| Priority | Layer | Why |
|---|---|---|
| 🔴 Do now | L3 Database + L8 Security | Foundation of everything: schema design + tenant isolation. RLS Wall 3 is closed; confirm prod runs non-superuser. |
| 🔴 Do now | L12 Error Tracking | Monitor exists but `MAIL_MODE=mock` — alerts are inert. This is the single biggest gap between "built" and "actually protects a client." |
| 🟡 Before first client | L4 Auth | Multi-tenant data isolation proven end-to-end. |
| 🟡 Before first client | L13 Availability | RDS backup verification + rollback tested. Runbooks R1-R7 written but never drilled — run one before relying on them. |
| 🟡 Before first client | L2 APIs | API contracts defined; consistent response shapes. |
| 🟢 After MVP | L6 Cloud | Billing alerts on AWS; cost-per-query estimates. |
| 🟢 After MVP | L9 Rate Limiting | Debouncing + AMC quota management. |
| 🟢 After MVP | L7 CI/CD | Branch strategy + staging workflow. |
| 🔵 Growth phase | L11 Scaling | Revisit at 5+ clients. |
| 🟢 After MVP | L1 Frontend | Team (not Sam) builds the UI now; needs its own design system to hold Lina's quality bar as it grows. |
| 🔵 Nice to have | L5, L10 | Team owns these; Mahmoud reviews. |

---

## How Matt Murphy's certification maps to your role

You are not a vibecoder building a toy app. You are the data scientist designing the data layer of a production platform. The 13 layers still apply — but your leverage points are different:

| Matt's framing | Mahmoud's framing |
|---|---|
| "Tell AI what protections to build" | "Define the tenant isolation rules in SQL; Tamana implements" |
| "Describe what you need to AI" | "Write the query registry contracts; Tamana builds the API routes" |
| "Set up error tracking" | "Define the AMC workflow log schema; ask Sam to wire Sentry" |
| "Test what users cannot do" | "Test that Swiss Arabian data never leaks into another client's query result" |
| "Commit before AI changes" | "Commit every SQL template + migration before running it on RDS" |

The course teaches you to be a confident supervisor of your AI coding tools. For the AMC platform: **you are the AI's supervisor for the data layer**. Sam and Tamana are the AI's supervisors for the platform shell. The interface between you is the API contract and the schema.

---

## Quick-reference: AI audit prompts to run on the AMC platform

Run these before each milestone:

**L3 + L8 combined (data layer foundation):**
```
Review the AMC platform's database schema. For every table:
1. Is client_id present and indexed?
2. Is capturedAt present on all QueryResult-type tables?
3. Are there migrations for every schema change (no manual edits)?
4. Is RLS or equivalent row-level filtering enforced for every tenant?
Tell me pass/fail per table and list the top 3 risks.
```

**L12 (error tracking for async AMC jobs):**
```
Review the AMC workflow execution path. For each workflow submission:
1. Is the workflowId, clientId, queryId, and status logged?
2. If status = FAILED, does an alert fire?
3. Are AMC error codes captured with enough context to diagnose?
4. Is there an error boundary on each dashboard chart if data is unavailable?
Give me pass/fail and the top 3 logging gaps.
```

**L12 + L13 combined (is the support system actually wired, not just built):**
```
Review the AMCP health monitor and alerting setup end to end:
1. Does MAIL_MODE (or equivalent) point at a real channel, or is it mocked?
2. If the app or its monitor process dies, does anything OUTSIDE the box
   detect it, or does the monitor depend on the thing it's monitoring?
3. Are severity levels defined so critical failures alert immediately and
   routine ones don't cause alert fatigue?
4. For each of runbooks R1-R7: has it ever been drilled, or only read?
Give me pass/fail on each and the single highest-risk gap to close first.
```
