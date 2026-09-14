---
course: "The Mastery"
module: "Module 6 — Vercel Deployment and Environments"
lesson: "Module 6: Vercel Deployment and Environments — Exam"
type: "course_quiz"
post_id: 106186753
space_id: 24191170
source: "https://the-faction.mn.co/posts/106186753"
updated: "2026-08-21T15:19:24Z"
---

# Module 6: Vercel Deployment and Environments — Exam

> Exam for **Module 6 — Vercel Deployment and Environments** (The Mastery) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. Your AI merges a reviewed PR into main and the feature is live on production minutes later, with no manual deploy step run by anyone. What explains this behavior on Vercel?

- **A.** A scheduled nightly job promoted the latest build; production only updates on Vercel's automated release timer, not merges.
- **B.** Pushes to the production branch trigger production deploys automatically, so on Vercel a merge to main means the code goes live.  ✅
- **C.** The preview deployment for that PR was auto-promoted because its build passed checks, which Vercel treats as production approval.
- **D.** Someone ran vercel logs from the CLI, which finalizes the most recent build and pushes it to the production domain by default.

> **Answer:** B

### Q2. Preview deploys must hit a test database while production hits the real one. Your builder asks how a single DATABASE_URL variable can do both jobs on Vercel. What do you tell them?

- **A.** Vercel scopes variables to Production, Preview, and Development, so one variable name holds a different value in each environment.  ✅
- **B.** Create separate variable names like DATABASE_URL_TEST and switch between them in code with a runtime check on the current deploy URL.
- **C.** Commit two .env files to the repository, one per environment, and Vercel selects the right file based on the deploying branch.
- **D.** Set the variable once globally and override it per request in middleware, since Vercel injects values at the edge on each call.

> **Answer:** A

### Q3. During review you spot NEXT_PUBLIC_STRIPE_SECRET_KEY in your project's Vercel settings, added by your AI to fix a build error. Why is this a critical problem?

- **A.** The NEXT_PUBLIC_ prefix restricts the variable to the Development scope, so all production requests will silently fail without it.
- **B.** Variables with that prefix are read-only at runtime, so rotating the key would require deleting and recreating the project.
- **C.** The prefix forces the value through Vercel's edge network, adding latency to every payment call that reads the secret key.
- **D.** The prefix bundles the value into client JavaScript, so any visitor with dev tools can read the secret and it must be rotated.  ✅

> **Answer:** D

### Q4. You rotate a leaked API key in the Vercel dashboard, but production keeps authenticating with the old key an hour later. Your AI insists the variable is saved correctly. What is missing?

- **A.** Changed environment variables do not take effect until you redeploy, so the running deployment still holds the old value.  ✅
- **B.** Vercel caches variables at the CDN layer for 24 hours; you must purge the edge cache from the dashboard to force the new key.
- **C.** The dashboard only stages changes; you must also run vercel env pull in CI so the pipeline commits the value to the repo.
- **D.** The old key persists in each returning visitor's browser storage, so the fix only takes effect for brand new sessions.

> **Answer:** A

### Q5. You are pointing yourdomain.com at Vercel without moving nameservers. Your AI drafts the DNS changes for your registrar. Which record setup should you approve?

- **A.** A CNAME on the apex pointing to Vercel and an A record for www, since the subdomain needs a fixed IP address for SSL to provision.
- **B.** MX records for both apex and www pointing to Vercel, letting the platform route web and mail traffic through one endpoint.
- **C.** TXT records on both hosts verifying ownership; Vercel then resolves the traffic automatically without any address records.
- **D.** An A record for the apex domain and a CNAME for www, after which SSL certificates provision automatically once DNS resolves.  ✅

> **Answer:** D

### Q6. A route in your app runs a heavy report: complex database queries plus a Node-only PDF library. Your AI proposes the edge runtime for global speed. What is the right call?

- **A.** Use serverless, since it runs with full Node.js support in a single region and suits heavy work and database-driven logic.  ✅
- **B.** Use edge, since near-zero cold starts matter most for long tasks and the restricted runtime will polyfill Node APIs it needs.
- **C.** Use edge, but split the PDF work into client-side JavaScript so the restricted runtime only handles the database queries.
- **D.** Use serverless for the first request and edge for repeat traffic, since Vercel promotes frequently hit routes to the edge.

> **Answer:** A

### Q7. Your AI moved an auth-check API route to the edge runtime, but it queries your Postgres database hosted in a single US region. Users in Asia now report slower responses. Why?

- **A.** Edge runtimes throttle outbound connections to protect shared infrastructure, so any database call gets queued behind others.
- **B.** The edge function runs near each user but still crosses the world to reach the distant database, adding a slow round trip.  ✅
- **C.** Edge functions execute code twice, once at the edge and once at origin, so database routes always pay a duplicated query cost.
- **D.** The restricted edge runtime falls back to serverless mid-request when it sees Node database drivers, doubling cold starts.

> **Answer:** B

### Q8. A deploy just broke checkout for your 10K-user SaaS. Your AI suggests hot-patching the bug on main. What is the fastest recovery path Vercel gives you?

- **A.** Push a revert commit and wait for the pipeline, since Vercel requires a fresh build before production can change versions.
- **B.** Delete the broken deployment from the dashboard, which automatically resurrects the prior build after the cache clears.
- **C.** Promote the previous known-good deployment back to production; deployments are immutable, so it takes seconds with no rebuild.  ✅
- **D.** Restart the production serverless functions from the logs panel, which quietly reloads the last stable code from Vercel's build cache.

> **Answer:** C

### Q9. Your AI opens a pull request with a risky payment flow change. Before it merges, you want to click through the feature against real infrastructure. Where does Vercel give you that?

- **A.** In the Development environment on your machine, since vercel env pull mirrors production data locally for fully realistic testing.
- **B.** On the production domain behind a feature flag, since Vercel dark-launches every PR to a small slice of live traffic first.
- **C.** On the PR's preview deployment, a live URL running Preview environment variables where you review before it hits production.  ✅
- **D.** In the build logs, where Vercel renders screenshots of every changed route so you can approve without visiting any URL.

> **Answer:** C

### Q10. Your team wants a formal staging layer beyond per-PR previews: one stable URL clients can always check, with staging data behind it. What setup matches Vercel's model?

- **A.** Pin a dedicated staging branch with its own domain and its own environment variable values, giving a persistent staging site.  ✅
- **B.** Enable staging mode in the project settings, which clones production nightly into a sandboxed copy on a separate vercel.app subdomain.
- **C.** Point clients at the newest preview URL each week, since preview deployments persist and rotate automatically as PRs merge.
- **D.** Run a second production deploy of the same branch and mark it hidden, so it shares live variables but stays off the domain.

> **Answer:** A

### Q11. Your content site answers on both www.yourdomain.com and the apex with no redirect between them, and rankings are stagnating. What should you direct your AI to fix?

- **A.** Serve both versions but add separate sitemaps for each host, so crawlers index the two variants as intentional mirror sites.
- **B.** Drop the www subdomain entirely from DNS, since search engines penalize any site that resolves on more than one hostname.
- **C.** Add a canonical meta tag on www pointing to itself, which lets both hosts keep serving while ranking signals stay combined.
- **D.** Pick one canonical version, www or apex, and let Vercel redirect the other, because serving both splits your SEO signals.  ✅

> **Answer:** D

### Q12. Twenty minutes after a clean deploy, payments fail in production. Logs show Stripe rejecting charges because the app is sending a test key. The code is unchanged. What class of failure is this?

- **A.** A code bug: the AI hardcoded the test key in a component, and the fix is a source patch followed by a fresh production build.
- **B.** A caching failure: Vercel served a stale build with old credentials, and purging the deployment cache restores the live key.
- **C.** An environment management failure: the key was misscoped, so production is reading a value meant for another environment.  ✅
- **D.** A DNS failure: the payment webhook resolves to the preview URL, so Stripe replies with test-mode responses to production.

> **Answer:** C

### Q13. You direct an AI agent to work across several branches of your Next.js repo connected to Vercel. What rule about the main branch must the agent treat as non-negotiable?

- **A.** Keep main frozen except for monthly release windows, since Vercel batches its production deploys on a fixed monthly schedule anyway.
- **B.** Keep main deployable at all times, because every merge to the production branch goes live and merged effectively means live.  ✅
- **C.** Keep main free of environment variable references, since Vercel only injects variable values into non-production branches.
- **D.** Keep main rebased onto every preview branch daily, since Vercel discards preview deployments that drift from production.

> **Answer:** B

### Q14. Local development keeps failing because your .env file has drifted from what the deployed app actually uses. Your AI wants to copy values from the dashboard by hand. What is the better direction?

- **A.** Run vercel logs to print each variable the deployment read at runtime, then paste the reported values into the local file.
- **B.** Commit the dashboard values into next.config.js so local, preview, and production all read one tracked source of truth.
- **C.** Run vercel env pull, which syncs the project's environment variables from Vercel into a local .env file without hand copying.  ✅
- **D.** Delete the local file entirely, since Next.js fetches environment values from Vercel's API at runtime when none is present locally.

> **Answer:** C

### Q15. This week's deploy shows build time and client bundle size both roughly doubled, though the feature diff looked small. As the reviewer of AI-built code, how should you read this signal?

- **A.** As expected growth: bundles scale with route count, and Vercel's CDN compression makes client size largely irrelevant now.
- **B.** As a red flag that something was added that should not be there, such as a heavy dependency bloating the client bundle.  ✅
- **C.** As a Vercel platform issue: build minutes vary by region and load, so size and duration are not meaningful review inputs.
- **D.** As a sign the framework updated itself: Next.js periodically inlines new runtime features, which doubles output size briefly.

> **Answer:** B

### Q16. Your AI got a failing deploy to pass by setting ignoreBuildErrors and ignoreDuringBuilds in the Next.js config. The build is green and the app loads. How should you rule on this in review?

- **A.** Approve it: those flags only silence editor warnings, and Vercel independently type-checks every production build anyway.
- **B.** Approve it for production but not preview, since preview deployments are where the strict checks deliver the most value.
- **C.** Reject it only if bundle size grew, since lint and type errors have no runtime effect once the final build output is generated.
- **D.** Reject it: ignoring TypeScript and ESLint errors just to force a deploy hides real defects and violates clean build practice.  ✅

> **Answer:** D

### Q17. You are moving a live revenue site's domain to Vercel next week. Your AI proposes simply swapping the A record at the registrar during business hours. What is the flaw you should catch?

- **A.** A records cannot be changed on live domains; you must let the current registration lapse and reregister pointing at Vercel.
- **B.** The plan ignores propagation and TTL; a cutover without accounting for them can take the site dark for hours at peak crawl.  ✅
- **C.** Swapping the A record permanently disables SSL on Vercel, since certificates only provision on full nameserver transfers.
- **D.** The registrar swap is fine, but Vercel requires you to delete the old deployment first so the new domain can attach cleanly.

> **Answer:** B

### Q18. You are auditing runtime choices route by route in an AI-built app. Which workload is the strongest fit for Vercel's edge runtime rather than serverless?

- **A.** A report generator using Node-only libraries, since edge regions each cache the library closer to the requesting user.
- **B.** A single-region database write path, since edge placement compensates for the distance to the data with much faster startup times.
- **C.** Middleware doing auth checks, redirects, and personalization, which runs close to users worldwide with near-zero cold starts.  ✅
- **D.** Any route with heavy sustained traffic, since the edge runtime is a strict superset of serverless with no restrictions.

> **Answer:** C

### Q19. Your AI's pull request shows a passing build and green checks, and it asks you to merge. According to this module's review discipline, what must happen before that merge?

- **A.** Nothing more; a passing Vercel build verifies the feature works, so preview clicks add process without adding real safety.
- **B.** You click through the preview URL as the QA gate, checking the feature and its data in a real deployed context first.  ✅
- **C.** You redeploy production first so the preview and live environments match before comparing the two deployments directly.
- **D.** You ask the AI to self-certify its changes in a comment, which Vercel records as the audit trail for the deployment.

> **Answer:** B

### Q20. You have never opened Vercel's rollback panel, reasoning you will learn it if an outage ever happens. What does this module say about that stance?

- **A.** It is reasonable; rollback flows change often with dashboard updates, so rehearsing early creates outdated muscle memory.
- **B.** It is safe as long as you keep a revert commit script ready, since Git-based recovery is the primary path Vercel supports.
- **C.** It is fine for small apps; rollback rehearsal only pays off once you pass roughly 100K users or multi-region traffic.
- **D.** It is a known pitfall; if the first time you look for the rollback button is an outage, you debug live while users churn.  ✅

> **Answer:** D

### Q21. Your builder asks why Vercel can restore a previous production version in seconds while your old host needed a full redeploy. What property of Vercel deployments explains this?

- **A.** Every previous deployment is kept immutable and ready, so promoting a known-good deploy back to production needs no rebuild.  ✅
- **B.** Vercel keeps a warm standby copy of your Git repository and re-runs the build on much faster dedicated rollback hardware tiers.
- **C.** Production runs two versions at once behind a load balancer, so a rollback just shifts the traffic weighting between them.
- **D.** Vercel snapshots your database alongside each deploy, letting the code and its data revert together in one restore step.

> **Answer:** A

### Q22. Your AI pushes a feature branch and opens a PR against main on a Vercel-connected repo. It also pushes a small commit directly to main. What deployments result?

- **A.** The feature branch generates a preview deployment with its own URL, while the push to main triggers a production deploy.  ✅
- **B.** Both pushes create preview deployments, and production only changes when you press Promote in the Vercel dashboard later.
- **C.** Only the push to main creates any deployment; branch pushes are ignored by Vercel until the pull request gains approval.
- **D.** Both pushes go to production in commit order, since Vercel treats every branch of a connected repo as a production source.

> **Answer:** A

### Q23. A contractor testing a preview URL of your store accidentally placed a real order with a real card charge. What misconfiguration does this module say to look for first?

- **A.** The preview deployment was built from main instead of the feature branch, which automatically inherits production traffic.
- **B.** The contractor used the production domain by mistake, since preview URLs cannot reach live payment providers by design.
- **C.** SSL on the preview URL let the browser trust it like production, so the payment provider processed the charge as live.
- **D.** A live payment key was misscoped into the Preview environment, so preview deploys transacted against the real provider.  ✅

> **Answer:** D

### Q24. You import a monorepo into Vercel and the build fails at once: no Next.js app detected, wrong lockfile, missing pages. The app lives in apps/web. What build setting should your AI check first?

- **A.** The Node.js version pin, since monorepos require the latest LTS runtime before Vercel will even scan any nested directories.
- **B.** The install command, since monorepos need a global flag telling the package manager to hoist the app to the repo root.
- **C.** The root directory setting, which must point at the app's folder in a monorepo so Vercel builds from the correct location.  ✅
- **D.** The output file tracing flag, since Vercel cannot locate build artifacts in a repo containing more than one package.

> **Answer:** C

### Q25. Beyond any single scenario, what is the governing principle Module 6 teaches about deployment for builders directing AI on Vercel?

- **A.** Direct AI to set up the pipeline, then audit it yourself, because automatic deploys make every misconfiguration a live risk.  ✅
- **B.** Choose the edge runtime by default for every route, because global latency wins outweigh any restriction of the runtime.
- **C.** Avoid automatic Git-based deploys in favor of manual promotions, because releases triggered by humans are inherently safer.
- **D.** Delegate environment, domain, and DNS decisions fully to the AI, because Vercel's platform defaults are safe enough without review.

> **Answer:** A


---
_Take it in the browser: https://the-faction.mn.co/posts/106186753_
