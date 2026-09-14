---
course: "The Mastery"
module: "Module 7 — Ship: Production Next.js App"
lesson: "Module 7: Ship: Production Next.js App — Exam"
type: "course_quiz"
post_id: 106186888
space_id: 24191170
source: "https://the-faction.mn.co/posts/106186888"
updated: "2026-08-21T15:19:34Z"
---

# Module 7: Ship: Production Next.js App — Exam

> Exam for **Module 7 — Ship: Production Next.js App** (The Mastery) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. Your builder is one day from launching a content site and asks what the pre-launch audit must cover. Per the module checklist, which five gates do you direct the AI through?

- **A.** Performance audit, SEO verification, security headers, error monitoring, and analytics, run as a literal checklist  ✅
- **B.** Unit test coverage, accessibility review, database backups, load testing, and legal compliance sign-off before launch
- **C.** Performance audit, SEO verification, uptime alerts, CDN configuration, and a full penetration test of every route
- **D.** Security headers, dependency updates, TypeScript strict mode, image compression, and a final AI code review pass

> **Answer:** A

### Q2. Your AI added Content-Security-Policy and HSTS to next.config and reports the security gate done. Before you accept the work, what does the module say you must do?

- **A.** Run an external scanner like securityheaders.com against the live site to confirm the headers appear in responses  ✅
- **B.** Read the next.config diff carefully, since headers defined in config are always served exactly as written in production
- **C.** Move every header into middleware instead, because next.config headers are ignored once the app deploys
- **D.** Disable the CSP temporarily in production so you can confirm the site still renders before re-enabling protections

> **Answer:** A

### Q3. A bot farm found your public form endpoint overnight and your Vercel bill jumped. You direct the AI to add rate limiting. Per the module, where does it belong?

- **A.** Only on admin routes behind authentication, since public endpoints are already covered by Vercel's default edge layer
- **B.** On auth endpoints, form submissions, and anything touching the database, using Upstash Redis or Vercel WAF patterns  ✅
- **C.** On every static page and asset request, since bots consume the most bandwidth downloading HTML and images repeatedly
- **D.** Inside each React component's event handlers, throttling clicks client side before requests ever leave the browser

> **Answer:** B

### Q4. Reviewing the AI's error.tsx, you see it renders error.message and a stack trace directly to visitors. What is the production standard you enforce?

- **A.** Show a friendly recovery UI to the user and log the real error to monitoring, never render internals in the browser  ✅
- **B.** Keep the stack trace visible but style it to match the brand, so users can screenshot useful detail for support tickets
- **C.** Replace error.tsx with a redirect to the homepage so users never linger on failures long enough to read any output
- **D.** Print the stack trace only for logged-in users, since authenticated customers are trusted and support gains detail

> **Answer:** A

### Q5. Two weeks after launch, your Vercel dashboard shows build times creeping steadily upward with each deploy. Per the module, what does this signal?

- **A.** A bandwidth spike from bot traffic, which always shows up first as slower builds before the bandwidth meter ever moves
- **B.** Vercel throttling your account tier, which resolves automatically once you upgrade to a plan with faster builders
- **C.** Healthy growth in traffic, since build duration scales directly with the number of daily users hitting the app
- **D.** Dependency bloat or unbounded static generation, which you should investigate before builds get slower and costlier  ✅

> **Answer:** D

### Q6. The morning dashboard shows bandwidth doubled overnight on your content site. Per the module's monitoring guidance, what is your immediate job?

- **A.** Celebrate the growth and scale up the plan, since a bandwidth doubling on a content site almost always means rankings
- **B.** Roll back the latest deploy immediately, because bandwidth spikes are nearly always caused by regressions
- **C.** Ignore it for a week to gather more data, since single-day bandwidth movements are noise that rarely justifies action
- **D.** Determine within hours whether the spike is real user growth or bot traffic, because the right response differs  ✅

> **Answer:** D

### Q7. Your capstone passes correctness and security review, but the AI suggests two more weeks of speed tweaks on pages already meeting Core Web Vitals. What does the module's rule say?

- **A.** Take the two weeks, since every performance gain compounds and launching an imperfect app damages your reputation
- **B.** Delay launch until Lighthouse reports a perfect 100 score on every route, then ship with full confidence in quality
- **C.** Ship now and defer the tweaks, because anything merely could-be-faster waits until real traffic proves it matters  ✅
- **D.** Split the difference by launching to a small beta group while the AI keeps optimizing the main production branch

> **Answer:** C

### Q8. Your AI reports a perfect Lighthouse score, but the run was against localhost. Why does the module say this number means little?

- **A.** Localhost scores are always lower than production, so a perfect dev score means the deployed app will exceed thresholds
- **B.** Cold starts, real network latency, and production data change performance, so you must audit the deployed URL  ✅
- **C.** Lighthouse cannot measure Core Web Vitals on local builds, so the tool silently substitutes estimated values
- **D.** Vercel re-runs Lighthouse automatically on deploy and blocks any release that fails, making local audits redundant

> **Answer:** B

### Q9. You already watch the Vercel Observability Dashboard daily, so a teammate argues Sentry is redundant. Per the module, what does an error tracker add?

- **A.** Nothing beyond duplication, since Vercel's dashboard already captures every exception with stack traces and alerts
- **B.** Only client side crash reports, because Vercel handles all server exceptions through function execution logs
- **C.** It captures production exceptions and alerts you before users report blank screens, complementing Vercel's meters  ✅
- **D.** A replacement for analytics, since error events double as conversion tracking once tagged with page metadata fields

> **Answer:** C

### Q10. Directing the error handling build, you ask the AI which Next.js files own failure states. Which mapping matches the module?

- **A.** try-catch blocks in every component are the standard, since Next.js has no file convention for rendering errors
- **B.** error.tsx and global-error.tsx catch failures per route segment while not-found.tsx handles missing routes  ✅
- **C.** middleware.ts intercepts errors before rendering, so one middleware file replaces per-segment boundaries
- **D.** 500.html and 404.html in the public folder are the standard, mirroring how classic static hosts handle errors

> **Answer:** B

### Q11. A scraper is hammering an unprotected API route on your Vercel app. Per the module, why does bot protection matter double here?

- **A.** Scrapers are a security problem and a billing problem at once, since you pay for the bandwidth and function time they burn  ✅
- **B.** Bots inflate your analytics dashboards, which is the primary cost, while Vercel absorbs all bandwidth overage charges for you
- **C.** Vercel suspends any project that receives bot traffic, so protection is mainly about avoiding account penalties
- **D.** Scrapers only threaten SEO by duplicating content elsewhere, and the module treats billing exposure as negligible

> **Answer:** A

### Q12. You ask the AI to add Strict-Transport-Security and X-Frame-Options to the capstone. In Next.js, where does the module say these headers live?

- **A.** In each page component's metadata export, alongside the title and description fields that power SEO for that same route
- **B.** In Vercel's dashboard settings only, since Next.js code has no supported mechanism for attaching response headers
- **C.** In next.config headers or in middleware, with your job being to verify they appear in the live production response  ✅
- **D.** In the root layout's HTML meta tags, where browsers read security policies the same way they read viewport rules

> **Answer:** C

### Q13. Post-launch, the function execution meter climbs while traffic stays flat, and costs follow. Per the module, what does slow function execution usually signal?

- **A.** Vercel cold starts that no setting can influence, so the right response is waiting for the platform to warm
- **B.** A DDoS attack in progress, since function duration is the first meter attackers move before bandwidth shows anything
- **C.** Healthy server rendering, because longer execution means richer pages and the meter is informational, not actionable
- **D.** Missing caching from your M3 work, since functions doing repeated work cost money and point to routes to cache  ✅

> **Answer:** D

### Q14. A content site launched and traffic never came; you discover there is no sitemap.xml and robots.txt blocks indexing. Which checklist gate was skipped?

- **A.** SEO verification, the gate that confirms metadata, sitemap.xml, and robots.txt from your M5 work before launch  ✅
- **B.** Security headers, since robots.txt is served as a header and a missing one causes crawlers to reject the domain
- **C.** Analytics, because Google only indexes sites that report traffic data back through a verified analytics setup
- **D.** Error monitoring, since indexing failures surface first as exceptions inside Sentry rather than search dashboards

> **Answer:** A

### Q15. Launch day went perfectly and your builder wants to stop checking dashboards. What cadence does the module prescribe for the Vercel Observability Dashboard?

- **A.** Check it daily for the first two weeks after launch, then weekly, because problems like creep surface after day one  ✅
- **B.** Check it only when Sentry fires an alert, since observability data is fully redundant until an actual exception occurs
- **C.** Check it hourly forever, because production apps require constant human monitoring regardless of traffic size
- **D.** Check it once at launch and again at the one year mark, treating the dashboard as an annual audit artifact only

> **Answer:** A

### Q16. securityheaders.com shows your live site missing CSP even though the AI defined it in next.config. Per the module's pitfalls, what likely happened?

- **A.** The scanner is wrong, since external tools cannot read headers on Vercel deployments protected by the edge network
- **B.** Browsers stripped the header because CSP must be declared in HTML meta tags rather than a server response
- **C.** Vercel requires a paid plan for custom headers, so free tier deployments silently drop everything you configure
- **D.** The header sits in the wrong config location or middleware overrides it, so it silently ships nothing at all  ✅

> **Answer:** D

### Q17. A teammate says the demo already works on your laptop, so hardening is overkill. Per the module, what does production expose that a demo does not?

- **A.** Nothing new in practice, since Vercel's platform automatically hardens any Next.js app during the deployment build
- **B.** Only cosmetic issues like fonts and layout shifts, which annoy users but never carry financial or security risk
- **C.** Merely scale limits, which are solved by upgrading the hosting plan rather than by any audit or hardening work
- **D.** Missing headers become vulnerability reports, unhandled errors become blank screens, open routes become big bills  ✅

> **Answer:** D

### Q18. During the performance gate, you need a tool to hold the line on Core Web Vitals for the deployed capstone. Which toolkit pairing does the module assign to that job?

- **A.** Sentry alone, since its performance module replaces both lab audits and field data collection for Core Web Vitals
- **B.** securityheaders.com, which measures LCP and CLS as part of its standard scan of production response headers
- **C.** Lighthouse or Vercel Speed Insights run against the production URL, holding the line on Core Web Vitals numbers  ✅
- **D.** The Vercel build log, where Core Web Vitals are printed automatically at the end of every successful deployment

> **Answer:** C

### Q19. Your AI audit ends with one flat list of twenty fixes and no priorities. Per the module's audit prompt design, how should the findings be organized?

- **A.** Alphabetically by file name, so the AI can apply fixes in a stable deterministic order across repeated audit runs
- **B.** By estimated effort in hours, so the cheapest fixes ship first regardless of security or correctness impact
- **C.** Into MUST FIX BEFORE LAUNCH and SAFE TO DEFER groups, each finding carrying a one line justification with it  ✅
- **D.** Into frontend and backend buckets, since launch decisions hinge on which half of the stack owns each finding

> **Answer:** C

### Q20. After passing the exam, your builder treats the shipped capstone as finished and stops touching it. How does the module frame a production app instead?

- **A.** As a final exam you submit once, since post-launch changes risk destabilizing an app that already passed its full audit
- **B.** As living infrastructure you monitor and improve continuously, letting real traffic set the ongoing priorities  ✅
- **C.** As a portfolio artifact, where the deployed URL matters mainly for certification evidence rather than users
- **D.** As a frozen release, where further work belongs in a rewrite on a newer framework version rather than patches

> **Answer:** B

### Q21. A builder has spent three weeks polishing an app with zero users, refusing to launch until it feels perfect. What does the module call this pattern?

- **A.** Prudent engineering, since shipping before perfection causes the vulnerability reports the module warns about
- **B.** Procrastination in an engineering costume, because endless optimizing without users delays real feedback  ✅
- **C.** A Core Web Vitals failure, since apps left unlaunched too long regress below performance thresholds
- **D.** Correct capstone procedure, because certification requires a perfect Lighthouse score before the exam attempt

> **Answer:** B

### Q22. Launch day showed zero errors, so your builder wants to skip monitoring entirely. Per the module's pitfalls, why is that risky?

- **A.** Because Vercel deletes observability data after 24 hours, so skipping a day permanently destroys the launch baseline
- **B.** Because monitoring is contractually required by Vercel's terms, and unmonitored projects can face suspension
- **C.** Because day one is the easiest day, and bandwidth spikes and creeping builds show up in week two if you watch  ✅
- **D.** Because Sentry only begins capturing exceptions after a fourteen day warmup period following first deployment

> **Answer:** C

### Q23. You are about to run the module's production readiness audit prompt against the deployed capstone. Which five sections does it demand findings in?

- **A.** Routing, components, caching, Server Actions, and deployment, mirroring the module structure of the course
- **B.** Performance, SEO, security, error handling, and monitoring with analytics, each with a pass or fail verdict  ✅
- **C.** Unit tests, integration tests, end to end tests, load tests, and manual QA, ordered cheapest to most costly
- **D.** Design, accessibility, copywriting, branding, and legal, covering all that a launch review board would evaluate

> **Answer:** B

### Q24. A user screenshot shows your app's error page displaying a full stack trace with file paths. Beyond looking broken, why does the module treat this as severe?

- **A.** A leaked stack trace kills trust and hands attackers reconnaissance, so reviewing every AI written boundary is required  ✅
- **B.** Stack traces slow page rendering dramatically, so the main cost is a heavy Core Web Vitals penalty on the error route itself
- **C.** Google indexes error pages aggressively, so the main risk is stack traces outranking real content in search results
- **D.** It only matters cosmetically, since stack traces contain no useful attacker information once source maps are hidden

> **Answer:** A

### Q25. Which statement best captures the governing principle of Module 7, Ship: Production Next.js App?

- **A.** Perfect optimization comes first, because a production app should never launch until every metric is at its best
- **B.** Deployment is the finish line, and once the app is live on Vercel the builder's responsibility for it is fully complete
- **C.** Production readiness is the AI's job, so a builder's role ends once the audit prompt is pasted and executed
- **D.** Close the gap between it works and it ships: audit, harden, monitor, and treat the live app as living infrastructure  ✅

> **Answer:** D


---
_Take it in the browser: https://the-faction.mn.co/posts/106186888_
