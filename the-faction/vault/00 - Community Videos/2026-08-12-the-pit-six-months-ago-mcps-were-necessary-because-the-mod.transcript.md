---
type: transcript
lesson: "Six months ago MCPs were necessary because the models could not access APIs dire"
course: "The Pit"
author: "Matt Murphy"
post_id: 105838724
published: "2026-08-12T19:00:01Z"
source_url: "https://the-faction.mn.co/posts/105838724"
duration: "2m20s"
words: 369
transcribed_by: "deepgram auto-captions (Mighty)"
---

# Transcript — Six months ago MCPs were necessary because the models could not access APIs dire

> Six months ago MCPs were necessary because the models could not access APIs directly. That is no longer true. Every MCP you keep loaded is consuming context and competing for attention in a finite window. Strip them out. Let your agent build integrations on demand. The tools outgrew the wrappers. Mo

Your MCPs are cooked. Your agent can build its own integrations now. Six months ago, MCPs, they were definitely necessary. The models were not capable enough to access APIs directly in most cases. They needed wrappers.

They needed connectors. They needed pre built bridges to talk to external services. That was a real limitation and MCPs definitely solved it back then. That limitation no longer Here's what changed and why it matters for how you're going to build going forward. Step one: Your agent can call APIs directly.

It can read documentation, authenticate, construct requests and handle responses on the fly. It does not need pre built wrapper to talk to Stripe anymore. It does not need an MCP to query a database and it does not need a connector to access third party services. It can build the integration in a moment for the exact task and move on. Loading a stack of prebuilt MCPs is like handing a chef a box of frozen meals when they have a full kitchen to work with.

Step two. Every MCP you keep loaded is consuming context for no reason at all. Your agent evaluates every connected tool every time it processes a request. Ten MCPs loaded means ten tools your agent considers before it even starts working. Most of them are irrelevant to the current task.

They are not helping. They are competing for attention in a finite context window. So strip them out. Get rid of them. Let your agent access what it needs when it needs it instead of carrying a toolbox full of tools it'll never use on this job.

And step three, the builders who are still stacking MCPs are optimizing for a world that no longer exists. The models have outgrown the wrappers in just six months. The platforms matured past the need for pre built bridges. If you're still loading every connector you can find, you're building for January's AI with August's AI. Direct your agent to build integrations on demand right now.

It's faster, cleaner, and it keeps your context window focused on the work that matters the most. MCP solved a real problem. That problem is gone. So let your agent cook.

---
_Source: https://the-faction.mn.co/posts/105838724_
