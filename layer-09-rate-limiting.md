# Layer 9 of 13 — Rate Limiting
**Tier 1 — Solopreneur** | Matt Murphy Builder Certification Series

> *Keeping Your API Bill from Exploding*

---

## What It Covers

Rate limits on API endpoints, billing alerts, API key management, throttling vs blocking, and protecting against runaway costs.

**Core goal:** You can add basic rate limits, set up billing alerts for paid services, and prevent a single user or coding bug from generating an unexpected bill.

---

## Key Concepts

**What a rate limit is** — A rule: "this endpoint can only be called X times per Y time period." Example: "each user gets 60 API calls per minute." When exceeded, return a 429 "Too Many Requests" response. The user waits — your cost doesn't spiral.

**Where rate limits are needed** — Every endpoint that calls a paid API (AI models, maps, payment processors), login/signup forms (brute-force prevention), and anything that sends emails or notifications. Rule of thumb: if it costs money or could be abused, it needs a limit.

**Billing alerts (your financial safety net)** — Set a spending threshold on every paid service you use. OpenAI, AWS, Google Cloud, Vercel all have built-in alert settings. Set before you write a line of code. The alert warns you; a hard cap saves you.

**API keys** — Like an ID badge for your app. Use separate keys for dev vs production — a dev testing mistake won't eat your production budget. Never commit keys to GitHub. Rotate them if exposed.

**Throttling vs blocking** — Throttling: slow down, but keep going. Blocking: stop entirely and return a 429. Most rate limiting starts with throttle, escalates to block. Decide what makes sense per feature.

**Debouncing** — For search/autocomplete: wait until the user *stops* typing before calling the API. Without it, a 20-character search query fires 20 API calls. With debouncing: 1 call.

---

## Toolkit

- **Upstash / Redis** — fast in-memory store for rate limit counters ("user X has made N calls in the last minute")
- **API provider dashboards** — OpenAI, Vercel, Supabase: check usage weekly at minimum
- **Billing alert systems** — configure on every paid API before launch

---

## Common Pitfalls

- No rate limits because "we don't have many users yet" — one bot changes that instantly
- No billing alerts — first notice is when the invoice arrives
- API call on every keystroke without debouncing (20 calls instead of 1)
- Same API key for dev and production
- No retry logic with backoff (tight-loop retries on 429 make it worse)
- Ignoring 429 responses — users see errors, not a graceful wait

---

## Tier 1 Self-Assessment Checklist

- [ ] Are billing alerts set on every paid API you use?
- [ ] Do expensive endpoints have per-user rate limits?
- [ ] Can you check API usage dashboards and explain your spend?
- [ ] Does your app handle 429 responses gracefully (retry with backoff)?
- [ ] Are dev and production using separate API keys?
- [ ] Is debouncing implemented on any API calls triggered by user input?
- [ ] Do you know the per-request cost of each paid API you use?

---

## AI Audit Prompt (copy into your AI tool)

```
Review my app's rate limiting and cost management setup. Pass or fail with a specific example:
1. Rate limits: Are endpoints calling paid APIs protected with per-user rate limits?
2. Billing alerts: Are spending alerts configured on all paid API providers?
3. Debouncing: Are API calls triggered by user input debounced (not fired on every keystroke)?
4. 429 handling: Does the app handle "Too Many Requests" with retry logic, not error screens?
5. API key management: Are keys stored securely and separated for dev vs production?
6. Usage monitoring: Can you see API usage trends and cost data?
7. Cost per feature: Can you estimate monthly cost per user for each API-dependent feature?

Give me a score out of 7 and list the top 3 cost risks to address first.
```
