---
course: "The Foundation"
module: "Layer 10: Caching & CDN"
lesson: "Layer 10: Caching & CDN — Exam"
type: "course_quiz"
post_id: 102895171
space_id: 23777123
source: "https://the-faction.mn.co/posts/102895171"
updated: "2026-08-21T14:49:48Z"
---

# Layer 10: Caching & CDN — Exam

> Exam for **Layer 10: Caching & CDN** (The Foundation) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. You deploy a CSS fix but users keep seeing the old styling until they hard-refresh. What should you direct your AI tool to change?

- **A.** Direct your AI tool to shorten the cache lifetime to one hour, which guarantees that no visitor is ever served a stale stylesheet again
- **B.** Direct your AI tool to stop caching stylesheets altogether, since correctness matters more than speed and these files are small anyway
- **C.** Direct your AI tool to publish a release notice asking every visitor to hard-refresh, since browsers cannot be told to drop files they cached
- **D.** Direct your AI tool to add content-hashed filenames so that each deploy produces new URLs that no browser can serve from its existing cache  ✅

> **Answer:** D

### Q2. Your app has a product catalog (same for all users) and a user dashboard (personalized). Which page is a good candidate for aggressive caching?

- **A.** The product catalog, because it displays identical content to every visitor and aggressive caching won't risk exposing one user's data to another  ✅
- **B.** Both pages should use the exact same caching rules, since they are served from the same application, the same domain, and the same deployment pipeline
- **C.** The user dashboard, because personalized pages get opened far more frequently than catalog pages and would therefore benefit the most from aggressive caching
- **D.** Neither page should be cached at all, because any form of caching will inevitably end up showing users outdated versions of the page information

> **Answer:** A

### Q3. You run Lighthouse and score 45. What are the first two metrics you should examine to diagnose the issue?

- **A.** The total number of pages on the site and the total number of registered users, since having more pages generally means more for the browser to load first
- **B.** Server CPU utilization percentage and the total count of database queries, since the backend load is what drives the frontend speed
- **C.** The color contrast ratio scores and the overall accessibility rating, since visual design choices have a real impact on how fast a page feels to users
- **D.** Largest Contentful Paint and First Contentful Paint — LCP measures time until the biggest visible element loads, FCP when first content appears  ✅

> **Answer:** D

### Q4. A user visits your app a second time and it loads much faster than the first visit. What explains this improvement?

- **A.** The browser cached static files like CSS, JS, and images during the first visit and loads them from local storage on repeat visits  ✅
- **B.** The user's home internet connection happened to randomly improve between their first visit and their second visit to your site
- **C.** The server hardware warmed up after handling the first request and now processes every subsequent request at a noticeably faster rate than before
- **D.** The database automatically optimized its own query execution plans after it saw the same requests being repeated against the same set of tables

> **Answer:** A

### Q5. Your AI tool deployed your app without cache headers on CSS and JS files. What is the real-world impact on users?

- **A.** No impact at all, because modern browsers automatically cache every static file they encounter regardless of what headers are present on the response
- **B.** Browsers may re-download CSS and JS on every visit, slowing repeat loads. Headers should specify long cache lifetimes with cache-busting filenames  ✅
- **C.** The entire application will crash immediately on load, because a browser cannot actually render any pages without cache headers being present
- **D.** Cache headers only affect image files specifically — CSS and JavaScript files are never cached by any browser, so nothing changes for those two

> **Answer:** B

### Q6. Your app has a site logo, user profile photos, and personalized dashboards. Which of these are static content suitable for CDN caching?

- **A.** Only the site logo is static since it is identical for everyone. Profile photos and dashboard layouts are dynamic, varying per user  ✅
- **B.** All three of the items count as static content and should be cached identically by the CDN using the same aggressive settings for each one of them
- **C.** None of these assets should ever be cached anywhere, because caching any single one of them risks displaying stale content to your users
- **D.** Only plain text content can ever be cached by a CDN — images and layout components are never eligible for any edge caching

> **Answer:** A

### Q7. You are choosing cache lifetimes for your app. The HTML page must reflect content edits within minutes, while your image and script files are given unique fingerprinted names that change whenever their contents change. What should you direct your AI tool to configure?

- **A.** A short lifetime for the HTML page and a long one for the fingerprinted files, because a content change produces a new filename no old cached copy can satisfy  ✅
- **B.** One long lifetime applied uniformly to every file the app serves, because a single consistent rule is what keeps behaviour at the edge predictable and correct
- **C.** A short lifetime on every file the app serves, because any longer setting risks showing outdated content and cancels the benefit fingerprinting was meant to add
- **D.** Caching switched off for the HTML page and a long lifetime elsewhere, because any lifetime above zero stops edits from ever reaching a returning visitor

> **Answer:** A

### Q8. You want to measure your app's speed objectively. Which tool and metric should you prioritize?

- **A.** Google Analytics with bounce rate as the primary metric, since users leaving the site quickly means the pages loaded far too slowly for them
- **B.** Use a physical stopwatch and time how fast each page subjectively feels while you load it a few times on your computer
- **C.** Check the raw server access logs for total requests per minute, since a higher request volume indicates faster server response times
- **D.** Chrome DevTools Lighthouse focusing on LCP — a score under 2.5 seconds is good, over 4 seconds is rated poor performance  ✅

> **Answer:** D

### Q9. Your AI tool used plain img tags for all images. What should you direct it to use instead for better performance?

- **A.** Replace every image with a custom video player component that streams the visual content instead of loading any static image files at all
- **B.** Swap each img tag for a div element that uses a CSS background-image property pointed at exactly the same image source URL
- **C.** Use the Next.js Image component or equivalent framework tool that automatically resizes, converts to WebP, and lazy-loads images  ✅
- **D.** Embed each image inside its own dedicated iframe that loads the file from a completely separate third-party hosting server on another domain

> **Answer:** C

### Q10. Your app uses Vercel. What caching features does a modern deployment platform like Vercel provide out of the box?

- **A.** Database query result caching plus automatic API rate limiting, so that your backend never gets overwhelmed by sudden spikes in traffic
- **B.** CDN distribution across global edge nodes, automatic cache headers on all static assets, and built-in image optimization tools  ✅
- **C.** Built-in user authentication flows and session management, so that you never need to wire up a separate auth service for your application
- **D.** Automated code review that scans every deployment for bugs and performance issues before it ever goes live on the edge

> **Answer:** B

### Q11. Your gallery shows product photos at 400px wide but the originals are 4000px, 5MB files. What pitfall is this?

- **A.** Using far too many distinct colors in the image palette, which inflates each file size well beyond what the format was designed to support
- **B.** Listing too many products on a single gallery page at once, which overwhelms the browser layout engine while it is rendering the grid
- **C.** Serving full-size originals when thumbnails would do — a single unoptimized image can be larger than your entire app's code bundle  ✅
- **D.** Using the wrong file naming convention for product images, which prevents the browser from locating and loading them

> **Answer:** C

### Q12. You deployed to a platform that advertises CDN support and assumed it was active. Users overseas report slow loads. What pitfall is this?

- **A.** You chose the wrong hosting platform entirely and need to migrate the whole application over to a provider that has genuine CDN support
- **B.** Not verifying whether your CDN is actually active — you assumed it was working without ever checking the response headers  ✅
- **C.** Not having enough separate pages on your site for the CDN to distribute across its whole network of edge locations
- **D.** Loading too many custom font files, which are exempt from CDN delivery and must instead come down from the origin server on every visit

> **Answer:** B

### Q13. You cached database queries but users now see outdated prices after sellers update them. What went wrong?

- **A.** The database engine itself is simply too slow at processing write operations and keeps falling behind on recording the sellers' price updates
- **B.** The CDN layer is overriding and replacing the fresh database values with its own cached copy of the original listing prices it stored
- **C.** Caching dynamic data without an invalidation strategy — every cached item needs a clear plan for when and how it gets refreshed  ✅
- **D.** Users just need to clear their browser cookies and local storage to force the app to fetch the latest pricing data again

> **Answer:** C

### Q14. You tested on your MacBook at home and it loaded in under a second. Real users on mobile report 8-second loads. What pitfall is this?

- **A.** The real problem is using a Mac instead of a PC for the development work, since Macs render web pages differently than Windows machines do
- **B.** Your app simply ships too many features for mobile devices to handle, and you need to remove functionality before the speed will improve
- **C.** You do not have enough separate server instances running to handle all of the load from mobile users connecting over slower cellular networks
- **D.** Never measuring load time from real-world conditions — you tested on fast hardware, home WiFi, near the server, missing real user experience  ✅

> **Answer:** D

### Q15. You push a CSS update but users still see the old styling. What caused this?

- **A.** The CSS syntax in your update file is invalid somewhere, so the browser silently rejected it and fell back to the previous working stylesheet
- **B.** The CDN infrastructure itself is broken and is serving corrupted files that do not reflect any of the deployments you pushed recently
- **C.** Deploying without cache-busting — the browser cached old CSS files and the filename did not change, so it served the stale version  ✅
- **D.** Users need to manually update their web browsers to the latest version before the newer CSS features will render correctly

> **Answer:** C

### Q16. Your live app is slow and adding caching now requires major restructuring. What principle does this illustrate?

- **A.** You chose the wrong programming language for this project, and a different language would have shipped with caching already built into it
- **B.** Treating caching as an afterthought instead of a design decision — caching works best when planned into the architecture from day one  ✅
- **C.** You do not have enough developers on the team to implement caching properly across all of the different layers of the application
- **D.** You simply selected the wrong cloud platform and need to migrate to one that includes automatic caching as part of its base infrastructure

> **Answer:** B

### Q17. Before sitting for this exam, what should you do first to verify your app's performance baseline?

- **A.** Ask your AI coding tool to estimate what your Lighthouse score would probably be, based on the codebase that it already knows about
- **B.** Count the total number of pages in your application, since having fewer pages generally means faster performance across the whole site
- **C.** Run Lighthouse on your deployed app and know your actual performance score and LCP time before answering any exam questions  ✅
- **D.** Check your total registered user count first, because a low number of active users means performance is not a concern yet

> **Answer:** C

### Q18. Your CDN dashboard reports a 40 percent cache hit rate on static assets. What does that tell you, and what should you do about it?

- **A.** The CDN is misconfigured and should be switched off, since a hit rate below half adds latency instead of removing it
- **B.** Nothing useful, because the hit rate counts how many visitors returned rather than how well the edge is serving your static files
- **C.** Forty percent is normal and needs no action, since almost every request a site receives is unique to that one visitor
- **D.** Most requests still reach your origin, so review cache headers and asset naming to raise the share served from the edge  ✅

> **Answer:** D

### Q19. How do you confirm your CDN is actively serving content from edge locations near your users?

- **A.** The hosting platform's marketing page says a CDN is included with your plan, which is sufficient confirmation that it is working properly
- **B.** The app loads fast when you test it from your own home network, which proves the CDN is distributing content to edge locations globally
- **C.** You paid for the CDN add-on plan in your hosting dashboard, so it must already be active and serving from edge nodes
- **D.** Response headers show CDN cache status indicators like cache-hit and edge location identifiers, confirming active edge serving  ✅

> **Answer:** D

### Q20. Your static assets have no cache headers configured. What happens to performance and what should you set up?

- **A.** No impact at all — every browser automatically caches every static asset using sensible defaults even when no explicit headers are set
- **B.** Only font files require explicit cache headers; other static assets like CSS and JS are cached automatically anyway
- **C.** Browsers may re-download assets on every visit, wasting bandwidth. Configure cache headers with long lifetimes for static files  ✅
- **D.** Cache headers are only necessary for mobile browsers — desktop browsers handle their caching automatically without any configuration

> **Answer:** C

### Q21. Should a shopping cart page be cached the same way as the About page?

- **A.** Yes, all pages should use identical caching rules, since they are part of the same application and share the same underlying infrastructure
- **B.** No — About is static content, the same for everyone, and can be cached aggressively. Cart is dynamic, per-user, and needs careful caching  ✅
- **C.** Neither page should be cached at all, because caching any page whatsoever risks showing stale or incorrect information to your visitors
- **D.** Yes, if both of the pages share the same layout template they should use identical caching rules, since the underlying structure is the same

> **Answer:** B

### Q22. You have only tested load time from your laptop near the server. Why is this insufficient for judging real performance?

- **A.** Real users connect from different continents, on varying connection speeds and devices — local testing misses all of these conditions  ✅
- **B.** You should also test from your phone while it is connected to your home WiFi network, in order to cover the mobile use case properly as well
- **C.** Local testing from your own laptop is perfectly sufficient, as long as your internet connection is a standard home broadband plan
- **D.** You should test at different times of day from the same location, to see whether the server load fluctuates during the peak usage hours

> **Answer:** A

### Q23. Your app takes 4 seconds to load. Lighthouse flags images as the biggest issue. What three things should you direct your AI tool to fix?

- **A.** Direct your AI tool to convert images to WebP, resize to match display dimensions, and add lazy loading below the fold  ✅
- **B.** Rewrite the entire backend in a faster language, add more server memory, and migrate to a completely different database system
- **C.** Remove all of the images from the application entirely so that the page has nothing heavy to load on any visit
- **D.** Relocate your server physically closer to your own location so that your local testing environment loads faster

> **Answer:** A

### Q24. You want to verify whether your app's static files are being cached by the browser instead of re-downloaded every visit. Where do you check?

- **A.** Open your database admin panel and carefully search through the query logs for any repeated or duplicate data requests
- **B.** Open Chrome DevTools Network tab, reload the page, and look for '(from cache)' or '304 Not Modified' status codes to confirm caching  ✅
- **C.** Send out a survey to all your users asking them whether the site subjectively feels faster on their second visit
- **D.** Review your cloud hosting invoice to check and see whether your monthly bandwidth charges have decreased over time

> **Answer:** B

### Q25. Your app is on Vercel. A user in Australia reports slow loads. How do you verify whether the CDN is serving from a nearby edge server?

- **A.** Check HTTP response headers for CDN indicators like edge location or cache-hit status, confirming files serve from nearby nodes  ✅
- **B.** Ask the Australian user to try switching to a completely different browser to see if performance improves at all
- **C.** Tell the user to clear their entire browser cache and all local storage data, then try reloading the page again
- **D.** Migrate your entire application server infrastructure to an Australian data center to reduce latency for that user

> **Answer:** A


---
_Take it in the browser: https://the-faction.mn.co/posts/102895171_
