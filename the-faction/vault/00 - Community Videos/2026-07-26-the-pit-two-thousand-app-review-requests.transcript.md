---
type: transcript
lesson: "Two thousand app review requests."
course: "The Pit"
author: "Matt Murphy"
post_id: 105091450
published: "2026-07-26T14:34:33Z"
source_url: "https://the-faction.mn.co/posts/105091450"
duration: "2m19s"
words: 372
transcribed_by: "deepgram auto-captions (Mighty)"
---

# Transcript — Two thousand app review requests.

> Two thousand app review requests.

Over two thousand builders have had us look at their app. And the same three things are broken in almost every single one. Two thousand requests. Not kidding. DMs, comments, emails, inbound audits, at the faction group, at mattmurphyai from everywhere.

And there are people sending their URLs, asking what's wrong. The pattern was so consistent it was almost heartbreaking. They all built something that works. None of them built anything that protects it. Here are the three things that we're missing in almost every single app that we've reviewed.

Number one, no error handling beyond the default. Their AI built the feature. When the feature works, it works beautifully, right? But when it fails, the user gets a white screen or a stack trace or a generic five hundred error that means nothing to anyone. No graceful error messages, no fallback states, no way for the user to understand what happened or what to do next.

Your AI builds the happy path. It never builds the unhappy path. And your users live most of their life on the unhappy path way more than you think. Number two, no environment separation. Development and production are running in the same database, same API keys, same configuration altogether.

One wrong query in development and your production users are gonna feel it instantly. I saw apps where test users named ASDF were sitting in the same tables as all the paying customers. And your AI does not know the difference between a test environment and a live one. Same for users. So unless you tell it they need to be separate, they aren't going to be.

And number three, no audit trail on sensitive actions. Users upgrading plans, changing email addresses, deleting data, modifying permissions, none of it is logged. When a customer says I did not authorize that charge, you have no record of what happened. When a team member accidentally deletes a record, you have no way to trace it back. And your AI, it built the actions, just never built the receipts.

Over two thousand apps we've seen. Same three gaps almost every time. Direct your AI to close them before your customers find them first, which is usually exactly what happens.

---
_Source: https://the-faction.mn.co/posts/105091450_
