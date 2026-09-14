---
type: transcript
lesson: "Your database might have perfect row-level security. Your cache sits in front of"
course: "The Pit"
author: "Matt Murphy"
post_id: 105411383
published: "2026-08-02T14:00:07Z"
source_url: "https://the-faction.mn.co/posts/105411383"
duration: "2m27s"
words: 392
transcribed_by: "deepgram auto-captions (Mighty)"
---

# Transcript — Your database might have perfect row-level security. Your cache sits in front of

> Your database might have perfect row-level security. Your cache sits in front of it and bypasses every rule you set up. Today I walk through how cached queries leak cross-tenant data, why caching is not the only shared layer that leaks, and how to test for it in ten minutes. If your app has more tha

A customer just called you. They're looking at someone else's revenue dashboard on your system. Their invoices, their customer list, their monthly revenue on your customer's screen right now. So your AI set up caching to speed up your app, but it never scoped the cache to the appropriate tenant. So customer A loaded their dashboard and the result got cached.

Customer B loaded the same page and boom, your cache served customer A's financial data instantly to customer B. Here's why this happens and what you need to direct your AI to do to fix it immediately. Step one. Your database security is irrelevant if your cache layer completely bypasses it. So you might have perfect row level security on your databases.

A lot of people do. But your cache sits in front of your database. So when your AI cached that query result, it cached the output after your security rules ran for customer A. So customer B never hit the database. They get customer A's cached results served directly to them.

So you need to direct your AI to scope every single cache key to the tenant ID. No exceptions. Every cached query, every cached page fragment, every cached API response must include a tenant context in that key. That's a win. Step two.

Caching is not the only shared layer leaking. Search indexes, background job queues, file storage paths, and logging pipelines. Right? Every shared service in your stack is a potential cross tenant leak if your AI never scoped it appropriately. So direct your AI to audit every shared layer and verify tenant isolation on every single one.

If the layer does not know which tenant is serving, it should not be serving anything at all. And step three, test this before your customer figures it out. Direct your AI to build a cross tenant access test. Log in as customer a, load a page, log out, log in as customer b, load that same page. If any data from customer a appears, your cache is leaking.

This takes ten minutes to test. The lawsuit from not testing it will take you years and a couple bucks. Promised. So one cash queried, two customers, and zero trust is left in your product. Direct your AI to scope every shared layer to every tenant today.

That's the win.

---
_Source: https://the-faction.mn.co/posts/105411383_
