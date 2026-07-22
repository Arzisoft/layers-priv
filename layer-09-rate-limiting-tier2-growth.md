# Layer 9 of 13 — Rate Limiting
**Tier 2 — Growth** | Matt Murphy Builder Certification Series

> *Builds on Tier 1 (Solopreneur). Assumes those concepts and tools are already understood.*

---

## What It Covers

Managing rate limits and API costs strategically once the app has more users, more API
integrations, and paid plans with different usage levels — shifting from "prevent disasters" to
"manage costs and give different users different access."

**Core goal:** You can implement tiered rate limits based on user plans, monitor usage across
multiple API integrations, manage API keys with different quotas, and forecast costs accurately
as the app grows.

---

## Key Concepts

**Tiered rate limits** — Free users get 100 calls/day, Pro gets 1,000, Enterprise gets 10,000.
The app checks the user's plan and applies the matching limit. AI can build this, but you must
define the tiers clearly — which plan gets how many calls on which features; this directly
shapes pricing strategy.

**Distributed rate limiting** — When the app runs on multiple servers, each server needs to
share rate limit counts, or a user could hit Server A 100 times and Server B 100 times and get
200 requests when the limit is 100. A shared counter (usually Redis) keeps all servers
synchronized.

**Usage monitoring and forecasting** — Dashboards showing not just "how much did we spend
today" but "at this growth rate, what will we spend next month?" — used to negotiate better
rates with providers and set customer pricing.

**Retry logic with backoff** — When the app hits someone else's rate limit, it shouldn't just
fail. Exponential backoff waits a short time, then longer, then longer still. Without it, a
temporary rate limit becomes a permanent failure for users.

**Quota management across services** — Multiple paid APIs (AI, email, maps) each have their
own pricing, limits, and billing cycle. At Tier 2 you need a unified view of total spend and the
ability to set budgets per service — like managing separate credit cards but watching the total.

---

## Toolkit (adds to Tier 1)

- **Redis or Upstash with sliding windows** — distributed rate limiting across multiple servers, accurate counts regardless of which server handles the request
- **API gateway (Kong, AWS API Gateway)** — single entry point handling rate limiting, authentication, and usage tracking in one place instead of per-endpoint
- **Usage analytics dashboards (Datadog, Grafana)** — usage trends, cost projections, alerts on spending pattern changes
- **Cost management platforms (AWS Cost Explorer, Vercel Usage)** — spend broken down by service, endpoint, and time period

---

## Common Pitfalls

- Not setting rate limits because "my app doesn't have many users yet" — one bot, one viral moment, or one bug can generate thousands of requests in minutes
- Setting up API calls without billing alerts configured first — flying blind on spend
- Calling an API on every keystroke (autocomplete/search) without debouncing — a 20-character search term triggers 20 calls instead of one
- Using the same API key for development and production — a dev bug can eat the production budget
- Not implementing retry logic with backoff — tight-loop retries make it worse and can get the account suspended
- Ignoring the 429 status code ("Too Many Requests") instead of handling it gracefully

---

## Tier 2 Self-Assessment Checklist

- [ ] Have you set up billing alerts on every paid API your app uses?
- [ ] Do your most expensive or most-called endpoints have rate limits in place?
- [ ] Can you check your API usage dashboards and explain what you're spending money on?
- [ ] Does your app handle 429 responses gracefully instead of showing users an error?
- [ ] Are you using separate API keys for development and production?
- [ ] Have you implemented debouncing on any feature that calls an API based on user input?
- [ ] Do you know the per-request cost of each paid API your app uses?

---

## AI Audit Prompt (copy into your AI tool)

```
Review my app's rate limiting and cost management setup. For each item, tell
me pass or fail with a specific example:
Rate limits on expensive endpoints: Are the endpoints that call paid APIs
protected with rate limits? What are the current thresholds?
Billing alerts: Are spending alerts configured on all paid API providers?
What are the alert thresholds?
Debouncing: Are API calls triggered by user input (search, autocomplete,
filtering) debounced so they don't fire on every keystroke?
429 handling: Does the app handle "Too Many Requests" responses gracefully—
with retry logic, not just error messages?
API key management: Are API keys stored securely and are separate keys used
for development vs. production?
Usage monitoring: Can you see API usage trends and cost data in a dashboard
or logging system?
Cost per feature: Can you estimate how much each API-dependent feature costs
per user per month?
Give me an overall score out of 7 and list the top 3 cost risks to address
first.
```

---

## Certification pathway

Associate Builder = all 13 layers at Tier 1. Certified Builder = all 13 layers at Tier 1 + Tier 2.
MADE Certified = all 39 tier exams + capstone. 80% to pass each exam, 24-hour retake cooldown.
