# Layer 10 of 13 — Caching & CDN
**Tier 1 — Solopreneur** | Matt Murphy Builder Certification Series

> *Making Your App Load Fast Everywhere*

---

## What It Covers

Browser caching, Content Delivery Networks (CDN), static vs dynamic content, image optimization, and measuring performance with Lighthouse.

**Core goal:** You can set up caching and CDN, optimize images, and verify your app loads quickly — all by directing AI with the right prompts.

---

## Key Concepts

**Caching** — Save a copy of something so you don't have to fetch it again. First page load: compute + send. Second load: already ready. Like leftovers vs cooking from scratch every time.

**Browser caching** — Your server tells the browser "keep this file for 7 days." Cache headers (`Cache-Control`) do this. Hosting platforms (Vercel, Netlify) set these automatically — but verify they're configured correctly.

**CDN (Content Delivery Network)** — Copies of your static files on servers worldwide. User in Tokyo loads from Tokyo, not from a server in Virginia. Result: pages that took 2 seconds load in fractions. Most modern hosting includes a CDN; confirm it's active.

**Static vs dynamic content**
- Static: logo, fonts, CSS, JS — same for everyone. Perfect for caching.
- Dynamic: dashboard, profile, cart — different per user. Cannot blindly cache. Cache with care + invalidation strategy.

**Image optimization (biggest speed win)** — A single unoptimized photo can be larger than all your app code combined.
- Right format: WebP > JPEG for same quality
- Right size: don't serve a 4000px image for a 400px thumbnail
- Lazy loading: images below the fold don't load until scrolled to
Ask AI to implement all three.

**Measuring speed** — Lighthouse (Chrome DevTools → Lighthouse tab) gives a performance score + specific recommendations. Key metric: **LCP (Largest Contentful Paint)**. Under 2.5s = good. Over 4s = poor. Know your numbers.

**Cache-busting** — After a deploy, users might see stale cached files. Cache-busting adds version hashes to filenames so browsers always fetch the latest version after a deploy.

---

## Toolkit

- **Vercel / Netlify / Cloudflare Pages** — CDN + cache headers built in
- **Chrome DevTools Lighthouse** — performance score + LCP time
- **Chrome DevTools Network tab** — verify files are cached, not re-downloaded
- **Next.js Image component** — automatic resize, WebP conversion, lazy loading

---

## Common Pitfalls

- Serving full-size images when thumbnails would do
- Not checking whether CDN is actually active (you deployed to a CDN-capable platform but didn't verify)
- Caching dynamic data without a plan for when to invalidate it
- Never measuring actual load time ("works fast on my laptop")
- No cache-busting — users see outdated CSS/JS after deploys

---

## Tier 1 Self-Assessment Checklist

- [ ] Have you run Lighthouse and know your performance score + LCP time?
- [ ] Are images in WebP format, right-sized, and lazy-loaded?
- [ ] Have you verified CDN is active and serving from edge locations?
- [ ] Do static assets (CSS, JS, fonts) have cache headers set?
- [ ] Can you explain the difference between static and dynamic content caching?
- [ ] Have you tested load time from a location far from your server?
- [ ] Is cache-busting set up so deploys serve fresh files?

---

## AI Audit Prompt (copy into your AI tool)

```
Review my app's caching and performance setup. Pass or fail with a specific example:
1. Image optimization: Are images served in WebP/AVIF, sized correctly, and lazy-loaded?
2. CDN configuration: Are static assets served from a CDN with appropriate cache headers?
3. Cache headers: Do static files (CSS, JS, fonts) have long cache lifetimes with cache-busting?
4. Dynamic caching: Are frequently-accessed database queries cached, with a clear invalidation strategy?
5. Performance metrics: What is the current Lighthouse score and LCP time?
6. Font loading: Are web fonts preloaded with display:swap so they don't block rendering?
7. Code splitting: Is the app loading only code needed for the current page?

Give me a score out of 7 and the top 3 performance improvements to make first.
```
