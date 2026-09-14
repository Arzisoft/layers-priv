---
type: transcript
lesson: "Shoutout to Alireza for requesting this one. You keep patching v1 because v2 sou"
course: "The Pit"
author: "Matt Murphy"
post_id: 106568257
published: "2026-08-28T14:00:02Z"
source_url: "https://the-faction.mn.co/posts/106568257"
duration: "2m21s"
words: 383
transcribed_by: "deepgram auto-captions (Mighty)"
---

# Transcript — Shoutout to Alireza for requesting this one. You keep patching v1 because v2 sou

> Shoutout to Alireza for requesting this one. You keep patching v1 because v2 sounds like a rewrite. It is not. Today I walk through the real signal that tells you it is time for v2, how to run v1 and v2 side by side without shutting anything down, and why every API without a sunset policy becomes pe

Your AI assistant added one endpoint to your API just last week. Well, it broke three integrations you did not know existed. So every time a customer needs something your API does not do, you just bolt another endpoint on to version one. So every time an endpoint should have worked differently from the start, you patched it and hope nobody noticed the inconsistency. However, six months of this and your API is a patchwork of workarounds that your documentation cannot keep up with.

That and your customers can't predict it anymore either. That's when v two stops being optional. V one is dead. So here's the fix. Step one, the signal is not feature count.

It is breaking changes you cannot make. You need to rename a field, change a response structure, fix an authentication flow, or remove an endpoint that never should have shipped, but existing clients depend on that broken version. So the moment you cannot fix your API without breaking someone, you need to move to v two. So direct your AI to audit every endpoint in your current API and flag every change you would make if backward compatibility were not a constraint. That is your v two scope and that is a win.

Step two. V two is not a rewrite. It is a parallel path. You do not shut down v one the day v two launches. You run both side by side.

Existing clients stay on v one, new clients onboard to v two immediately. So you set a sunset date for v one, communicate it clearly, and give people a migration window. Then DirectoryAI to build a versioned routing layer so v one and v two run side by side behind the same domain with version specific routing, shared authentication, and independent endpoint logic. That's a win. And step three, every API without a sunset policy becomes permanent technical debt.

If v one has no expiration date, you're maintaining two APIs forever. So direct your AI to implement sunset headers on every v one response with a deprecation date and a migration guide URL. So clients, they know exactly when to move and where to go. Your API, it's a product. And products, they have versions.

Ship v two before v one buries you.

---
_Source: https://the-faction.mn.co/posts/106568257_
