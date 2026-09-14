---
course: "The Frontier"
module: "Module 5: Memory Management: Pruning, Summarization, and Decay"
lesson: "Module 5: Memory Management: Pruning, Summarization, and Decay — Study Guide"
type: "course_lesson"
post_id: 107155317
space_id: 24391596
source: "https://the-faction.mn.co/posts/107155317"
updated: "2026-09-10T19:36:59Z"
---

# Module 5: Memory Management: Pruning, Summarization, and Decay — Study Guide

# Agent Memory Systems

### T8 The Frontier | Module 5 Study Guide

## Module 5: Memory Management: Pruning, Summarization, and Decay

> Direct AI to implement the maintenance layer that keeps memory useful as it grows, because a store that only accumulates eventually buries its own signal.

## Why This Matters

Every memory system that works gets bigger. Retrieval slows, storage bills climb, and worse, good memories drown in mediocre ones. The agents that stay sharp at month twelve are the ones whose builders treated forgetting as a feature to engineer, not a failure to prevent.

## Core Concepts

**Memory does not scale infinitely.** Cost grows with rows, embeddings, and the retrieval compute that ranks them. Quality degrades even faster than cost grows: every junk memory is a candidate that can outrank a good one. A memory layer without a maintenance plan has a shelf life.

**Pruning.** Deliberate deletion of memories that no longer earn their storage: duplicates, superseded facts, trivia that was never retrieved. Pruning runs on rules you define, on a schedule, with logs of what was removed.

**Progressive summarization.** Instead of deleting old detail, compress it in stages. Thirty related episodic records become one monthly summary; four monthly summaries become a quarterly one. Each stage trades detail for density while preserving the storyline. The original records can be archived rather than destroyed, so detail is recoverable when it matters.

**Importance scoring.** A weight assigned at write time or learned from usage: standing decisions and hard-won corrections score high, small talk scores low. Importance protects memories from pruning and decay, and boosts them in retrieval. Retrieval frequency is a useful learning signal: memories that keep getting used argue for their own survival.

**Time-based decay.** Scores that fade with age unless something refreshes them: a retrieval, a citation, an explicit re-confirmation. Decay is gentler than deletion; a decayed memory still exists but stops competing until something makes it relevant again.

**Cost control is a design duty.** Embedding calls, storage, and retrieval compute all bill per unit. Memory-heavy agents that never maintain their stores develop bills that grow linearly while value plateaus. Maintenance is where the curve bends.

## How It Works

A monthly maintenance cycle for a production agent:

1. Dedupe: find near-identical memories, keep the best-sourced one, log the removals.
1. Supersede: where a fact has a newer version, archive the old record and point history at the new one.
1. Summarize: roll episodic records older than 60 days into monthly summaries; archive the originals.
1. Score: refresh importance from retrieval logs; protect the high scorers, flag the never-retrieved.
1. Decay and prune: apply age decay, then delete what sits below the floor with low importance and no retrievals.
1. Report: row counts, storage size, and retrieval latency before and after, so the cycle proves its value.

## Directing AI

1. "Implement a dedupe pass over the memories table: cluster near-identical records, keep the best-sourced one per cluster, and log every removal."
1. "Build progressive summarization: roll episodic memories older than 60 days into monthly summaries, archive originals, and link summaries to their sources."
1. "Add importance scoring: seed weights at write time by memory type, then adjust from retrieval frequency in the logs."
1. "Implement time-based decay with refresh-on-retrieval, and a pruning job that deletes only below a score floor, with a dry-run mode first."
1. "Analyze last month's embedding, storage, and retrieval costs for this agent and rank the three maintenance actions that would cut them most."

## Common Mistakes

1. **No maintenance plan at all.** The default failure: the store grows until retrieval quality and cost force an emergency cleanup that deletes carelessly.
1. **Pruning by age alone.** Old does not mean worthless; an old standing decision can matter more than fresh chatter. Age is one signal, never the only one.
1. **Summarizing without archiving.** Progressive summarization that destroys originals turns a compression decision into an irreversible one.
1. **Importance as a manual chore.** If every memory needs a hand-assigned weight, none will get one. Seed by type, learn from usage.
1. **Deleting without logs.** Silent pruning makes memory bugs undiagnosable; you cannot tell a pruned memory from a write that never happened.
1. **Letting embeddings bill quietly.** Re-embedding unchanged content and embedding trivia are silent budget leaks; embed selectively and cache.

## Real-World Application

A builder's operations agent has run for a year: 80,000 memories, retrieval getting slower each month, and a storage bill that doubled twice. Instead of a panic purge, the builder directs AI to build the maintenance cycle: dedupe collapses 14,000 near-duplicates, episodic records older than 60 days roll into monthly summaries with originals archived, importance scores seed from type and learn from retrieval logs, and a decay-plus-floor pruning job runs monthly with a dry-run first. The store drops to 31,000 active memories, retrieval latency falls by half, the bill flattens, and nothing irreplaceable was destroyed because summaries link back to archived sources.

## Decision Framework

- **Is a memory an exact duplicate or superseded?** Prune it; keep the best-sourced survivor and a log entry.
- **Is old detail still occasionally useful?** Summarize progressively and archive originals; do not delete.
- **Is a memory critical regardless of age?** Give it importance high enough to shrug off decay and pruning.
- **Is something never retrieved and low-importance?** Let decay carry it below the floor, then prune on schedule.
- **Is cost climbing while quality holds?** Target embeddings and storage first: dedupe, selective embedding, archive tiers.
- **Is quality falling while cost holds?** Target ranking pollution: prune junk, refresh importance, tighten admission.

## Tool and Platform Notes

Everything here runs on Supabase: SQL for dedupe and pruning, scheduled functions or cron for the monthly cycle, an archive table or cold-storage bucket for originals, and retrieval logs feeding importance updates. Keep pruning jobs in dry-run mode until the logs look right twice in a row. Embedding spend lives with your model provider; cache embeddings and only re-embed changed content.

## Key Takeaways

- Growth without maintenance degrades quality faster than it raises cost, and it raises cost plenty.
- Prune duplicates and superseded facts; summarize progressively and archive instead of destroying detail.
- Importance is seeded at write time and learned from retrieval; it shields what matters from decay.
- Decay fades unused memories out of competition without deleting them; refresh on use.
- Every maintenance cycle should log what it did and prove its value in before-and-after numbers.

## What's Next

Module 6 leaves the single-agent world: shared memory across multi-agent systems, synchronization, conflict resolution, and the line between shared context and agent-private state.

## Exam Prep Notes

Know the difference between pruning, summarization, and decay, and when each is the right tool. Understand progressive summarization's stages and why archiving matters, how importance is seeded and learned, and how decay interacts with refresh and pruning floors. Expect cost-control scenarios and diagnosis questions about stores that grew without maintenance.

---

Matt Murphy AI | The Faction Group LLC | mattmurphy.ai

---
_Source: https://the-faction.mn.co/posts/107155317_
