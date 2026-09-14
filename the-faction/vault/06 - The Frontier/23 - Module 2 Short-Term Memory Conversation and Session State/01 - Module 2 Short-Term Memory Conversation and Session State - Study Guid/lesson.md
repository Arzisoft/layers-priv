---
course: "The Frontier"
module: "Module 2: Short-Term Memory: Conversation and Session State"
lesson: "Module 2: Short-Term Memory: Conversation and Session State — Study Guide"
type: "course_lesson"
post_id: 107155294
space_id: 24391596
source: "https://the-faction.mn.co/posts/107155294"
updated: "2026-09-10T19:34:15Z"
---

# Module 2: Short-Term Memory: Conversation and Session State — Study Guide

# Agent Memory Systems

### T8 The Frontier | Module 2 Study Guide

## Module 2: Short-Term Memory: Conversation and Session State

> Direct AI to implement session state that keeps a long conversation coherent without letting history swallow the context window.

## Why This Matters

Long before you touch a database, your agent has to survive a single long conversation. Sessions overflow windows, costs climb with every replayed turn, and a sloppy history strategy makes the agent lose the thread mid-task. Short-term memory is where token economics from Context Engineering meets real user sessions.

## Core Concepts

**Conversation history is a managed asset.** Every turn you replay into the window costs tokens and attention. Naive apps append forever; engineered agents decide, turn by turn, what history still earns its place.

**Session state is more than transcript.** A session carries structured state alongside the messages: the current task, variables collected so far, tool results, user corrections. Treating all of that as loose text in history is how agents lose track of what they are doing.

**The sliding window.** The simplest history policy: keep the most recent N turns and drop the oldest. Cheap, predictable, and blind. It works until something important, like a constraint stated in turn two, slides out of view.

**Summarization strategies.** Instead of dropping old turns, compress them: replace early conversation with a running summary that preserves decisions, constraints, and open questions. The tradeoff is loss of detail and the cost of the summarization calls themselves.

**The hybrid pattern.** Production agents combine the two: a rolling summary of everything old, verbatim recent turns, and pinned items that never leave the window regardless of age. Pinning protects the constraint stated in turn two.

**Threads and sessions are architecture.** A thread is a container for one line of work; a session is one continuous run of interaction. Deciding what state is thread-scoped, what is session-scoped, and what outlives both is a design decision you make before storage ever enters the picture.

## How It Works

A production session loop looks like this:

1. A turn arrives. The agent assembles context: system prompt, pinned items, running summary, recent verbatim turns, and the new message.
1. The agent responds, possibly updating structured session state: task status, collected variables, tool outputs.
1. A budget check runs. If history is approaching its token allowance, the oldest verbatim turns are folded into the running summary.
1. Pinned items are re-verified: constraints, identities, and standing corrections stay verbatim no matter how old they are.
1. At session end, anything durable is handed to the long-term layer, which is Module 3's territory.

The discipline is that every element in the window is there by policy, not by accumulation.

## Directing AI

1. "Implement a sliding window over conversation history with a 12-turn cap, and pin any turn I mark as a constraint so it never drops."
1. "Design a running-summary strategy for this agent: what triggers a summarization pass, what the summary must preserve, and its maximum token size."
1. "Refactor this session so task status and collected variables live in structured state, not in loose conversation text."
1. "Given this transcript that broke at turn 40, diagnose whether the failure came from dropped history, summary loss, or missing pins."
1. "Define what state is thread-scoped versus session-scoped for this app, and implement the session close handoff to persistent storage."

## Common Mistakes

1. **Appending history forever.** The default behavior of every quickstart tutorial, and the first thing that breaks in production.
1. **Summarizing away commitments.** A summary that keeps flavor but loses the client's stated budget is worse than no summary.
1. **No pinning mechanism.** Sliding windows without pins eventually drop the one instruction the user considered non-negotiable.
1. **Structured state stored as prose.** If the current task lives only as a sentence in history, it can be compressed, dropped, or misread.
1. **Summarizing on every turn.** Compression passes cost tokens too; run them on thresholds, not reflexively.
1. **Conflating thread and session.** Mixing three work streams into one thread guarantees the summary blends them into mush.

## Real-World Application

A builder runs an intake agent for a design agency. Intake conversations run 60 turns or more, and by turn 45 the agent had been quoting timelines that contradicted what the client said early on. The builder directs AI to rebuild the session layer: a 10-turn verbatim window, a running summary refreshed every 8 turns that must preserve budgets, deadlines, and decisions, and pins for the client's three stated constraints. The next 60-turn intake holds together, and token cost per session drops 40 percent because dead history stopped being replayed.

## Decision Framework

- **Is the conversation short and bounded?** Plain full history is fine; do not engineer what you do not need.
- **Are sessions long but low-stakes?** A sliding window alone is acceptable; losses are tolerable.
- **Do early constraints govern late turns?** Add pinning; constraints must never slide out.
- **Are sessions long and detail-heavy?** Use the hybrid: summary plus recent verbatim plus pins.
- **Is some state structural, like task status?** Move it out of prose into structured session state.
- **Does anything need to outlive the session?** Flag it for the long-term layer at session close.

## Tool and Platform Notes

Session state fits comfortably in Supabase: a sessions table, a messages table, and a JSONB column for structured state cover most agents. Keep the running summary as a field on the session row so it travels with the thread. Redis enters only if you measure session reads becoming a latency problem, not before. Framework session helpers vary; the policies above are yours to specify regardless of framework.

## Key Takeaways

- History is a managed, budgeted asset; nothing stays in the window by default.
- Sliding windows are cheap but blind; summaries preserve meaning but lose detail; hybrids with pins get both.
- Structured session state beats prose for anything the agent must act on, like task status and variables.
- Pinned items protect non-negotiables from both dropping and compression.
- Session close is a handoff point: durable state flows to long-term storage.

## What's Next

Module 3 crosses the session boundary: persistent storage patterns, choosing databases and stores by access pattern, and the schemas that give agent memory a durable home.

## Exam Prep Notes

Know the sliding window, summarization, and hybrid patterns, including what each loses and when each is enough. Be ready to diagnose mid-session failures: dropped turns, over-compressed summaries, missing pins, and prose-buried state. Understand thread versus session scoping and what happens at session close. Expect scenarios about token budgets and about which history policy fits a given app.

---

Matt Murphy AI | The Faction Group LLC | mattmurphy.ai

---
_Source: https://the-faction.mn.co/posts/107155294_
