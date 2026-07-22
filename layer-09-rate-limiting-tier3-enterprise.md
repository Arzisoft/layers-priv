# Layer 9 of 13 — Rate Limiting
**Tier 3 — Enterprise** | Matt Murphy Builder Certification Series

> *Builds on Tiers 1-2 (Solopreneur + Growth). Assumes those concepts and tools are already understood.*

---

## What It Covers

Architecting rate limiting at platform scale. At Tier 3, rate limiting is infrastructure — limits
managed across dozens of services, multiple teams with separate budgets, and potentially
usage-based pricing offered to your own customers. Systems that manage themselves with
minimal manual intervention.

**Core goal:** You can architect rate limiting at platform scale — distributed throttling across
microservices, automated abuse detection, usage-based billing for your own customers, and cost
governance across multiple teams and budgets.

---

## Key Concepts

**Automated abuse detection** — At scale, you can't manually monitor for abusive usage.
Automated systems detect anomalies: a sudden spike from one user, a bot making requests too
uniformly (real users are messy, bots are perfectly timed), or geographic patterns that don't
match normal usage — flagging suspicious activity and automatically applying stricter limits or
blocking bad actors.

**Usage-based billing (charging your own customers)** — If you're building a platform, you may
charge customers based on API usage, like cloud providers charge for compute time. Requires
accurate usage metering, billing integration, and transparent reporting — inaccurate metering
destroys customer trust.

**Multi-team cost governance** — Enterprise apps have multiple teams, each with their own
budget and API usage. A system allocates rate limits per team, tracks spending per team, and
prevents one team's runaway usage from affecting everyone else — departmental budgets, system
enforced.

**Circuit breakers (preventing cascade failures)** — A pattern where the app automatically stops
calling a service that's failing. If an API starts returning errors, a circuit breaker "opens" and
stops sending requests for a cooldown period, then cautiously tries again — without this, the app
keeps hammering a broken service, wasting money and making the problem worse.

**Global rate limiting across microservices** — When a platform is made of many small services,
rate limits need to be coordinated across all of them. A request passing through three services
might count against limits at each one — a global view prevents one service from consuming
all the capacity while others starve.

---

## Toolkit (adds to Tier 2)

- **Envoy or Istio (service mesh)** — infrastructure handling rate limiting, load balancing, and traffic management between all services, like a traffic control system for the entire platform
- **Stripe Billing or Lago (usage-based billing)** — connects usage metering to the payment system so customers can be charged based on actual consumption with accurate invoicing
- **Anomaly detection systems** — automated tools that learn normal usage patterns and flag anything unusual: a bot attack, a runaway loop, or a sudden traffic spike
- **Cost allocation platforms (CloudHealth, Kubecost)** — break down cloud spending by team, service, and feature for per-department budgeting

---

## Certification Exam Topics

- **Abuse detection** — Your platform sees a 10x spike in API calls from a single account over two hours. How does your automated system distinguish between a legitimate viral moment and a bot attack?
- **Usage-based billing** — A customer disputes their bill, claiming they made fewer API calls than you charged. How do you audit this, and what systems need to be in place for accurate metering?
- **Multi-team governance** — Team A's feature goes viral and their API usage doubles overnight, consuming budget allocated for Teams B and C. How do you prevent this in the future?
- **Circuit breaker** — A third-party API your platform depends on starts returning errors 50% of the time. What does a circuit breaker do in this situation, and how does it protect your costs and user experience?
- **Global coordination** — Two microservices both call the same paid external API. Each has its own rate limit of 1,000 calls/minute. But the external API's limit is 1,500 total. How do you coordinate?
- **Cost anomaly response** — Your monitoring shows API costs spiked 300% overnight. Walk through your investigation and response process.
- **Rate limit communication** — How do you communicate rate limits and usage quotas to developers building on your platform? What information do they need in API responses?
- **Graceful degradation** — Your primary AI API is rate-limited during a traffic surge. How does your platform maintain functionality without giving users errors?

---

## Common Pitfalls

- Not setting any rate limits because "my app doesn't have many users yet" — one bot, viral moment, or coding bug can generate thousands of requests in minutes
- Setting up API calls without billing alerts configured before writing a single line of code
- Calling an API on every keystroke (like autocomplete search) without debouncing
- Using the same API key for development and production, so a testing bug can eat through the production budget
- Not implementing retry logic with backoff — retrying immediately in a tight loop makes the problem worse and can get an account suspended
- Ignoring the 429 status code in API responses, leaving users with ugly error messages or broken features

---

## Tier 3 Self-Assessment Checklist

- [ ] Have you set up billing alerts on every paid API your app uses?
- [ ] Do your most expensive or most-called endpoints have rate limits in place?
- [ ] Can you check your API usage dashboards and explain what you're spending money on?
- [ ] Does your app handle 429 (Too Many Requests) responses gracefully instead of showing users an error?
- [ ] Are you using separate API keys for development and production?
- [ ] Have you implemented debouncing on any feature that calls an API based on user input (like search)?
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

## What's Next

Once you've gone through this kit and can answer "yes" to the self-assessment checklist,
you're ready for the Layer 9 certification exam at your target tier.

The best way to prepare: check your actual API spending right now. Log into every API provider
you use and look at your usage dashboards. Set up billing alerts if you haven't already. Then
review your app's code and find every place it makes an API call, and ask your AI tool to add
rate limits and debouncing where needed. Real cost management is the proof of work the exam
tests.

---

## Certification pathway

Associate Builder = all 13 layers at Tier 1. Certified Builder = all 13 layers at Tier 1 + Tier 2.
MADE Certified = all 39 tier exams + capstone. 80% to pass each exam, 24-hour retake cooldown.
