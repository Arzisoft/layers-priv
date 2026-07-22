# Layer 3 of 13 — Database & Storage
**Tier 3 — Enterprise** | Matt Murphy Builder Certification Series

> *Builds on Tiers 1-2 (Solopreneur + Growth). Assumes those concepts and tools are already understood.*

---

## What It Covers

Running a data operation at enterprise scale. At Tier 3, you're the person responsible for the
entire data layer — multiple databases may serve different purposes, data loss is not an
option, compliance requirements dictate how data is stored and accessed. The job is
architecture and governance.

**Core goal:** You can run a data operation at enterprise scale — overseeing database
replication, sharding strategies, data warehousing, compliance-grade auditing, and disaster
recovery across a platform that can't afford to lose data.

---

## Key Concepts

**Read replicas (spreading the load)** — A copy of the database that handles read-only
requests while the primary database handles writes, spreading the workload so the database
doesn't get overwhelmed during high traffic — multiple copies of a popular reference book in a
library so more people can look things up at once.

**Database sharding (splitting data across servers)** — When a single database server can't
handle all the data, sharding splits it across multiple servers — customers A-M on one server,
N-Z on another. This allows almost unlimited growth but adds complexity; knowing when it's
necessary and what trade-offs it creates is the Tier 3 judgment call.

**Data warehousing and analytics** — The production database is optimized for fast reads and
writes during normal app usage. A data warehouse is a separate system optimized for complex
analytical queries across huge amounts of historical data ("what were sales trends over the
last 3 years by region?"). These two systems serve different purposes and should stay separate.

**Compliance and data governance** — Enterprise applications often face legal requirements
about where data lives geographically (data residency), how long it's kept (retention
policies), who can access it (audit trails), and how it's deleted when requested (right to be
forgotten). Not optional — auditable, with legal consequences for failing.

**Disaster recovery and high availability** — At enterprise scale, the database needs a plan for
every type of failure: hardware crashes, network outages, an entire data center going offline.
High availability means the database keeps running through failures; disaster recovery means
everything can be restored from scratch if the worst happens. These plans need to be tested,
not just documented.

---

## Toolkit (adds to Tier 2)

- **Managed database clusters (AWS RDS, Supabase Pro, PlanetScale)** — handle replication, automatic failover, and scaling so a single server failure doesn't take down the app
- **Data warehouse (BigQuery, Snowflake, Redshift)** — separate analytical databases optimized for complex queries across massive datasets without slowing down production
- **Data pipeline tools (dbt, Fivetran)** — move and transform data between the production database and the data warehouse on a schedule, keeping analytics up to date
- **Compliance and audit tools (AWS CloudTrail, database audit logs)** — track every data access and change for compliance reporting: who accessed what, when, and why

---

## Certification Exam Topics

- **Replication strategy** — Can you evaluate when your database needs read replicas and how to configure them to handle peak traffic?
- **Sharding decisions** — Can you assess when a database should be sharded, what sharding key to use, and what complications it creates?
- **Analytics architecture** — Can you identify when analytics queries should be moved to a data warehouse instead of running against the production database?
- **Compliance evaluation** — Can you verify that your data storage meets residency, retention, and access-control requirements for your jurisdiction?
- **Disaster recovery planning** — Can you evaluate whether your disaster recovery plan actually works, including failover time, data loss tolerance, and restoration procedures?
- **Connection pooling and resource management** — Can you identify when your application is overwhelming the database with too many simultaneous connections?
- **Data lifecycle management** — Can you evaluate policies for archiving old data, purging expired records, and managing storage costs at scale?
- **Cross-region deployment** — Can you assess the trade-offs of replicating data across geographic regions for performance and compliance?

---

## Common Pitfalls

- Never looking at the actual data — trusting AI set up the database correctly without opening a database viewer to check for duplicate records, missing relationships, or wrong data types
- No backups, or backups that have never been tested with an actual restore
- Storing files directly in the database instead of a file storage service — the database gets huge and slow
- Not thinking about what happens when data grows — fine at 50 test records, a 30-second query at 50,000 real ones without indexes
- Letting AI create tables without unique constraints — duplicate accounts pile up over time
- Making schema changes directly on the production database instead of via migrations

---

## Tier 3 Self-Assessment Checklist

- [ ] Can you describe your app's data structure to AI clearly enough that it creates the right tables and relationships?
- [ ] Have you actually opened a database viewer and looked at the data AI created, checking for correct types, relationships, and constraints?
- [ ] Does your database prevent duplicate records where they shouldn't exist (like two accounts with the same email)?
- [ ] If you deleted your database right now, could you restore it from a backup?
- [ ] Are uploaded files (photos, documents) stored in a file storage service, not directly in the database?
- [ ] Can you describe what happens to related data when a record is deleted (like what happens to orders when a customer is removed)?
- [ ] Do you know how to check whether your database queries are fast enough, and what to do if they're not?

---

## AI Audit Prompt (copy into your AI tool)

```
Review my app's database and storage setup and check the following. For each
one, tell me pass or fail with a specific example:
Schema design: Are my tables logically organized with appropriate data types,
required fields, and clear naming conventions?
Relationships: Are related tables properly connected with foreign keys, and
are there rules for what happens when a parent record is deleted?
Unique constraints: Are there constraints preventing duplicate records where
duplicates shouldn't exist (like duplicate email addresses or duplicate order
numbers)?
Indexes: Are commonly searched and filtered columns indexed for fast lookups,
especially as data grows?
File storage: Are uploaded files (images, documents, videos) stored in a
proper file storage service instead of directly in the database?
Backups: Is there an automated backup system in place, and has a restore been
tested successfully?
Give me an overall score out of 6 and list the top 3 things to fix first.
```

---

## What's Next

Once you've gone through this kit and can answer "yes" to the self-assessment checklist,
you're ready for the Layer 3 certification exam at your target tier.

The best way to prepare: build something real. Pick a project that needs to store data, even a
simple one like a task tracker or a customer directory, and go through the full loop. Describe
your data to AI. Check the schema it creates. Look at the actual data in a viewer. Test what
happens when you delete records. Fix the gaps. Ship it. Every mistake caught during building is
exactly what the exam tests.

---

## Certification pathway

Associate Builder = all 13 layers at Tier 1. Certified Builder = all 13 layers at Tier 1 + Tier 2.
MADE Certified = all 39 tier exams + capstone. 80% to pass each exam, 24-hour retake cooldown.
