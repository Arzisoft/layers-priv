---
space: "The Pit"
author: "Matt Murphy"
post_id: 105666918
reactions: 0
comments: 0
published: "2026-08-07T19:00:01Z"
source: "https://the-faction.mn.co/posts/105666918"
---

# Every builder using AI agents for complex work has watched the agent lose the th

Every builder using AI agents for complex work has watched the agent lose the thread halfway through. That is not a model problem. It is a context management problem. Today I walk through structured state files, task decomposition, and validation checkpoints. This maps directly to T8 The Frontier Module 4: Context Management at Scale.

**PROMPT:** Direct your AI: "Build a context management system for long-running AI agent tasks with three components: (1) A project state file template in JSON that tracks: completed steps with outputs, current step with objectives, active constraints and decisions made, and next steps queued. This file gets passed to the agent at the start of every new session. (2) A task decomposition framework. Take any complex project and break it into chunks of 5-7 discrete steps. Each chunk runs as an independent session with the state file passed in. Define the handoff format between chunks. (3) A validation checkpoint protocol. After each chunk completes, the agent outputs a summary of what was done, what changed, and what the next chunk should expect. No chunk proceeds until the summary is reviewed and approved. Build this as a reusable workflow I can apply to any multi-step agent project."

---

## Video transcript

_deepgram auto-captions (Mighty) · 2m14s_

Did your AI agent forget what it was doing halfway through the job? It started strong. Step one was great. Step five was pretty solid. By step fifteen it was contradicting step three.

And by step thirty it had forgotten the project altogether. Well, that's not a bug folks. That is a context window limit and every single builder using AI agents for complex work hits it every day. So here are three things you direct your AI to build so your agent stays coherent across long operations. Step one, a structured context document that travels with every task.

Your AI agent does not remember what it did ten steps ago unless you tell it. So direct your AI to create a running project state file that updates after every step. What has been completed, what is in progress, what the constraints might be, and what decisions have been made. So when the agent starts a new step, it reads that state file first. And that file is the memory your agent does not have natively.

So that's a win. Step two. Task decomposition before execution. A thirty step job should never run as one continuous conversation. So direct your AI to break complex work into discrete chunks of five to seven steps each.

Each chunk gets its own session with the state file that passed in the start. So smaller scopes mean the agent never drifts far enough to contradict itself. The architecture of how you feed your work to your agent matters more than which model you're using. So figure it out. Step three, a validation checkpoint between every chunk.

Before the agent moves from chunk one to chunk two, something has to verify that output. And that something, that's you. So direct your AI to pause after each chunk and present a summary for you to review before proceeding. The builders who let agents run unsupervised for thirty steps, they know they're getting hallucinated garbage. The builders who check every live step before it goes to production get quality output.

So your AI agent is powerful, but it's not persistent. Direct it in pieces, verify in between. That is orchestration, and that is the win.


---
_Source: https://the-faction.mn.co/posts/105666918_
