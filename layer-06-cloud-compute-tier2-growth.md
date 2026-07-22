# Layer 6 of 13 — Cloud & Compute
**Tier 2 — Growth** | Matt Murphy Builder Certification Series

> *Builds on Tier 1 (Solopreneur). Assumes those concepts and tools are already understood.*

---

## What It Covers

Actively managing and optimizing cloud costs and compute choices once an app has real users
and the cloud bill is real money.

**Core goal:** You can optimize cloud costs across multiple services, choose the right compute
model per workload, set up scaling rules, and manage resources as traffic grows and shrinks.

---

## Key Concepts

**Containers** — The entire app (code, settings, dependencies) packaged into one unit that runs
the same everywhere — a shipping container for software. Docker is the common tool; Railway
and Fly.io use containers under the hood.

**Scaling: vertical vs. horizontal** — Vertical = a bigger server (sedan to truck). Horizontal =
more servers sharing the load (adding more trucks). Horizontal is usually better for web apps —
if one server fails, the others keep running.

**Edge functions** — Run code at data centers near users instead of one central location, so a
London request is processed in London, not shipped to Virginia and back. Vercel Edge
Functions, Cloudflare Workers.

**Cost optimization patterns** — Caching (don't recompute), right-sizing (use only the compute
actually needed), scheduling (heavy tasks in off-peak/cheaper hours). Can cut cloud bill 40-60%
without changing what the app does.

**Auto-scaling** — Rules that add capacity when traffic increases and reduce it when traffic
drops, instead of guessing — no paying for empty servers at 3am, no crashing at noon.

---

## Toolkit (adds to Tier 1)

- **Docker** — package the app into containers that run consistently across any cloud platform; AI can generate Dockerfiles
- **Cloud cost management (AWS Cost Explorer, Infracost)** — spend breakdown by service, trend alerts
- **CDN (Cloudflare, AWS CloudFront)** — distribute static files worldwide, cut load time and transfer cost
- **Caching layers (Redis, Upstash)** — fast temporary storage for frequently accessed data, cuts repetitive-request compute cost

---

## Common Pitfalls

- Never checking the cloud bill until month-end — a runaway function can burn money for weeks unnoticed
- Assuming "serverless" means free — it's pay-per-execution; popularity turns pennies into real money fast
- Letting AI pick cloud services without understanding the pricing model — AI optimizes for working code, not cost-effective code
- Running the same compute 24/7 when traffic is only 8 hours/day — paying for 16 hours of empty servers
- Ignoring data transfer costs — moving data between services/out to users often costs more than compute itself
- No billing alerts set up before the first surprise bill

---

## Tier 2 Self-Assessment Checklist

- [ ] Can you explain in plain language where the app's code actually runs for a visitor?
- [ ] Do you know current monthly cloud spend and which services cost the most?
- [ ] Have you set up billing alerts for unexpected spend spikes?
- [ ] Can you explain serverless vs. traditional server and why it matters for the bill?
- [ ] Do you know the app's free-tier limits and how close you are to them?
- [ ] If traffic went 10x tomorrow, do you know what would happen to cost and performance?
- [ ] Can you name at least one place caching/optimization would cut the cloud bill?

---

## AI Audit Prompt (copy into your AI tool)

```
Review my app's cloud and compute setup and check the following. For each
one, tell me pass or fail with a specific example:
Cost efficiency: Are there any functions, queries, or API calls that run more
frequently than necessary, and could caching or batching reduce the compute
cost?
Resource sizing: Is the app using more compute power or memory than it
actually needs, or is it under-provisioned and at risk of slowdowns?
Serverless configuration: Are serverless function timeouts, memory limits,
and concurrency settings appropriate for the workload?
Data transfer: Are there large assets (images, videos, files) being served
directly from the compute layer instead of through a CDN?
Scaling readiness: If traffic increased 10x, which parts of the
infrastructure would fail first, and what would need to change?
Billing visibility: Are there billing alerts, budget limits, or cost
monitoring dashboards set up to catch spending anomalies?
Give me an overall score out of 6 and list the top 3 things to fix first.
```

---

## Certification pathway

Associate Builder = all 13 layers at Tier 1. Certified Builder = all 13 layers at Tier 1 + Tier 2.
MADE Certified = all 39 tier exams + capstone. 80% to pass each exam, 24-hour retake cooldown.
