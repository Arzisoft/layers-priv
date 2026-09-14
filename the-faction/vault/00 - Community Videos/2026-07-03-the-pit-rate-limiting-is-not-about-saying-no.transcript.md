---
type: transcript
lesson: "Rate limiting is not about saying no."
course: "The Pit"
author: "Matt Murphy"
post_id: 104072371
published: "2026-07-03T13:00:01Z"
source_url: "https://the-faction.mn.co/posts/104072371"
duration: "2m23s"
words: 387
transcribed_by: "deepgram auto-captions (Mighty)"
---

# Transcript — Rate limiting is not about saying no.

> Rate limiting is not about saying no.

Alright, let's talk about rate limiting. Rate limiting is not just about stopping abuse. It is about building a pricing model that totally scales. So here's how I think about rate limiting architecture for production systems we build for clients at Faction. There are three layers, but most builders are only implementing one.

So here's how it works. Layer one are hard limits. Fixed number of requests per time window. Hit the wall, get a four twenty nine. This protects you from abuse but it does not create a good user experience.

A user who hits the wall at ten am on a Tuesday because they were productive is now being punished for using your product well. So hard limits are a safety net, but they are not a user strategy. Layer two is adaptive limits. Instead of a fixed wall, the limits adjust based on the system's health. When the server is healthy, limits are generous.

But when the system is under load, limits tighten automatically. Token bucket and sliding window algorithms handle this. And they are not exotic. They are a Tuesday at any company who's running an API at scale. Trust me.

And layer three, tiered access as a business model. I love this one. Free users get a hundred calls per day. Builder access gets five hundred calls per day. Enterprise, they get a billion, right?

The rate limit becomes the pricing architecture. So your free tier should be generous enough to prove value and restrictive enough to create a reason for a user to upgrade. If your free tier lets your users do everything the paid tier does, well, your rate limit is not a rate limit. It's a charity. And you don't want to run a charity if you're trying to make a dollar.

So if you combine all three as best practices, that's a whole different story altogether because hard limits protect the system, adaptive limits protect the experience, and tiered limits protect your business. And that is definitely a win. So automated bots, they get blocked before they even reach your rate limiter. That I love. So most builders think rate limiting is adding a number to an endpoint.

It's not. It is total architecture for your business. So build it like architecture from day one. That's a win.

---
_Source: https://the-faction.mn.co/posts/104072371_
