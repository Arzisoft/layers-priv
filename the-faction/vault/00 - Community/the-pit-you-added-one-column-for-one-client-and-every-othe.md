---
space: "The Pit"
author: "Matt Murphy"
post_id: 106195540
reactions: 1
comments: 0
published: "2026-08-22T14:00:05Z"
source: "https://the-faction.mn.co/posts/106195540"
---

# You added one column for one client and every other client's queries slowed down

You added one column for one client and every other client's queries slowed down by 40%. The schema is shared and one custom field polluted the database for every tenant. Today I walk through per-tenant schema extensions that keep the core schema clean, tenant-isolated compute that prevents one client's heavy workloads from degrading everyone else, and tenant-scoped migration paths so one client's evolution never forces a system-wide deployment. If you are building multi-tenant SaaS, this is how you say yes without destroying your product.

**PROMPT:** Direct your AI: "Build a multi-tenant isolation architecture with three components: (1) Per-tenant schema extensions. Design a system where tenant-specific custom fields are stored outside the core database schema. Options: a tenant_extensions table with tenant_id, entity_type, entity_id, and a JSONB data column, or a dedicated extension schema per tenant. The core schema must remain unchanged when a tenant adds custom fields. Custom fields should be queryable and joinable at query time for the requesting tenant only. Build migration scripts that create the extension layer and demonstrate adding a custom field for a single tenant without affecting others. (2) Tenant-isolated compute. Identify all heavy or long-running operations: report generation, data exports, bulk imports, analytics queries. Implement a job queue system where each tenant's heavy workloads run in isolated workers with defined resource limits. A tenant running a million-row export must not affect another tenant's API response times. Implement per-tenant rate limits on expensive operations. (3) Tenant-scoped migrations. Separate the migration system into two tracks: core migrations that affect the shared schema and must be backward-compatible with zero downtime, and tenant migrations that affect only the extension layer for a specific tenant. Build tooling that can run a tenant migration for one tenant without touching any other tenant's data or requiring a system-wide deployment. Log every migration with tenant scope, timestamp, and rollback instructions."

---

## Video transcript

_deepgram auto-captions (Mighty) · 2m23s_

You added one column to your database for one client. Now every other client's queries have slowed down by forty percent. So one client wanted a custom field on every single record and a new column in the shared schema that only they were using. So now every query, every migration, every backup, and every restore carries a custom field that ninety nine percent of the clients never asked for or see. So one client's feature request just became every client's technical debt, and every client is paying for it in performance.

You cannot say no to the revenue. We get it. But you said yes in the wrong way. And now tenant specific schema changes compound with every single release. Here's what tier three multi tenant isolation really looks like.

Step one, per tenant schema extensions without shared schema pollution. A metadata table or JSONB column scoped to a tenant that holds custom fields. The base schema stays clean. Tenant specific data lives in an extension layer that can grow without affecting anyone else. So direct your AI to implement a tenant extension model where custom fields are stored outside the core schema and joined at query time only for the requesting tenant.

That's a win. Number two, tenant isolated compute for heavy or custom workloads. When one tenant runs a report that scans millions of rows, that workload should not be competing for resources with every other tenant in real time. So isolate heavy compute into tenant scoped workers or queues. Direct your AI to implement workload isolation so one tenant's expensive operations cannot degrade the performance for all of the others.

And step three, tenant scoped migration pass. A schema change for one tenant cannot require downtime for all of your tenants. Migrations that affect the extension layer run per tenant. So migrations that affect the core schema are backwards compatible. Direct your AI to build a migration strategy that separates core schema changes from tenant specific changes.

This way, no single tenant's evolution forces a system wide deployment. Say yes to your client, but say it with your architecture. It's the best way to go.


---
_Source: https://the-faction.mn.co/posts/106195540_
