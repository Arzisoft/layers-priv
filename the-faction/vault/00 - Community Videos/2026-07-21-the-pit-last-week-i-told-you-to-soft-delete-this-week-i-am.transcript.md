---
type: transcript
lesson: "Last week I told you to soft delete. This week I am telling you that sometimes y"
course: "The Pit"
author: "Matt Murphy"
post_id: 104865813
published: "2026-07-21T14:40:46Z"
source_url: "https://the-faction.mn.co/posts/104865813"
duration: "2m15s"
words: 369
transcribed_by: "deepgram auto-captions (Mighty)"
---

# Transcript — Last week I told you to soft delete. This week I am telling you that sometimes y

> Last week I told you to soft delete. This week I am telling you that sometimes you cannot delete at all. Federal retention laws can require you to keep customer records for seven years. Your AI will never flag this conflict. Today I walk through building a retention policy engine, mapping your speci

Your user clicked delete my account. So you deleted all their data. Well, you just broke a federal law. Certain industries require you to retain customer records for up to seven years after your relationship ends. Financial services, healthcare, tax related transactions, and even some legal agreements.

So your user might want their data gone, but the federal government says you have to keep it. Here are the three things you're gonna direct your AI to build right now to handle this for you going forward. Step one, a data retention policy engine. This isn't a toggle that says active or deleted. It's a system that knows the difference between the data a user controls and the data the law requires you to keep.

Those are two completely different categories and your AI will lump them together unless you tell it not to. So your customer facing data gets anonymized and your compliance data stays locked in a separate retention layer with an expiration date attached to it. That's a win. Alright, step two, a retention schedule mapped to your actual obligations. Seven years is not universal to all companies and all projects, right?

It depends on your industry, your state, and the type of record you're collecting. Payment records, for example, have a different timeline than user communications. So your AI can research the requirements for your specific business. But it'll never do it unprompted because it does not know what industry you're in or what lies apply to you wherever you're at. And step three, an audit trail that proves you followed the policy.

When a regulator asks, and in certain industries they absolutely will, you need to show exactly what was retained, what was anonymized, and when the clock started, and also when it expires. Your AI can build that logging system in an afternoon. Without it, your policy retention is a promise with no proof. So last week, I told you to soft delete. This week I'm telling you that sometimes you cannot delete it all.

The rules depend on what you are building. You have to do the research. So direct your AI to find out before your first user asks you to leave.

---
_Source: https://the-faction.mn.co/posts/104865813_
