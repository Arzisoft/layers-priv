---
course: "The Frontier"
module: "Module 3: Long-Term Memory: Persistent Storage Patterns"
lesson: "Module 3: Long-Term Memory: Persistent Storage Patterns — Study Guide"
type: "course_lesson"
post_id: 107155301
space_id: 24391596
source: "https://the-faction.mn.co/posts/107155301"
updated: "2026-09-10T19:34:50Z"
---

# Module 3: Long-Term Memory: Persistent Storage Patterns — Study Guide

# Agent Memory Systems

### T8 The Frontier | Module 3 Study Guide

## Module 3: Long-Term Memory: Persistent Storage Patterns

> Direct AI to build the persistent storage layer where agent memory actually lives, chosen by access pattern instead of by hype.

## Why This Matters

Short-term memory dies with the session. Everything durable needs a home outside the window, and the home you pick determines what your agent can remember cheaply, quickly, and reliably. Builders who choose storage by fashion end up with vector databases holding data that wanted to be a table.

## Core Concepts

**Storage follows access pattern.** The first question is never "which database is best." It is "how will the agent ask for this data later?" Exact lookups, filtered queries, and similarity searches are different access patterns, and each has a natural store.

**Relational tables for structured facts.** Client records, preferences, task history, and anything with known fields belongs in Postgres tables. You get exact retrieval, filtering, constraints, and updates. Most agent memory is this, and builders underestimate how far plain tables go.

**Key-value stores for direct lookups.** When the agent always fetches state by a known key, like session ID or user ID, a key-value shape is the natural fit. In your stack that is usually still a Postgres table with a key column, or a JSONB blob keyed by ID; a dedicated store like Redis is a later optimization.

**Vector stores for meaning-based recall.** When the agent must find memories similar to the current situation without knowing exact keywords, you need embeddings and a vector store. With pgvector, Postgres does this inside the same database that holds your tables.

**Memory schemas are data modeling for agents.** A usable memory record carries more than content: type (episodic, semantic, procedural), source, timestamp, subject, and confidence. Schema design decides whether Module 4's retrieval has anything solid to work with.

**One database first.** Supabase Postgres with pgvector covers relational, key-value, and vector patterns in one place, with one backup story and one access model. Splitting storage across services is a scale decision, made on evidence.

## How It Works

Directing AI to build a long-term layer runs in this order:

1. Inventory what persists: the durable facts, events, and procedures identified at session close.
1. For each item, name the access pattern: fetched by ID, filtered by field, or found by similarity.
1. Map patterns to stores: tables for structure, keyed rows or JSONB for lookups, pgvector columns for similarity.
1. Design the schema: a memories table typically carries id, agent_id, subject, type, content, source, created_at, updated_at, and an embedding column where needed.
1. Wire the write path from session close and the read paths the agent will use, then verify round trips with real data.

## Directing AI

1. "Here is everything my agent must persist. For each item, classify the access pattern: exact key, filtered query, or similarity search."
1. "Design a Supabase schema for agent memory with episodic, semantic, and procedural types, including source and timestamp on every record."
1. "Implement the write path that saves durable facts at session close into the memories table, with upserts for facts that change."
1. "Add pgvector to this Supabase project and create an embedding column and index on the memories table for similarity recall."
1. "Review this schema and flag anything stored as a vector that would be better served by a plain table lookup, and the reverse."

## Common Mistakes

1. **Vector-first thinking.** Embedding everything because agents feel like an AI problem. Most memory reads are exact lookups; tables serve them better and cheaper.
1. **Schemaless dumping.** Throwing JSON blobs into one column with no type, source, or timestamp. Writing succeeds; retrieval starves.
1. **Splitting storage too early.** Adding Redis and a dedicated vector service on day one triples operational surface before any measured need exists.
1. **No update path for facts.** Semantic facts change. Insert-only designs accumulate contradictory records with no way to tell current from stale.
1. **Ignoring the subject field.** Memories without a subject, like a client or project reference, cannot be scoped, so every query returns everything.
1. **Designing schemas without retrieval in mind.** If you cannot write the query that gets a memory back out, the schema is not finished.

## Real-World Application

A builder's research agent stores everything it learns as embedded text chunks in a vector service, and simple questions like "what is this client's plan tier?" return fuzzy paragraphs instead of the answer. The builder directs AI to inventory access patterns: ninety percent of reads turn out to be exact or filtered lookups. The rebuild lands on one Supabase project: a clients table, a memories table with type, subject, source, and timestamp, and pgvector columns only for the research notes that need similarity recall. Lookups become instant and exact, the vector service subscription gets cancelled, and retrieval quality jumps because each read now hits the store shaped for it.

## Decision Framework

- **Will the agent fetch this by a known ID or key?** A keyed table row; no embeddings involved.
- **Will it filter by fields, like all memories about client X since March?** A relational table with indexed columns.
- **Will it search by meaning without knowing keywords?** Embeddings in pgvector.
- **Is it structured but flexible, like arbitrary preferences?** JSONB in Postgres keeps schema freedom with query power.
- **Does the fact get updated over time?** Design an upsert path with updated_at, not an append-only log.
- **Is scale forcing specialization?** Only split to Redis or a dedicated vector service on measured evidence.

## Tool and Platform Notes

Supabase is the default: managed Postgres, pgvector included, row-level security, and a clean API your agent can call. Direct AI to enable the pgvector extension and build indexes; you specify the access patterns and judge the results. Redis is a measured-need addition for hot lookups. Dedicated vector services like Pinecone earn consideration at real scale, when embedding count and query volume outgrow pgvector comfortably.

## Key Takeaways

- Choose storage by access pattern: exact, filtered, or similarity; never by fashion.
- Plain Postgres tables carry most agent memory; vectors serve the meaning-based slice.
- A memory record needs type, subject, source, and timestamp to be retrievable and trustworthy.
- Facts that change need update paths; append-only semantic memory breeds contradictions.
- One Supabase project first; split storage only when measurement demands it.

## What's Next

Module 4 makes the stored memory useful: retrieval, indexing, embedding-based search, and the scoring strategies that decide which memories deserve a place in the window.

## Exam Prep Notes

Focus on matching data to stores by access pattern, and on what belongs in a memory schema and why each field matters. Know when pgvector is justified versus a plain table, what JSONB buys you, and the one-database-first discipline. Expect scenarios diagnosing bad storage choices: vector-first designs, schemaless dumps, missing update paths, and premature splitting.

---

Matt Murphy AI | The Faction Group LLC | mattmurphy.ai

---
_Source: https://the-faction.mn.co/posts/107155301_
