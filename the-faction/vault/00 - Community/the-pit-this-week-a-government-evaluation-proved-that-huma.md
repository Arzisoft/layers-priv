---
space: "The Pit"
author: "Matt Murphy"
post_id: 105838643
reactions: 0
comments: 0
published: "2026-08-12T14:00:02Z"
source: "https://the-faction.mn.co/posts/105838643"
---

# This week a government evaluation proved that human-in-the-loop is not working.

This week a government evaluation proved that human-in-the-loop is not working. One in three dangerous agent commands got approved by the human reviewer. The fix is not better humans. The fix is architecture. Today I walk through why the audit should be the gate, not your attention span.

**PROMPT:** Direct your AI: "Build an agent containment architecture: credential scoping per agent, append-only tool call audit trail, and automated gates on red-line operations."

---

## Video transcript

_deepgram auto-captions (Mighty) · 2m14s_

An AI agent breached a company's production database this last week and the human supervising it clicked approve. This happened during a government evaluation of AI tools. This is not a hypothetical. This was not a lab exercise. This was production AI agent accessing government systems it was never authorized to touch.

And the human reviewer, the human in the loop that's responsible for catching it, waved it right on through. So here's what that means for how you're going to direct AI agents as you move forward. Step one: A human without the right tools is not a guardrail at all. They're just a bottleneck with no teeth. You cannot review hundreds of agent outputs every day and catch every single dangerous action by trying to read them.

You're gonna miss things. Everyone would. The skill set is not watch everything, read everything. The skill set is knowing what tools you put in front of that agent so the dangerous commands never reach it in the first place. Scoped credentials, network egress controls, automated gates that reject operations that are outside the defined boundaries of the agent.

Those tools catch what your eyes never will. Step two, logged tools calls are non negotiable. Every action your agent takes needs to be fully recorded. What it accessed, what it changed, what it called, and when. If you cannot produce that log, you have no way to know what your agent did when you weren't looking.

So direct your AI to instrument every tool call with an append only audit trail. When something goes wrong and my last name's Murphy, I know it will, that log is the difference between a diagnosis and a guess. And you want to know. So step three, run a structured audit against every build before it ships. Not a personal review of full system audit.

Same one we offer. Entry audits on the way in, exit audits on the way out. It's consistent. It's repeatable. It's not dependent on your attention span at two am when something's failing.

The human in the loop is only as good as the tools that they are using. So direct your AI to build those tools, then direct the agents how to operate them safely.


---
_Source: https://the-faction.mn.co/posts/105838643_
