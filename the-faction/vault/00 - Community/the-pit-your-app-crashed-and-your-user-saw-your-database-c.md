---
space: "The Pit"
author: "Matt Murphy"
post_id: 105564346
reactions: 1
comments: 0
published: "2026-08-05T14:00:02Z"
source: "https://the-faction.mn.co/posts/105564346"
---

# Your app crashed and your user saw your database connection string on their scre

Your app crashed and your user saw your database connection string on their screen. That is your AI showing an attacker exactly how to get in. Today I walk through splitting error handling into public and private layers, catching errors at every boundary including API routes and webhooks, and setting up automated testing with tools like Vitest and Playwright to catch failures before your users do. Shoutout to Matthew Byrd for requesting this one.

**PROMPT:** Direct your AI: "Audit and rebuild my application's error handling with three components: (1) Split error handling into two layers. Build a public error handler that returns clean, user-friendly messages with no technical detail. Build a private error logger that captures the full stack trace, request context, and user session on the server only. Ensure no stack trace, database connection string, framework version, or internal path is ever exposed to the client. (2) Boundary coverage audit. Identify every error boundary in my application: API routes, background jobs, webhook receivers, payment callbacks, cron jobs, and third-party integrations. For each boundary that lacks a try-catch or error middleware, add one. Then configure automated testing using Vitest for unit tests and Playwright for end-to-end tests targeting each boundary with intentional failure scenarios. (3) Error logging pipeline. Build a centralized error log that captures: timestamp, user session ID, route, HTTP method, request input, stack trace, and severity level. Make it searchable and filterable by date, route, and severity. Retain logs for 90 days minimum."

---

## Video transcript

_deepgram auto-captions (Mighty) · 2m02s_

Your user just saw your database password on their screen. Your app crashed instead of a friendly error message it dumped a raw stack trace with your database connection string, your framework versions, and the exact line of code that failed. That's not a bug people. That is your AI showing the world exactly how to break into your application. So here are the three things you're going to direct your AI to do right now to fix it.

Number one, split your error handling into two layers. A public layer that shows your user a clean, helpful message and a private layer that logs the full technical detail on your server where only you can see it. Your AI built a handler that does both jobs. That is not efficiency. That is a security hole disguised as a feature.

The moment you separate what your user sees from what your server records is the moment your app starts behaving like a product instead of a prototype. That's a win. Step two, catch errors at every boundary, not just your login form, your API routes, your background jobs, your webhook receivers, your payment callbacks. Every uncaught error is a stack trace waiting to leak. DirectoryAI to set up automated testing that catches these before your users do.

Unit tests with something like VITEST or end to end tests with something like Playwright. Your AI knows how to configure both, turn them on, but it'll never do it unless you ask it to. Step three, build an error logging pipeline. Timestamps, user sessions, routes, inputs, stack traces, all of it. All private, all searchable.

When something breaks at two am, you trace it in minutes, not three hours of guessing what happened. Your users should never see your internals. Your logs, they should see everything. That is the difference between a product and a total liability. So get out there and make it a win!


---
_Source: https://the-faction.mn.co/posts/105564346_
