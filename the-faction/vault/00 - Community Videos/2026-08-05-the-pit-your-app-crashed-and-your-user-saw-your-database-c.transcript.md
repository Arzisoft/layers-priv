---
type: transcript
lesson: "Your app crashed and your user saw your database connection string on their scre"
course: "The Pit"
author: "Matt Murphy"
post_id: 105564346
published: "2026-08-05T14:00:02Z"
source_url: "https://the-faction.mn.co/posts/105564346"
duration: "2m02s"
words: 324
transcribed_by: "deepgram auto-captions (Mighty)"
---

# Transcript — Your app crashed and your user saw your database connection string on their scre

> Your app crashed and your user saw your database connection string on their screen. That is your AI showing an attacker exactly how to get in. Today I walk through splitting error handling into public and private layers, catching errors at every boundary including API routes and webhooks, and settin

Your user just saw your database password on their screen. Your app crashed instead of a friendly error message it dumped a raw stack trace with your database connection string, your framework versions, and the exact line of code that failed. That's not a bug people. That is your AI showing the world exactly how to break into your application. So here are the three things you're going to direct your AI to do right now to fix it.

Number one, split your error handling into two layers. A public layer that shows your user a clean, helpful message and a private layer that logs the full technical detail on your server where only you can see it. Your AI built a handler that does both jobs. That is not efficiency. That is a security hole disguised as a feature.

The moment you separate what your user sees from what your server records is the moment your app starts behaving like a product instead of a prototype. That's a win. Step two, catch errors at every boundary, not just your login form, your API routes, your background jobs, your webhook receivers, your payment callbacks. Every uncaught error is a stack trace waiting to leak. DirectoryAI to set up automated testing that catches these before your users do.

Unit tests with something like VITEST or end to end tests with something like Playwright. Your AI knows how to configure both, turn them on, but it'll never do it unless you ask it to. Step three, build an error logging pipeline. Timestamps, user sessions, routes, inputs, stack traces, all of it. All private, all searchable.

When something breaks at two am, you trace it in minutes, not three hours of guessing what happened. Your users should never see your internals. Your logs, they should see everything. That is the difference between a product and a total liability. So get out there and make it a win!

---
_Source: https://the-faction.mn.co/posts/105564346_
