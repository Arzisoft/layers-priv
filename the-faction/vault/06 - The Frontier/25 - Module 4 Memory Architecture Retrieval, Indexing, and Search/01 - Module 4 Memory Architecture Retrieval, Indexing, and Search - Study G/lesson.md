---
course: "The Frontier"
module: "Module 4: Memory Architecture: Retrieval, Indexing, and Search"
lesson: "Module 4: Memory Architecture: Retrieval, Indexing, and Search — Study Guide"
type: "course_lesson"
post_id: 107155312
space_id: 24391596
source: "https://the-faction.mn.co/posts/107155312"
updated: "2026-09-10T19:36:30Z"
---

# Module 4: Memory Architecture: Retrieval, Indexing, and Search — Study Guide

# Agent Memory Systems

### T8 The Frontier | Module 4 Study Guide

## Module 4: Memory Architecture: Retrieval, Indexing, and Search

> Direct AI to build the retrieval layer that finds the right memory at the right moment, because stored memory the agent cannot surface might as well not exist.

## Why This Matters

Storage was the easy half. The hard half is the moment a session starts and your agent must pull the five memories that matter from the five thousand it holds, fast enough not to stall and precise enough not to pollute the window. Retrieval quality is memory quality as far as your users can tell.

## Core Concepts

**Retrieval is selection under a budget.** The window has token space for a handful of memories per turn. Retrieval's job is ranking everything the agent knows and admitting only what earns entry, which makes it a scoring problem, not a fetching problem.

**Embedding-based search.** Content is converted to vectors that place similar meanings near each other. The agent embeds its current situation as a query and pulls the nearest stored memories. This finds conceptual matches keywords miss: "the client is unhappy about timelines" retrieves the delay complaint from March.

**Recency scoring.** Newer memories usually matter more. A recency term decays a memory's score with age, so last week's decision outranks last year's, without deleting anything.

**Relevance plus recency plus importance.** Production scoring blends at least three signals: semantic similarity to the current situation, freshness, and a stored importance weight for memories flagged as critical. Blending prevents any single signal from dominating wrongly.

**Hybrid retrieval.** Semantic search alone misses exact identifiers; keyword and filtered search alone miss paraphrases. Hybrid runs structured filters first, then combines keyword and vector results, typically scoping by subject before ranking by meaning.

**This is RAG applied to memory.** Retrieval-augmented generation grounds responses in fetched documents. A memory system does the same with the agent's own past instead of a document corpus: same embeddings, same indexes, same ranking discipline, different source of truth.

## How It Works

A retrieval pass at the top of an agent turn:

1. Build the query: embed the current situation, and extract hard filters like subject and memory type.
1. Filter first: narrow by subject, type, or date range in SQL, so ranking runs over candidates, not the whole store.
1. Score candidates: combine vector similarity, recency decay, and importance weight into one number.
1. Admit under budget: take the top results that fit the token allowance reserved for memory.
1. Format for the window: each admitted memory enters as a compact statement with source and date, not a raw record dump.

Indexes make step 2 and 3 fast: standard B-tree indexes on subject and timestamps, a vector index on embeddings. Without them retrieval works in the demo and times out in production.

## Directing AI

1. "Implement embedding-based retrieval over the memories table in pgvector: embed the query, return top 10 by cosine similarity, scoped to this subject."
1. "Add a scoring function that blends similarity, recency decay with a 30-day half-life, and the importance column; expose the weights as config."
1. "Build hybrid retrieval: SQL filters on subject and type first, then merge keyword and vector rankings; explain your merging strategy."
1. "Given this retrieval log where the right memory ranked eleventh, adjust the balance between similarity and recency and show before-and-after rankings."
1. "Create the indexes this retrieval path needs, including the pgvector index, and demonstrate query time before and after on realistic volume."

## Common Mistakes

1. **Ranking the whole store.** Skipping the filter step means scoring every memory ever written, which is slow and drowns the ranker in irrelevant candidates.
1. **Similarity as the only signal.** Pure semantic search happily returns a vivid but ancient memory over yesterday's decision.
1. **Ignoring exact identifiers.** Invoice numbers, emails, and names deserve keyword or filtered matching; embeddings mangle them.
1. **No token budget for memory.** Admitting fifteen memories per turn crowds out the actual conversation, undoing Context Engineering.
1. **Raw records in the window.** Dumping JSON rows into context wastes tokens and confuses the model; format memories as compact statements.
1. **Unindexed vector columns.** pgvector without an index does a full scan per query; it works quietly until volume arrives.

## Real-World Application

A builder's project-management agent holds three thousand memories across forty client projects. Users complain it keeps citing stale decisions from months back. The retrieval log shows pure similarity search: old memories about the same topics outrank recent revisions. The builder directs AI to add subject filtering, a recency decay with a 30-day half-life, and an importance weight for memories marked as standing decisions, blended into one score with configurable weights. The agent now cites the current revision first, references the old one only when asked about history, and answers faster because ranking runs over one project's candidates instead of forty projects' worth.

## Decision Framework

- **Does the query carry an exact identifier?** Use filtered or keyword matching; skip embeddings for that part.
- **Is the need conceptual, stated in different words than stored?** Embedding search earns its keep.
- **Are both in play?** Hybrid: filter by subject and type, then rank by meaning.
- **Are stale results beating fresh ones?** Raise the recency weight or shorten the half-life.
- **Are critical memories losing to chatty ones?** Add or raise importance weighting.
- **Is retrieval slow at volume?** Check indexes first, filter scope second, and only then consider heavier infrastructure.

## Tool and Platform Notes

pgvector in Supabase handles embedding storage, cosine similarity, and vector indexes in the same Postgres that holds your filters, which is why hybrid retrieval stays one query away. Use a current embedding model from your provider and store its name with each embedding, so re-embedding after model changes is trackable. Dedicated vector services add value at scale but add a network hop to every hybrid query; move only on measurement.

## Key Takeaways

- Retrieval is ranking under a token budget: admit few, admit the best.
- Blend similarity, recency, and importance; any single signal alone misleads.
- Filter first in SQL, then rank; scoping before scoring is the performance and quality win.
- Hybrid retrieval covers both exact identifiers and paraphrased meaning.
- Memory retrieval is RAG over your agent's past; the same indexes and disciplines apply.

## What's Next

Module 5 confronts growth: pruning, progressive summarization, importance scoring, and decay policies that keep a memory store useful and affordable as it scales.

## Exam Prep Notes

Know what each retrieval signal contributes and what breaks when it is missing. Be able to order a retrieval pass correctly: filter, score, admit, format. Understand when embeddings help, when they hurt, and how hybrid resolves the split. Expect diagnostic scenarios: stale results winning, exact IDs missing, slow queries, and window pollution from over-admission.

---

Matt Murphy AI | The Faction Group LLC | mattmurphy.ai

---
_Source: https://the-faction.mn.co/posts/107155312_
