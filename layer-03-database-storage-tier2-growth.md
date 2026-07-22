# Layer 3 of 13 — Database & Storage
**Tier 2 — Growth** | Matt Murphy Builder Certification Series

> *Builds on Tier 1 (Solopreneur). Assumes those concepts and tools are already understood.*

---

## What It Covers

Keeping a growing database organized, fast, and safe as data and users increase. The challenge
shifts from "does it store things?" to "does it stay fast, organized, and recoverable as the app
grows?"

**Core goal:** You can manage schema changes, optimize queries, handle file storage, and
maintain reliable backups as the app scales.

---

## Key Concepts

**Migrations** — A controlled, planned change to the database structure (new column, renamed
table, changed type), instead of editing a live spreadsheet while people are using it. Without
migrations, database changes are risky guesswork.

**Indexes** — Like the index in the back of a book: look a value up instead of scanning every
row. Without indexes on commonly searched columns, the database gets slower as it grows; AI
often forgets to add them.

**File storage** — Databases are for structured data, not large files. Photos/PDFs belong in a
purpose-built file storage service (Supabase Storage, S3); the database stores a link, not the
file itself. Files stored directly in the database make everything slow.

**Backups and recovery** — Automated daily backups are table stakes, but an untested restore
isn't a backup, it's a hope — actually test restoring from one.

**Seeding and test data** — Sample data (fake users, orders, products) loaded for dev/test.
Without it, you're always testing against an empty database, which hides real-world problems
like slow queries on large datasets.

---

## Toolkit (adds to Tier 1)

- **Migration tools (Prisma Migrate, Drizzle Kit)** — controlled, versioned schema changes
- **File storage (Supabase Storage, AWS S3)** — purpose-built systems for uploaded files
- **Database monitoring (Supabase dashboard, PgHero)** — query performance, slow queries, table sizes
- **Backup automation (built into Supabase, RDS)** — scheduled snapshots, restore to any point in time

---

## Common Pitfalls

- Never looking at the actual data — trusting AI set it up correctly without opening a database viewer to check
- Backups that were never tested with an actual restore
- Storing files directly in the database instead of a file storage service
- No indexes — fine at 50 test records, a 30-second query at 50,000 real ones
- No unique constraints — duplicate accounts with the same email pile up over time
- Making schema changes directly on the production database instead of via migrations

---

## Tier 2 Self-Assessment Checklist

- [ ] Can you describe your data structure to AI and get the right tables/relationships?
- [ ] Have you opened a database viewer and checked types, relationships, constraints yourself?
- [ ] Does the database prevent duplicate records where they shouldn't exist?
- [ ] If the database vanished right now, could you restore it from a backup?
- [ ] Are uploaded files in a file storage service, not the database?
- [ ] Can you describe what happens to related data when a record is deleted?
- [ ] Do you know how to check if queries are fast enough, and what to do if not?

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
duplicates shouldn't exist (like duplicate email addresses or order numbers)?
Indexes: Are commonly searched and filtered columns indexed for fast lookups,
especially as data grows?
File storage: Are uploaded files (images, documents, videos) stored in a
proper file storage service instead of directly in the database?
Backups: Is there an automated backup system in place, and has a restore been
tested successfully?
Give me an overall score out of 6 and list the top 3 things to fix first.
```

---

## Certification pathway

Associate Builder = all 13 layers at Tier 1. Certified Builder = all 13 layers at Tier 1 + Tier 2.
MADE Certified = all 39 tier exams + capstone. 80% to pass each exam, 24-hour retake cooldown.
