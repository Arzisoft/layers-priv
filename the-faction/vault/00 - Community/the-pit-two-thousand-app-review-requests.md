---
space: "The Pit"
author: "Matt Murphy"
post_id: 105091450
reactions: 3
comments: 0
published: "2026-07-26T14:34:33Z"
source: "https://the-faction.mn.co/posts/105091450"
---

# Two thousand app review requests.

Two thousand app review requests.

The same three gaps in almost every single one.

No real error handling. Dev and prod on the same database. No audit trail on sensitive actions.

Today I walk through all three and how you direct your AI to close them. If you have not audited your own app for these three things, start today.

-MM

ORCHESTRATION PROMPT

Direct your AI: "Perform a three-point audit on my application: (1) Error handling audit: Review every API endpoint and identify where errors return raw stack traces, default framework error pages, or generic 500 responses to the user. Replace each with a graceful user-facing message and detailed backend-only logging. (2) Environment separation audit: Verify that development and production use completely separate databases, API keys, environment variables, and configuration files. Flag any shared credentials or connection strings. (3) Sensitive action audit trail: Identify every action that modifies user permissions, billing status, email address, password, or deletes data. Add audit logging to each that records who performed the action, when, from what IP, and what changed. Output a compliance-ready audit log schema."

---

## Video transcript

_deepgram auto-captions (Mighty) · 2m19s_

Over two thousand builders have had us look at their app. And the same three things are broken in almost every single one. Two thousand requests. Not kidding. DMs, comments, emails, inbound audits, at the faction group, at mattmurphyai from everywhere.

And there are people sending their URLs, asking what's wrong. The pattern was so consistent it was almost heartbreaking. They all built something that works. None of them built anything that protects it. Here are the three things that we're missing in almost every single app that we've reviewed.

Number one, no error handling beyond the default. Their AI built the feature. When the feature works, it works beautifully, right? But when it fails, the user gets a white screen or a stack trace or a generic five hundred error that means nothing to anyone. No graceful error messages, no fallback states, no way for the user to understand what happened or what to do next.

Your AI builds the happy path. It never builds the unhappy path. And your users live most of their life on the unhappy path way more than you think. Number two, no environment separation. Development and production are running in the same database, same API keys, same configuration altogether.

One wrong query in development and your production users are gonna feel it instantly. I saw apps where test users named ASDF were sitting in the same tables as all the paying customers. And your AI does not know the difference between a test environment and a live one. Same for users. So unless you tell it they need to be separate, they aren't going to be.

And number three, no audit trail on sensitive actions. Users upgrading plans, changing email addresses, deleting data, modifying permissions, none of it is logged. When a customer says I did not authorize that charge, you have no record of what happened. When a team member accidentally deletes a record, you have no way to trace it back. And your AI, it built the actions, just never built the receipts.

Over two thousand apps we've seen. Same three gaps almost every time. Direct your AI to close them before your customers find them first, which is usually exactly what happens.


---
_Source: https://the-faction.mn.co/posts/105091450_
