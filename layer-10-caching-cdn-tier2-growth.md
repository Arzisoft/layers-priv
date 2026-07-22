# Layer 10 of 13 — Caching & CDN
**Tier 2 — Growth** | Matt Murphy Builder Certification Series

> *Builds on Tier 1 (Solopreneur). Assumes those concepts and tools are already understood.*

---

## What It Covers

Caching more than static files — database queries, API responses, rendered pages — and
managing the hard part: cache invalidation, knowing when to throw away stale data and fetch
fresh data.

**Core goal:** You can implement server-side caching for dynamic content, manage cache
invalidation so users always see fresh data, monitor cache hit rates, and balance speed with
data freshness as the app grows.

---

## Key Concepts

**Server-side caching** — When 100 users request the same product page, the server queries
the database once, caches the result, and serves the cached version to everyone else. Redis
(an in-memory database) is the common tool.

**Cache invalidation** — When data changes, the cache goes stale. Strategies: time-based
expiration (cache expires after 5 minutes), event-based invalidation (cache clears when the
source record updates), or a combination of both.

**Cache hit rate** — A cache hit means the cached version was used; a cache miss means the
data had to be fetched fresh. A 90% hit rate means 9 of 10 requests are fast cached responses.
A low hit rate means the caching strategy needs adjustment — all the maintenance cost, none
of the speed benefit.

**Stale-while-revalidate** — Serve the cached version immediately for speed, fetch a fresh
version in the background for next time. Good default for data that changes but isn't urgent
(product catalog, blog).

**Cache layers** — Browser cache (closest to the user), CDN cache (geographically
distributed), server cache (closest to the database). Each layer catches what the layers above
missed — understanding this matters for diagnosing stale-data reports.

---

## Toolkit (adds to Tier 1)

- **Redis or Upstash** — fast in-memory server-side caching; Upstash is a managed, serverless-friendly version
- **ISR (Incremental Static Regeneration)** — Next.js feature that pre-builds pages as static files but regenerates them in the background when data changes
- **Cache monitoring dashboards (Datadog, Grafana)** — cache hit rates, response times, where caching is/isn't helping
- **Stale-while-revalidate headers** — HTTP headers telling browsers/CDNs to serve cached content immediately while fetching fresh content in the background

---

## Common Pitfalls

- Serving full-size images when thumbnails would do — use responsive images, WebP, lazy loading
- Not verifying the CDN is actually serving from edge locations — check response headers, don't assume
- Caching dynamic data without an invalidation strategy — fast now, stale for hours later
- Never measuring real load time — testing only on a fast laptop near the server hides what real users on slower connections/continents experience
- Deploying without cache-busting for CSS/JS — users keep seeing the old version because the browser cached the old files
- Treating caching as an afterthought instead of a design decision from day one

---

## Tier 2 Self-Assessment Checklist

- [ ] Have you run Lighthouse on your deployed app and know your performance score and LCP time?
- [ ] Are your images optimized — right format (WebP), right size, lazy loaded?
- [ ] Have you verified your CDN is active and serving static files from edge locations?
- [ ] Do static assets (CSS, JS, fonts) have cache headers so browsers don't re-download every visit?
- [ ] Can you explain static content (cacheable for everyone) vs. dynamic content (varies per user)?
- [ ] Have you tested load time from a location far from your server?
- [ ] Do you know what cache-busting is and can you verify updated files get served over stale ones?

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

## Certification pathway

Associate Builder = all 13 layers at Tier 1. Certified Builder = all 13 layers at Tier 1 + Tier 2.
MADE Certified = all 39 tier exams + capstone. 80% to pass each exam, 24-hour retake cooldown.
