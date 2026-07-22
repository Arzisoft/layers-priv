# Layer 11 of 13 — Load Balancing & Scaling
**Tier 2 — Growth** | Matt Murphy Builder Certification Series

> *Builds on Tier 1 (Solopreneur). Assumes those concepts and tools are already understood.*

---

## What It Covers

Managing multi-server deployments as the app has real daily users — the challenge shifts from
surviving occasional spikes to handling consistent, growing traffic efficiently.

**Core goal:** You can manage multi-server deployments with connection pooling, database
replicas, and health-check-based routing — keeping the app fast and reliable under sustained
traffic.

---

## Key Concepts

**Connection pooling** — Opening and closing a database connection per request is expensive.
Connection pooling keeps a set of connections open and reuses them — dedicated phone lines
instead of dialing every time. PgBouncer or a platform's built-in pooler handles this.

**Database read replicas** — Copies of the database that handle read requests, taking pressure
off the main database — photocopies of a reference book so multiple people can look things up
without fighting over the original.

**Health checks and intelligent routing** — An automated check every few seconds asking each
app copy "are you alive and working?" A copy that fails gets pulled from rotation automatically
instead of serving errors to real users.

**Sticky sessions vs. stateless design** — Sticky sessions force a user to always talk to the
same server copy — simple but fragile, since a crash loses everything. Stateless design stores
session data (carts, login status) in a shared store (Redis) so any copy can serve any user —
harder to set up, much more reliable.

**Rate limiting and traffic shaping** — Caps how many requests a single user/IP can make per
minute, protecting the app from one aggressive user, a bot, or an attack.

---

## Toolkit (adds to Tier 1)

- **PgBouncer or Supabase connection pooler** — manages database connections so the app doesn't overwhelm the database opening too many at once
- **Redis** — shared memory store keeping session data available to every app copy, so users don't lose state when routed to a different copy
- **Health check endpoints** — a simple URL (e.g. `/health`) returning "OK" that the load balancer checks to decide which copies receive traffic
- **k6 or Artillery (advanced)** — load testing tools for sustained traffic patterns, not just spike tests

---

## Common Pitfalls

- Never load-testing before launch — the app works fine with one user (you); the first hundred simultaneous users expose every bottleneck the hard way
- Storing sessions on the server instead of a shared store like Redis — adding a second server copy loses users' login state and cart contents
- Ignoring database connection limits — twenty app copies each opening fifty connections crashes production even though it worked fine locally
- Setting up auto-scaling without a maximum — a bot or bug can spin up hundreds of copies and run up a massive cloud bill overnight
- Not setting up health checks — the load balancer keeps sending traffic to crashed copies while healthy copies sit underused
- Scaling the app servers but forgetting the database — ten thousand requests/second hits a database that can only handle five hundred, and the database becomes the bottleneck

---

## Tier 2 Self-Assessment Checklist

- [ ] Can you explain why an app that works for ten users might crash for a thousand?
- [ ] Do you know horizontal scaling (more copies) vs. vertical scaling (bigger server) — and which to ask AI for?
- [ ] Have you run a load test on your app to see how it handles simulated traffic?
- [ ] Can you describe to AI what a load balancer does and ask it to set one up?
- [ ] Do you know what auto-scaling is and how to configure it with a minimum, maximum, and scaling trigger?
- [ ] If a user said the app was slow, would you know which metrics to check — response time, error rate, CPU usage?
- [ ] Can you explain what a health check is and why the load balancer needs one?

---

## AI Audit Prompt (copy into your AI tool)

```
Review my app's load balancing and scaling setup and check the following. For
each one, tell me pass or fail with a specific example:
Load balancing: Is my app configured to distribute traffic across multiple
copies, or is everything running on a single instance?
Auto-scaling: Is auto-scaling configured with sensible minimum and maximum
limits and a clear trigger (like CPU usage or request count)?
Health checks: Does my load balancer have health check endpoints that
automatically remove unhealthy copies from rotation?
Session management: Is user session data stored in a shared store (like
Redis) so it works across multiple app copies, or is it stuck on individual
servers?
Database connections: Is connection pooling configured so my app doesn't
overwhelm the database with too many simultaneous connections?
Database scaling: Are read replicas set up to handle read-heavy traffic, or
is my single database handling everything?
Give me an overall score out of 6 and list the top 3 things to fix first.
```

---

## Certification pathway

Associate Builder = all 13 layers at Tier 1. Certified Builder = all 13 layers at Tier 1 + Tier 2.
MADE Certified = all 39 tier exams + capstone. 80% to pass each exam, 24-hour retake cooldown.
