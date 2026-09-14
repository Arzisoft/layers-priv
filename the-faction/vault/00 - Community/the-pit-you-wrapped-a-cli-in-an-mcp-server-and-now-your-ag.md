---
space: "The Pit"
author: "Matt Murphy"
post_id: 106195643
reactions: 0
comments: 2
published: "2026-08-22T19:00:03Z"
source: "https://the-faction.mn.co/posts/106195643"
---

# You wrapped a CLI in an MCP server and now your agent is slower and more expensi

You wrapped a CLI in an MCP server and now your agent is slower and more expensive. Today I walk through why CLI is the native agent interface, when MCP actually adds value versus when it just adds overhead, and how to measure the cost difference at scale.

**PROMPT:** Direct your AI: "Audit my MCP server configuration: (1) List every MCP server currently configured. For each, identify whether the underlying tool has a native CLI equivalent. (2) For every MCP server that wraps a CLI tool, benchmark a representative operation via MCP versus direct CLI: measure latency, token cost, and output completeness. (3) Recommend which MCP servers to keep and which to replace with direct CLI calls based on the benchmarks."

---

## Video transcript

_deepgram auto-captions (Mighty) · 1m49s_

You wrapped a CLI tool in an MCP server. Your agent is now running slower, cost you more, and does less. Every MCP call carries context overhead, whether it's schema negotiation, transport serialization, permission handshakes. Your agent was already one command away from the answer. Now it routes through a wrapper that adds latency, tokens, and strips capabilities.

The tools outgrew the wrappers. CLIs were always there. So let's talk about it. First, CLI is the native interface. No wrapper, no translation layer.

Your agent calls the command directly, reads stand out, and acts on the result. One call, one response, zero protocol overhead. So direct your AI to identify every MCP wrap CLI tool in your stack and benchmark it against a direct CLI call for speed and token cost. That's a win. Step two, MCP adds value only when the tool does not have a CLI.

So APIs without command line access, proprietary services that require authentication negotiation, or multi step workflows that need stateful context, those are MCP use cases. A tool already has a CLI is not. So direct your AI to audit your MCP servers and flag everyone that wraps a tool with an existing CLI equivalent. And step three, cost per call matters at scale. If your agent makes two hundred tool calls per session, the overhead per call compounds.

So direct your AI to measure token cost and latency per MCP call versus direct CLI execution for your ten most important tools. Not every tool needs a wrapper. Most of them already have an interface. You just need to use it.


---

## Discussion

**Nicholas Carmona** · 2026-08-22

> Would it be better to make your product a MCP server so that users can use it anywhere they want, or do you prefer CLI instead? Of course making sure it’s multi tenant, but thinking of ease of use for users, speed+costs
> 
> We made our product available to be connected via MCP in Claude or ChatGPT and for sure of course noticed the costs increase but wonder if CLI would be the better route or just an extra for users and provide both options

**Matt Murphy** · 2026-08-22

> There’s no doubt you saw my video last week about MCP being dead, and also that if there was native tools like CLI that could achieve the same output, I would always use the native tools versus adding the tech overhead of an MCP. My .02👊😎 [Nicholas](https://the-faction.mn.co/members/40267888)


---
_Source: https://the-faction.mn.co/posts/106195643_
