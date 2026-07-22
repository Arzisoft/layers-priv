# Layer 6 of 13 — Cloud & Compute
**Tier 1 — Solopreneur** | Matt Murphy Builder Certification Series

> *Running Code in the Cloud Without Surprise Bills*

---

## What It Covers

Serverless functions, cloud billing, free tier limits, billing alerts, and cost optimization.

**Core goal:** You can deploy backend logic to the cloud and keep your bill predictable — by understanding what costs money and setting up alerts before you spend it.

---

## Key Concepts

**Serverless functions** — Code that runs only when called, not on a permanently-running server. You pay per execution (often fractions of a cent). Perfect for: API endpoints, webhooks, scheduled jobs. Vercel Functions, AWS Lambda, Cloudflare Workers.

**Pay per execution** — The cloud's cost model. A function that runs 1,000 times/day costs less than one that runs 1M times/day. AI optimizes for working code, not cost-effective code — *you* have to ask about cost.

**Free tier limits** — Every major cloud provider has a free tier: X GB-seconds of Lambda compute, Y API calls, Z storage. Know your limits before you launch. Free tier runs out. Alerts tell you when you're close.

**Billing alerts** — Set a spending threshold that sends you an email or notification. AWS: CloudWatch billing alarm. Vercel: usage alerts. OpenAI: monthly spending cap. Set these BEFORE you write a line of code.

**Cold starts** — Serverless functions "go to sleep" when not called. The first request after idle wakes them up (100ms–2s delay). Warming strategies exist; AI knows them. Just be aware the first call is slower.

**When NOT to use serverless** — Long-running processes (>15 minutes), apps that need persistent connections (WebSockets), or high-frequency tasks where per-execution costs exceed a fixed server. Sometimes a simple server (EC2, Fly.io) is cheaper.

---

## Toolkit

- **Vercel Functions** — serverless, integrated with Next.js
- **AWS Lambda** — the gold standard; huge ecosystem
- **Cloudflare Workers** — edge compute, ultra-fast cold starts
- **AWS CloudWatch / provider billing dashboards** — monitor spend
- **Calculator tools** — AWS Pricing Calculator before committing to architecture

---

## Common Pitfalls

- No billing alerts — first bill arrives as a surprise
- API calls inside loops — 1 call becomes 10,000 calls instantly
- Not knowing which cloud resources you're actually using (and paying for)
- Using the same API keys for dev and production (dev testing runs up prod budget)
- Never checking the billing dashboard until end of month

---

## Tier 1 Self-Assessment Checklist

- [ ] Do you have billing alerts on every paid cloud service you use?
- [ ] Do you know the per-execution cost of your serverless functions?
- [ ] Are dev and production using separate API keys?
- [ ] Have you checked the free tier limits for every service you use?
- [ ] Are there any infinite loops or runaway calls that could spike costs?
- [ ] Do you review your cloud billing dashboard at least weekly?
- [ ] Can you estimate your monthly cloud bill based on current usage?

---

## AI Audit Prompt (copy into your AI tool)

```
Review my app's cloud compute setup for cost and billing risks. Pass or fail:
1. Billing alerts: Are spending alerts configured on AWS, Vercel, OpenAI, and every other paid service?
2. API call patterns: Are there any API calls inside loops or on every keystroke that could multiply costs?
3. Key separation: Are separate API keys used for development vs production?
4. Free tier awareness: Do you know the free tier limits for each service and how close you are?
5. Cold start handling: Are serverless function cold starts handled gracefully for users?
6. Cost per feature: Can you estimate the monthly cost per feature for the 3 most-used features?

Give me a score out of 6 and the top 3 cost risks to address first.
```
