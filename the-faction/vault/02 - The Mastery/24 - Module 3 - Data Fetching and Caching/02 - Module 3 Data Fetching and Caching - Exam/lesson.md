---
course: "The Mastery"
module: "Module 3 — Data Fetching and Caching"
lesson: "Module 3: Data Fetching and Caching — Exam"
type: "course_quiz"
post_id: 106186087
space_id: 24191170
source: "https://the-faction.mn.co/posts/106186087"
updated: "2026-08-21T15:18:25Z"
---

# Module 3: Data Fetching and Caching — Exam

> Exam for **Module 3 — Data Fetching and Caching** (The Mastery) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. Your AI builds a sales dashboard page that fetches data in useEffect from a client component, adding spinners and an exposed endpoint. Reviewing the App Router output, what pattern should you direct instead?

- **A.** Keep the useEffect fetch but add a suspense boundary and a loading spinner so users can see progress while the browser loads the data
- **B.** Move the logic into a dedicated API route and have the client call it, since endpoints are the standard fetching layer
- **C.** Wrap the client fetch in a browser caching library so repeat visits render instantly from memory instead of the network
- **D.** Fetch directly inside the server component with async and await, so no endpoint is exposed and nothing refetches in the browser  ✅

> **Answer:** D

### Q2. An AI-built content site hammers the database on every page load in production even though the pages look perfectly cacheable. What default fetch behavior in recent Next.js explains this?

- **A.** fetch responses are cached per user session by default, so heavy database load means the session store is misconfigured
- **B.** fetch caches automatically whenever a route is static, so these routes must have been accidentally forced dynamic somewhere
- **C.** fetch caches everything by default in all versions, so the load has to come from client components refetching on every navigation
- **D.** Recent versions leave fetch uncached by default, so every call needs an explicit caching choice or it hits the source each time  ✅

> **Answer:** D

### Q3. A docs site calls a reference API whose content changes only at release time, yet your AI left the fetch options blank and every page view hits the API. What do you direct it to add?

- **A.** cache: 'force-cache', so the result is stored and reused across requests instead of hitting the reference API on every view  ✅
- **B.** cache: 'no-store', so each request is fresh, trusting the framework to deduplicate identical calls within a single render pass
- **C.** next: { revalidate: 0 }, so the response caches permanently without any background refresh work happening on the server
- **D.** Nothing at all, since recent Next.js already stores every successful response in the shared data cache automatically

> **Answer:** A

### Q4. A storefront must show a live inventory count that can change between any two requests, but the AI cached the fetch for sixty seconds and shoppers see sold-out items as available. What fix do you specify?

- **A.** Shorten the revalidate window to five seconds, which keeps the cache while making the staleness too brief for shoppers to notice
- **B.** Add a tag to the fetch and call revalidateTag on a timer so the count refreshes in the background every few seconds
- **C.** Set cache: 'no-store' on that fetch so it runs fresh on every request and a stored count is never served to a shopper  ✅
- **D.** Mark the layout with dynamic = 'force-static' so the framework recomputes the inventory number during each background rebuild

> **Answer:** C

### Q5. A pricing page pulls rates from a billing API that updates about once an hour. You want cached speed but no more than an hour of staleness. Which fetch option do you specify to your AI?

- **A.** next: { revalidate: 3600 }, so the response is cached and refreshed after an hour, balancing speed with acceptable staleness  ✅
- **B.** cache: 'no-store', so rates are always live, accepting per-request rendering because pricing can never be served stale to anyone
- **C.** cache: 'force-cache', so the response is stored until the next deployment picks up whatever the billing API returns
- **D.** next: { revalidate: 60 } inside the client component, so the browser polls the billing API for rate changes every minute

> **Answer:** A

### Q6. A page you expected to be static is rendering on every request in production. During your audit of the AI's code, which finding would explain the route being pushed dynamic?

- **A.** The page imports a client component somewhere in its tree, which always forces the entire route to render per request
- **B.** The page exports metadata generated at build time, which the framework treats as a per-request personalization signal
- **C.** The route reads cookies, headers, or searchParams, or performs an uncached fetch, any of which forces per-request rendering  ✅
- **D.** The page lives outside the app directory, so it falls back to legacy pages behavior and loses all static optimization entirely

> **Answer:** C

### Q7. Your marketing site's landing pages, docs, and blog posts show identical content to every visitor, and organic search is the growth channel. Which rendering mode do you direct your AI to use?

- **A.** Dynamic rendering, so each crawler visit gets a freshly rendered page, which search engines reward with better rankings
- **B.** Static rendering, so pages are built once and served from the CDN, giving the fast loads that content and SEO depend on  ✅
- **C.** Client-side rendering with a fast skeleton, since crawlers now execute JavaScript and users see an instant shell first
- **D.** ISR with a sixty second window, because every route should regenerate constantly regardless of how often content changes

> **Answer:** B

### Q8. You are speccing a logged-in account dashboard that shows each user's own billing and usage data. How should you tell your AI to render it?

- **A.** Statically with a long revalidate window, since dashboards are read far more often than the underlying data ever changes
- **B.** With ISR, so each user's dashboard is prebuilt in the background and served instantly from the shared CDN cache layer
- **C.** Statically at build time for known users, falling back to dynamic rendering only for accounts created after the deploy
- **D.** Dynamically per request with uncached data, since personalized responses must never be stored and served across users  ✅

> **Answer:** D

### Q9. A content site shows product prices inside articles, and readers report prices staying stale for days after edits. You want static speed but updates within minutes, without redeploying. What do you direct?

- **A.** Force the routes dynamic so every article renders per request, since correctness has to outweigh any caching benefit here
- **B.** Trigger a full site redeploy from the CMS on every edit so the static build always reflects the latest published data
- **C.** Use ISR with a short revalidation window so articles stay static and fast but rebuild in the background after each edit  ✅
- **D.** Move price display into a client component that fetches on mount, keeping articles static while prices load in the browser afterward

> **Answer:** C

### Q10. A blog uses ISR with a five minute window. An author edits a post, and a visitor arrives one minute after the window expires. What do you expect that visitor to experience while regeneration happens?

- **A.** The visitor waits on a blocking request while the page rebuilds, since expired ISR pages render synchronously on demand
- **B.** The visitor gets a 404 until regeneration completes, because the expired page is evicted from the cache immediately
- **C.** The visitor sees a loading skeleton streamed from the server until the regenerated page finishes building and hydrates
- **D.** The visitor is served the previous static page while the new version builds in the background, then later requests get it  ✅

> **Answer:** D

### Q11. An AI-built dashboard awaits a user query, then a metrics call, then a notifications call, each from a different service and none depending on another. Load time is 900ms though no call exceeds 300ms. What is wrong?

- **A.** The sequential awaits form a waterfall, so each independent fetch waits for the previous one instead of starting together  ✅
- **B.** The server is cold starting between the awaits, so the fix is raising memory allocation to keep the function warm longer
- **C.** The fetches are uncached, so the fix is adding force-cache to each call and letting stored responses hide all the latency
- **D.** Server components cannot issue more than one network call per render pass, so the data needs to move into an API route

> **Answer:** A

### Q12. You spot three independent fetches awaited one after another in AI output for a reports page. What fix do you direct, and what latency should you expect afterward?

- **A.** Start them together with Promise.all, so the total wait drops to roughly the slowest single request instead of the sum  ✅
- **B.** Move the two slower fetches into an API route so the network hops overlap, leaving the page to await only one endpoint
- **C.** Cache the first fetch with force-cache so the remaining two start earlier, cutting the chain down to two sequential steps
- **D.** Wrap each await in its own suspense boundary so the framework is able to reorder the requests by measured response time

> **Answer:** A

### Q13. A CMS update changes an author bio that appears on dozens of article pages, each fetching it with a shared 'author' tag. Which invalidation call do you direct after the write?

- **A.** revalidatePath on the author's profile route, since path invalidation cascades to any page embedding that same data
- **B.** revalidatePath('/') so the entire cache refreshes at once and nothing that displays the bio can possibly remain stale
- **C.** Set cache: 'no-store' on the bio fetch so every page rereads it from then on and no invalidation call is needed
- **D.** revalidateTag('author') so every fetch labeled with that tag refreshes, no matter which routes consume the data  ✅

> **Answer:** D

### Q14. You are writing the prompt for a product catalog build and want cache invalidation to stay precise later. What do you tell the AI to do when it creates each fetch?

- **A.** Set every fetch to no-store now, since precision matters less when nothing is cached and invalidation never becomes necessary
- **B.** Give every fetch the same global tag so one revalidateTag call anywhere always brings the whole site back to fresh data
- **C.** Tag each fetch by the data it loads so later invalidation can target exactly the affected entries instead of whole routes  ✅
- **D.** Skip tags and rely on revalidatePath, since route level invalidation is the framework's recommended precision mechanism

> **Answer:** C

### Q15. An editor fixes a typo in one article and the CMS fires a webhook. The AI's handler currently redeploys the whole site. You want only that article's cached page refreshed. What do you direct?

- **A.** Call revalidateTag with the site-wide content tag so every cached fetch refreshes and the typo cannot persist anywhere on the site
- **B.** Call revalidatePath with that article's route so only the affected page refreshes and other cached pages stay untouched  ✅
- **C.** Set the article fetch to no-store going forward, since content that editors can freely change should never be cached at all
- **D.** Lower the site's ISR window to ten seconds so typo fixes propagate quickly without any webhook handling code at all

> **Answer:** B

### Q16. During review you find the AI created an API route for product data, and the product page's server component fetches from that internal route. What is your call as the builder?

- **A.** Keep it, since routing reads through your own API layer centralizes validation and is the pattern the App Router docs recommend
- **B.** Remove the hop and fetch the data directly in the server component, since the internal route adds latency and duplicate code  ✅
- **C.** Keep the route but add force-cache on the internal fetch so the extra network hop is only paid on the very first request
- **D.** Convert the page to a client component so the API route is doing real work instead of being wrapped by the server layer

> **Answer:** B

### Q17. Planning a build, you must decide which data needs API routes and which should be fetched directly. What ownership rule do you give your AI?

- **A.** Build API routes for everything, since a uniform endpoint layer keeps fetching consistent for your pages and partners alike
- **B.** Fetch directly everywhere, since App Router projects should never expose API routes once server components can query data
- **C.** Fetch directly when your own pages consume the data; save API routes for external clients, webhooks, and browser-side calls  ✅
- **D.** Split it by table: reads go through server components while writes always go through API routes so they stay auditable

> **Answer:** C

### Q18. After a small AI change, your entire content site stopped serving static pages and every route renders per request. The change touched only the shared root layout. What likely happened?

- **A.** The layout now calls cookies() or headers(), which silently forces every route beneath it to render on every request  ✅
- **B.** The layout imports a client component, and any client boundary in a layout converts descendant routes to dynamic rendering
- **C.** The layout added metadata exports, which move rendering to request time so titles can reflect the latest content
- **D.** The layout added a database query, and any direct database access in a layout disables static generation for the tree

> **Answer:** A

### Q19. Support tickets say logged-in users of your AI-built SaaS occasionally see another customer's account dashboard. What is the most likely cause and the right framing for it?

- **A.** A session bug in the auth library is mixing tokens; treat it as a vendor issue and wait on an upstream patch before acting
- **B.** The CDN is misrouting requests between regions; treat it as an infrastructure hiccup and add a cache busting query string
- **C.** A personalized response was cached and served across users; treat it as a security incident and make the route uncached  ✅
- **D.** Users are sharing sign-in links that carry session state; treat it as user error and add a warning to the login screen

> **Answer:** C

### Q20. You notice the AI's CMS webhook handler calls revalidatePath('/') after every minor content edit. Why do you flag this in your review?

- **A.** Root revalidation only clears the homepage, so nested article routes keep serving stale content until their own windows expire
- **B.** It wipes far more cache than needed, causing rebuild storms after each small update; scope invalidation with tags or exact paths  ✅
- **C.** revalidatePath cannot be called from webhook handlers, so the calls silently fail and nothing ever actually refreshes
- **D.** Path revalidation is deprecated in favor of tags, so the handler will stop working on the next framework major version

> **Answer:** B

### Q21. You want the fastest possible review checkpoint for how each AI-built page renders, without tracing every fetch call in the codebase. Where do you look first?

- **A.** The route segment config exports, like dynamic = 'force-static' and revalidate = 60, declared at the top of each page file  ✅
- **B.** The build output logs, since only a production compile reveals the final rendering mode the framework actually selected
- **C.** The network tab in devtools, where cached routes are distinguishable by response headers on first and on repeat loads
- **D.** The middleware file, since every rendering decision in the App Router is registered there centrally for the application

> **Answer:** A

### Q22. Your app serves 10K daily users, and serverless bills keep climbing while the database strains under load. What does a solid caching strategy change about this picture?

- **A.** Most requests never touch the database, so the app runs on a fraction of the compute and rides out traffic spikes safely  ✅
- **B.** Compute costs shift from the database to the CDN tier, so total spend stays similar while response times get better
- **C.** It mostly improves developer experience; production costs depend on user count, which a caching layer does not actually change
- **D.** The database load moves to build time instead, so bills fall only if the team also reduces its deployment frequency

> **Answer:** A

### Q23. You are auditing AI-generated code before launch and know caching mistakes are invisible in development. What is the highest value check to run on every fetch call?

- **A.** Confirm each fetch has a try catch block, since silent network failures are the main way stale data reaches production users
- **B.** Confirm each fetch sets explicit cache or revalidate options, since a missing option signals an unexamined default choice  ✅
- **C.** Confirm each fetch runs inside useEffect so the browser controls freshness and the server never stores a stale response
- **D.** Confirm each fetch targets an internal API route, since direct external calls from components cannot be cached at all

> **Answer:** B

### Q24. A storefront has thousands of product pages; prices change a few times a day and organic search drives most sales. Which rendering strategy do you specify to your AI?

- **A.** Dynamic rendering for the whole catalog, since prices that change at all can never be served safely from any cached page
- **B.** Full static builds with a redeploy for each price change, since deploys are the only fully reliable invalidation signal
- **C.** Client-side fetching for prices on a static shell, so crawlers index the shell while browsers load the current prices
- **D.** ISR with a modest revalidation window, so pages stay prebuilt and indexable while price edits appear within minutes  ✅

> **Answer:** D

### Q25. Which statement best captures the governing principle of Module 3, Data Fetching and Caching?

- **A.** Cache everything as aggressively as possible, because compute savings outweigh occasional staleness in nearly every app
- **B.** Every fetch and route needs a deliberate, explicit freshness decision, specified up front and audited before production  ✅
- **C.** Prefer dynamic rendering by default, because correct data always matters more than the speed a CDN can ever provide
- **D.** Let the framework's defaults decide caching, because Next.js chooses the optimal strategy better than builders can

> **Answer:** B


---
_Take it in the browser: https://the-faction.mn.co/posts/106186087_
