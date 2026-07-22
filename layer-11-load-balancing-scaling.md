# Layer 11 of 13 — Load Balancing & Scaling
**Tier 1 — Solopreneur** | Matt Murphy Builder Certification Series

> *Handling More Users Without Crashing*

---

## What It Covers

Why apps crash under load, load balancers, horizontal vs vertical scaling, auto-scaling, health checks, and how to test before real traffic arrives.

**Core goal:** You understand why apps crash under heavy traffic, can describe load balancing and auto-scaling to AI, and can verify your app handles traffic spikes without going down.

---

## Key Concepts

**Why apps crash under load** — Your server has limits: CPU, memory, concurrent connections. When more users arrive than it can handle, it slows down, then stops responding. That's a crash. Your app works perfectly for one user (you) — it may fall over for a hundred.

**Load balancer** — A traffic cop in front of your app. Distributes incoming users across multiple copies. If one copy is busy, users go to a less busy one. Vercel, Railway, and Fly.io include this automatically.

**Horizontal vs vertical scaling**
- Vertical: make the one server bigger (more RAM, faster CPU) — like buying a bigger food truck
- Horizontal: run more copies of your app — like opening more food trucks
- Horizontal is almost always better: no hard limit, if one copy crashes the others keep running

**Auto-scaling** — Watches traffic and adds copies when busy, removes them when quiet. You're not paying for 10 servers at 3am. Most platforms (Vercel, Fly.io, AWS) offer this. Ask AI to configure it with: minimum instances, maximum instances, trigger threshold.

**Health checks** — A `/health` endpoint your app exposes. Load balancer pings it regularly. If it stops responding, that copy gets removed from rotation automatically. Without health checks, dead copies still receive traffic.

**Session stickiness** — If user sessions are stored on one server, they break when traffic goes to a different copy. Solution: store sessions in a shared store like Redis, not on individual servers.

**Database connection limits** — 20 app copies each opening 50 connections = 1,000 database connections. Most databases have a limit. Use a connection pooler (PgBouncer).

---

## Toolkit

- **Cloud platform** — Vercel, Fly.io, Railway, Render, or AWS (your choice)
- **k6 or Artillery** — load testing tools; simulate hundreds/thousands of simultaneous users
- **Cloud platform metrics dashboard** — response times, error rates, CPU after load tests
- **Redis / Upstash** — shared session store for multi-instance apps

---

## Common Pitfalls

- Never load testing before launch — first real traffic spike reveals all bottlenecks
- Sessions stored on individual servers — users lose state when load-balanced
- No max on auto-scaling — a bot or bug spins up hundreds of instances overnight
- No health checks — crashed copies keep receiving traffic
- Scaling app servers but forgetting the database is the real bottleneck

---

## Tier 1 Self-Assessment Checklist

- [ ] Can you explain in plain language why 10-user apps can crash under 1,000 users?
- [ ] Do you know the difference between horizontal and vertical scaling?
- [ ] Have you run a load test on your app before launch?
- [ ] Can you describe a load balancer to AI and ask it to configure one?
- [ ] Is auto-scaling configured with min, max, and a trigger threshold?
- [ ] Do you know which metrics to check when the app is slow?
- [ ] Does your load balancer have a health check endpoint configured?

---

## AI Audit Prompt (copy into your AI tool)

```
Review my app's load balancing and scaling setup. Pass or fail with a specific example:
1. Load balancing: Is traffic distributed across multiple instances, or running on a single server?
2. Auto-scaling: Is auto-scaling configured with sensible min/max limits and a clear trigger?
3. Health checks: Does the load balancer have health check endpoints to remove unhealthy instances?
4. Session management: Is session data in a shared store (Redis), not stuck on individual servers?
5. Database connections: Is connection pooling configured to prevent DB overload?
6. Database scaling: Are read replicas set up for read-heavy traffic?

Give me a score out of 6 and the top 3 things to fix first.
```
