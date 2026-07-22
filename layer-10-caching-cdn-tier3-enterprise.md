# Layer 10 of 13 — Caching & CDN
**Tier 3 — Enterprise** | Matt Murphy Builder Certification Series

> *Builds on Tiers 1-2 (Solopreneur + Growth). Assumes those concepts and tools are already understood.*

---

## What It Covers

Architecting caching at platform scale. At Tier 3, you're serving millions of requests, users span
the globe, and performance targets are measured in milliseconds, not seconds — cache
architectures need to scale automatically and degrade gracefully under pressure.

**Core goal:** You can architect caching at platform scale — edge computing for sub-second
responses worldwide, multi-layer cache consistency, automated cache optimization, and
performance SLAs for high-traffic applications.

---

## Key Concepts

**Edge computing (running code close to users)** — Traditional caching stores pre-built
responses on CDN servers. Edge computing goes further: it runs your actual code on those CDN
servers. Instead of your code running in one data center and caching the results globally, the
code itself runs globally — a user in Singapore triggers code that runs on a server in Singapore,
queries a nearby database replica, and responds in milliseconds. Platforms like Cloudflare
Workers, Vercel Edge Functions, and Deno Deploy make this possible.

**Multi-region cache consistency** — When your cache exists on servers across 50 cities, keeping
them all in sync becomes a real challenge. If you update a product price, how long until all 50
cache servers reflect the new price? Strategies: eventual consistency (all servers update within a
few seconds), active purging (push updates to all servers immediately), or versioned caching
(new data gets a new cache key, so old and new never conflict).

**Cache stampede prevention** — When a popular cached item expires, hundreds of simultaneous
requests all try to rebuild it at once, overwhelming the database — a cache stampede (or
thundering herd). Prevention strategies: lock-based rebuilding (only one request rebuilds, others
wait), probabilistic early expiration (random requests refresh the cache before it expires), and
pre-warming (rebuilding popular items before they expire).

**Performance budgets and SLAs** — At enterprise scale, formal performance targets exist —
"95% of pages load in under 500ms" or "API responses average under 100ms." These are Service
Level Agreements (SLAs). The caching architecture needs to be designed to meet these targets,
with monitoring that alerts when at risk of missing them. The AI tool can help implement
monitoring, but you set the targets.

**Automated cache optimization** — Manual cache tuning doesn't scale to enterprise traffic.
Automated systems analyze traffic patterns, identify which content benefits most from caching,
adjust expiration times based on how often data changes, and pre-warm caches for predictable
traffic spikes (a product launch or marketing email) — the shift from "you manage the cache" to
"the cache manages itself."

---

## Toolkit (adds to Tier 2)

- **Cloudflare Workers or Vercel Edge Functions** — platforms for running application code at the edge, on servers in 200+ cities worldwide, so every user gets sub-second response times regardless of geography
- **Varnish or Fastly** — enterprise-grade HTTP caching layers that sit in front of the application and serve cached responses at massive scale, handling millions of requests per second
- **Cache observability platforms (Datadog, New Relic)** — track cache performance across all layers and regions, showing hit rates, latency distributions, and cache consistency metrics in real time
- **Load testing tools (k6, Gatling)** — simulate thousands of concurrent users to test whether the caching strategy holds up under pressure, finding breaking points before users do

---

## Certification Exam Topics

- **Edge computing decision** — Your app has a personalized dashboard (different for each user) and a product catalog (same for everyone). Which one benefits from edge computing, and which benefits from traditional CDN caching? Why?
- **Cache consistency** — You update a critical product price, but users in three countries still see the old price 30 minutes later. What went wrong in your cache invalidation strategy?
- **Cache stampede** — Your most popular product page's cache expires, and 500 simultaneous requests all hit your database at once. What pattern prevents this, and how does it work?
- **Performance SLA** — Your SLA requires 95% of pages to load in under 500ms. Current monitoring shows you're at 92%. What caching optimizations do you investigate first?
- **Multi-layer debugging** — A page is slow despite having caching at the browser, CDN, and server levels. How do you determine which cache layer is the bottleneck?
- **Pre-warming** — You're launching a marketing campaign that will drive 10x normal traffic to a specific landing page. What caching preparations do you make?
- **Cost vs. speed** — Adding an edge caching layer would reduce your average response time from 800ms to 200ms but would cost an additional $2,000/month. How do you evaluate whether it's worth it?
- **Graceful degradation** — Your Redis cache server goes down during peak traffic. What should happen to your application, and how do you design for this failure?

---

## Common Pitfalls

- Serving full-size images when thumbnails would do — a single unoptimized image can be larger than the entire app's code
- Not checking whether the CDN is actually active — verify files come from edge locations via response headers, not just the origin server
- Caching dynamic data without an invalidation strategy — every cached item needs a plan for when and how it gets refreshed
- Never measuring the app's actual load time from a slow connection, older phone, or distant continent — only testing on a fast laptop on home internet
- Deploying without cache-busting for CSS and JavaScript, so users keep seeing the old version after a deploy
- Treating caching as an afterthought instead of a design decision — retrofitting is harder and less effective than building with caching in mind from day one

---

## Tier 3 Self-Assessment Checklist

- [ ] Have you run Lighthouse on your deployed app and know your performance score and LCP time?
- [ ] Are your images optimized — right format (WebP), right size (not larger than displayed), and lazy loaded?
- [ ] Have you verified that your CDN is active and serving static files from edge locations?
- [ ] Do your static assets (CSS, JS, fonts) have cache headers set so browsers don't re-download them on every visit?
- [ ] Can you explain the difference between static content (cacheable for everyone) and dynamic content (varies per user)?
- [ ] Have you tested your app's load time from a location far from your server, not just from your own device?
- [ ] Do you know what cache-busting is and can you verify that updated files get served instead of stale cached versions?

---

## AI Audit Prompt (copy into your AI tool)

```
Review my app's caching and performance setup. For each item, tell me pass or
fail with a specific example:
Image optimization: Are all images served in modern formats (WebP/AVIF),
properly sized for their display dimensions, and lazy loaded below the fold?
CDN configuration: Are static assets being served from a CDN with appropriate
cache headers? Check response headers for CDN indicators.
Cache headers: Do static files (CSS, JS, fonts, images) have long cache
lifetimes with cache-busting on deploy?
Dynamic content caching: Are frequently-accessed database queries or API
responses being cached, with a clear invalidation strategy?
Performance metrics: What is the current Lighthouse performance score and
Largest Contentful Paint (LCP) time?
Font loading: Are web fonts loaded efficiently (preloaded, display:swap) so
they don't block page rendering?
Code splitting: Is the app loading only the code needed for the current page,
or downloading everything upfront?
Give me an overall score out of 7 and list the top 3 performance improvements
to make first.
```

---

## What's Next

Once you've gone through this kit and can answer "yes" to the self-assessment checklist,
you're ready for the Layer 10 certification exam at your target tier.

The best way to prepare: run Lighthouse on your deployed app right now and look at the score.
If it's below 90, there's work to do. Check your images, verify your CDN is active, and ask your
AI tool to optimize your biggest performance bottlenecks. Speed improvements are immediately
visible and measurable, making them some of the most satisfying proof of work in the entire
certification.

---

## Certification pathway

Associate Builder = all 13 layers at Tier 1. Certified Builder = all 13 layers at Tier 1 + Tier 2.
MADE Certified = all 39 tier exams + capstone. 80% to pass each exam, 24-hour retake cooldown.
