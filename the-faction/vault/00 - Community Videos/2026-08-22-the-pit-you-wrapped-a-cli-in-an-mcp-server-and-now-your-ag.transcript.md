---
type: transcript
lesson: "You wrapped a CLI in an MCP server and now your agent is slower and more expensi"
course: "The Pit"
author: "Matt Murphy"
post_id: 106195643
published: "2026-08-22T19:00:03Z"
source_url: "https://the-faction.mn.co/posts/106195643"
duration: "1m49s"
words: 268
transcribed_by: "deepgram auto-captions (Mighty)"
---

# Transcript — You wrapped a CLI in an MCP server and now your agent is slower and more expensi

> You wrapped a CLI in an MCP server and now your agent is slower and more expensive. Today I walk through why CLI is the native agent interface, when MCP actually adds value versus when it just adds overhead, and how to measure the cost difference at scale.

You wrapped a CLI tool in an MCP server. Your agent is now running slower, cost you more, and does less. Every MCP call carries context overhead, whether it's schema negotiation, transport serialization, permission handshakes. Your agent was already one command away from the answer. Now it routes through a wrapper that adds latency, tokens, and strips capabilities.

The tools outgrew the wrappers. CLIs were always there. So let's talk about it. First, CLI is the native interface. No wrapper, no translation layer.

Your agent calls the command directly, reads stand out, and acts on the result. One call, one response, zero protocol overhead. So direct your AI to identify every MCP wrap CLI tool in your stack and benchmark it against a direct CLI call for speed and token cost. That's a win. Step two, MCP adds value only when the tool does not have a CLI.

So APIs without command line access, proprietary services that require authentication negotiation, or multi step workflows that need stateful context, those are MCP use cases. A tool already has a CLI is not. So direct your AI to audit your MCP servers and flag everyone that wraps a tool with an existing CLI equivalent. And step three, cost per call matters at scale. If your agent makes two hundred tool calls per session, the overhead per call compounds.

So direct your AI to measure token cost and latency per MCP call versus direct CLI execution for your ten most important tools. Not every tool needs a wrapper. Most of them already have an interface. You just need to use it.

---
_Source: https://the-faction.mn.co/posts/106195643_
