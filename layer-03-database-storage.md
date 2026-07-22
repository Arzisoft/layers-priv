# Layer 3 of 13 — Database & Storage
**Tier 1 — Solopreneur** | Matt Murphy Builder Certification Series

> *Storing Your Data So It Doesn't Get Lost*

---

## What It Covers

Relational databases (PostgreSQL), schema design, table relationships, constraints, indexes, file storage, and backups.

**Core goal:** You can describe your data model to AI and get a well-structured schema — and you understand enough to verify it's correct.

---

## Key Concepts

**Relational database (PostgreSQL)** — Data lives in tables (rows + columns). Tables relate to each other via foreign keys. Postgres is the standard for serious apps — battle-tested, free, scales well.

**Schema design** — Every table needs a clear purpose. Name tables as plural nouns (`users`, `orders`, `products`). Each row = one thing. Don't put two kinds of things in one table.

**SQL vs NoSQL** — SQL (Postgres, MySQL): structured, relational, ACID-compliant. NoSQL (MongoDB, Firebase): flexible documents, great for prototypes. For most production apps: SQL wins.

**Table relationships** — One user has many orders (one-to-many). Products can be in many orders and orders can have many products (many-to-many, via a join table).

**Constraints** — Rules enforced by the database: `NOT NULL` (field required), `UNIQUE` (no duplicates), `FOREIGN KEY` (no orphaned records). Constraints catch bad data before it lands.

**Indexes** — Speeds up queries on columns you search/sort by. Add an index on `user_id`, `email`, `created_at`. Without them, queries scan every row.

**File storage** — Don't store files (images, PDFs) in the database. Use S3, Supabase Storage, or Cloudflare R2. Store the file URL in the database.

**Migrations** — Version-controlled database changes. Never edit a live schema by hand. Every change is a migration file that can be run, reviewed, and rolled back.

---

## Toolkit

- **Prisma** (Node.js) or **Eloquent** (Laravel) — ORM to talk to Postgres from code
- **pgAdmin / DBeaver** — GUI to browse your database directly
- **S3 / Supabase Storage / Cloudflare R2** — file storage
- **Automated backups** — turn on from day one, test restore monthly

---

## Common Pitfalls

- Storing everything in one giant table ("God table")
- No foreign key constraints — orphaned records pile up
- Indexing nothing, then wondering why queries are slow
- Storing files in the database as blobs
- Editing the schema directly in production (always use migrations)
- Never testing a backup restore

---

## Tier 1 Self-Assessment Checklist

- [ ] Can you describe your data model with a simple diagram?
- [ ] Does every table have a primary key and appropriate constraints?
- [ ] Are foreign key relationships defined in the schema?
- [ ] Are indexes on the columns you filter/sort by most?
- [ ] Are files stored in object storage (not the database)?
- [ ] Do schema changes go through migrations, not manual edits?
- [ ] Are automated backups running and have you tested a restore?

---

## AI Audit Prompt (copy into your AI tool)

```
Review my database schema and check the following. Pass or fail with a specific example:
1. Normalization: Is data structured in separate related tables, or duplicated across rows?
2. Constraints: Do tables have NOT NULL, UNIQUE, and FOREIGN KEY constraints where needed?
3. Indexes: Are there indexes on columns used in WHERE clauses, JOINs, and ORDER BY?
4. File storage: Are files stored in object storage (not as blobs in the database)?
5. Migrations: Are all schema changes managed through migration files?
6. Backups: Are automated backups configured and has a restore been tested?

Give me a score out of 6 and the top 3 things to fix first.
```
