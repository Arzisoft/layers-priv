---
course: "The Frontier"
module: "Module 6: Shared Memory Across Multi-Agent Systems"
lesson: "Module 6: Shared Memory Across Multi-Agent Systems — Study Guide"
type: "course_lesson"
post_id: 107155323
space_id: 24391596
source: "https://the-faction.mn.co/posts/107155323"
updated: "2026-09-10T19:37:35Z"
---

# Module 6: Shared Memory Across Multi-Agent Systems — Study Guide

# Agent Memory Systems

### T8 The Frontier | Module 6 Study Guide

## Module 6: Shared Memory Across Multi-Agent Systems

> Direct AI to configure shared memory that lets multiple agents work as a team without trampling each other's state.

## Why This Matters

The moment you run a second agent, memory stops being a private matter. A research agent and a writing agent working the same project either share what they learn or duplicate work and contradict each other. Shared memory is what turns a pile of agents into a system, and it is also where the ugliest bugs live.

## Core Concepts

**Shared versus private is a boundary decision.** Not everything should be shared. Project facts, client preferences, and task status usually belong to the team; an agent's scratch reasoning, retries, and half-formed drafts stay private. The design question for every piece of state is: who else needs this, and who would it confuse?

**A shared store is the meeting point.** The standard pattern is one shared memory store, usually the same Supabase tables from Module 3, that all agents read from and write to, alongside a private store or namespace per agent. Sharing through the database beats passing state through messages, because the store survives any single agent's failure.

**Synchronization is about timing.** Agents do not read the store continuously; they load state at boot and at defined checkpoints. Between those moments, the world can change. Sync patterns decide when agents refresh: on boot, before writes, on task handoff, or on notification.

**Conflicts are normal, not exceptional.** Two agents will eventually write different values for the same fact. Resolution needs a rule chosen in advance: last-write-wins with timestamps, source authority where one agent owns a domain, or escalation where a human or supervisor agent decides. Pretending conflicts will not happen is how shared stores rot.

**Ownership prevents most conflicts.** The cleanest multi-agent memory designs assign each domain a single writer: the research agent owns findings, the ops agent owns schedules, and everyone else reads. Write ownership plus shared reads eliminates whole classes of race conditions before they exist.

**Handoffs carry context.** When agent A finishes and agent B begins, B needs A's relevant conclusions, not A's whole transcript. A handoff record: what was done, what was decided, what remains, is a memory artifact that makes multi-agent pipelines composable. This becomes the backbone of the multi-agent architectures covered in the dedicated Multi-Agent Systems course later in the catalog.

## How It Works

Directing AI to add shared memory to a two-agent pipeline:

1. Inventory state and draw the boundary: shared facts and task status versus private working notes.
1. Create the shared store: shared tables with subject scoping, plus per-agent namespaces for private state.
1. Assign write ownership per domain, and give every record a writer ID and timestamp.
1. Define sync points: each agent refreshes shared state at boot, before writing, and at every handoff.
1. Pick the conflict rule per table: last-write-wins for low-stakes facts, owner-wins for owned domains, escalate for high-stakes contradictions.
1. Build the handoff record and make it the required interface between pipeline stages.

## Directing AI

1. "Split this agent system's state into shared and private: for each item, name who writes it, who reads it, and who must never see it."
1. "Implement a shared memory store with per-agent namespaces in Supabase, with writer ID and timestamp on every shared record."
1. "Assign write ownership per domain across these three agents and generate the access rules that enforce single-writer discipline."
1. "Define the sync points for this pipeline: boot, pre-write refresh, and handoff; implement stale-read detection using timestamps."
1. "Design the handoff record between the research agent and the writer agent: done, decided, remaining, with links to supporting memories."

## Common Mistakes

1. **Sharing everything.** Dumping every agent's scratch thoughts into shared memory buries teammates in noise and multiplies conflict surface.
1. **Sharing nothing.** Agents that only pass state through messages lose everything when one crashes mid-pipeline.
1. **No conflict rule until the first conflict.** Deciding resolution during an incident produces the worst rule every time.
1. **Multiple writers per domain.** Two agents updating the same fact class without ownership is a race condition subscription.
1. **Handoffs by transcript dump.** Passing agent A's entire history to agent B blows the context budget and hides the conclusions.
1. **Assuming instant sync.** An agent acting on state loaded at boot, an hour into changed reality, makes confidently stale decisions.

## Real-World Application

A builder runs a three-agent content pipeline: research, drafting, and review. Version one shares state by pasting each agent's output into the next agent's prompt. A crash in the drafting stage loses a morning's research, and the review agent keeps flagging claims the researcher already verified. The builder directs AI to rebuild on shared memory: a shared Supabase store with research findings owned by the researcher, draft status owned by the drafter, and a handoff record at each stage: done, decided, remaining. The review agent now reads verified claims from the store instead of re-litigating them, a crash resumes from the last handoff instead of from zero, and the pipeline runs unattended overnight.

## Decision Framework

- **Do multiple agents need this state to do their jobs?** Shared store; otherwise private namespace.
- **Could two agents plausibly write this fact?** Assign one owner and make everyone else a reader.
- **Is the fact low-stakes and frequently updated?** Last-write-wins with timestamps is enough.
- **Is a contradiction here expensive?** Route conflicts to escalation instead of silent overwrites.
- **Is one agent finishing work another continues?** Build the handoff record; do not pass transcripts.
- **Did an agent load state a while ago?** Refresh at sync points; treat boot-time state as perishable.

## Tool and Platform Notes

One Supabase project serves the whole team: shared tables with subject and writer columns, per-agent namespaces via a scoping column or schema, and row-level security if agents run with separate credentials. Timestamps and writer IDs are non-negotiable on shared records; they are what make conflict resolution and stale-read detection possible. Message queues can carry notifications between agents, but the durable truth lives in the store, not in the messages.

## Key Takeaways

- Decide shared versus private per piece of state; both extremes, share-everything and share-nothing, fail.
- One shared store plus per-agent private namespaces is the default architecture.
- Single-writer ownership per domain prevents most conflicts; timestamps and writer IDs handle the rest.
- Pick conflict rules per table in advance: last-write-wins, owner-wins, or escalate.
- Handoff records, not transcript dumps, are how agents pass work; sync points keep state fresh.

## What's Next

Module 7 takes everything into production: deploying memory systems, debugging retrieval failures, monitoring memory quality, and the AI Chief of Staff pattern as the capstone.

## Exam Prep Notes

Be able to draw the shared-private boundary for a given system and justify it. Know the sync point pattern, the three conflict resolution rules and when each fits, and why single-writer ownership works. Understand handoff records versus transcript passing, and what fails in share-everything, share-nothing, and message-passing designs. Expect pipeline scenarios with crashes, duplicated work, and stale reads to diagnose.

---

Matt Murphy AI | The Faction Group LLC | mattmurphy.ai

---
_Source: https://the-faction.mn.co/posts/107155323_
