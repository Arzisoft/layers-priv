---
course: "The Mastery"
module: "Module 5 — SEO Metadata and Performance"
lesson: "Module 5: SEO Metadata and Performance — Exam"
type: "course_quiz"
post_id: 106186617
space_id: 24191170
source: "https://the-faction.mn.co/posts/106186617"
updated: "2026-08-21T15:19:04Z"
---

# Module 5: SEO Metadata and Performance — Exam

> Exam for **Module 5 — SEO Metadata and Performance** (The Mastery) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. A builder's AI created a static About page and a blog route whose titles come from fetched posts. The builder asks when a static metadata export is enough. What should guide the choice?

- **A.** Always use generateMetadata everywhere, since it handles both static and dynamic cases and keeps every route consistent.
- **B.** Use the static metadata export when values are fixed at authoring time, and generateMetadata when titles depend on fetched data.  ✅
- **C.** Static exports are only allowed in layouts, so individual pages must use generateMetadata regardless of their content.
- **D.** The choice depends on rendering mode: static exports work only on statically generated pages, never server rendered ones.

> **Answer:** B

### Q2. Your AI set a title template of '%s | LaunchPad' in the root layout, and the pricing page exports the title 'Pricing'. A builder reviewing search listings wants to know what crawlers will actually see. What renders?

- **A.** The template is ignored because page titles always override layout metadata completely, so the tab shows only 'Pricing'.
- **B.** Both titles render as separate head tags, and search engines choose whichever title they judge more relevant to the query.
- **C.** The root layout title wins, so every route displays just 'LaunchPad' until the template is removed from the layout.
- **D.** The page value fills the template placeholder, so the route renders 'Pricing | LaunchPad' with the layout as the suffix.  ✅

> **Answer:** D

### Q3. A founder shares her new landing page on LinkedIn and the preview shows a bare gray link with no image. Her AI insists the page has a title and description. What is the most likely cause?

- **A.** The page is missing a canonical link tag, which social platforms require before they will render any rich preview card for a link.
- **B.** Social crawlers cannot read server rendered head tags, so the site needs a client script that injects preview markup.
- **C.** The sitemap does not list the landing page yet, and platforms only build preview cards for URLs found in a sitemap.
- **D.** The page has no og:image tag, so the platform has no picture to display and falls back to a bare link with poor click-through.  ✅

> **Answer:** D

### Q4. A builder migrating a content site from a client rendered React SPA asks why the Next.js Metadata API matters for pages that need to rank in search. What is the key advantage?

- **A.** Next.js renders the head tags on the server, so crawlers see complete titles and descriptions without running JavaScript.  ✅
- **B.** The Metadata API submits every page directly to search engines, so new routes get indexed without waiting for a crawl.
- **C.** It compresses all head tags into a single meta element, shrinking page weight enough to improve rankings by itself.
- **D.** It automatically rewrites page titles using high volume keywords pulled from live search trend data during each production build.

> **Answer:** A

### Q5. An AI built a store with a thousand product pages that all share one hardcoded title. The builder wants unique titles and Open Graph images per product without hand writing head tags. What direction is correct?

- **A.** Add a generateMetadata function to the product route that fetches the product data and returns per-item titles and images.  ✅
- **B.** Export one static metadata object per product in a large central config file, then import the matching entry into every product page.
- **C.** Add client side JavaScript that rewrites document.title after each product page finishes loading data in the browser.
- **D.** Move all product titles into the root layout metadata so each child route automatically inherits its own unique entry.

> **Answer:** A

### Q6. A builder's recipe site ranks, but its listings are plain blue links while a competitor's show star ratings and rich article cards. The builder asks the AI what is missing. What explains the difference?

- **A.** The competitor pays for enhanced listings through search advertising, and rich formatting is reserved for sponsored results.
- **B.** The competitor's higher Core Web Vitals scores unlock rich formatting, which Google grants only to fast loading pages.
- **C.** The competitor publishes JSON-LD structured data describing each page, making it eligible for rich results like ratings.  ✅
- **D.** The competitor writes more descriptive meta descriptions, which Google converts into star ratings when they mention reviews.

> **Answer:** C

### Q7. An AI hand typed a JSON-LD block for an article page, copying the headline into the script manually. The builder worries about upkeep as content changes over time. What is the right direction to give?

- **A.** Move the JSON-LD into a static file in the public folder so it stays stable even when the article content is edited later.
- **B.** Render the JSON-LD inside the page component, serialized from the same data source as the content so it never drifts.  ✅
- **C.** Have the AI regenerate the JSON-LD by hand after each article edit, and add a reminder to the deployment checklist.
- **D.** Remove the JSON-LD entirely, since search engines now infer structured data from page markup and the script adds risk.

> **Answer:** B

### Q8. A builder is directing AI to add structured data across a site with blog posts, a product catalog, and a company about page. Which schema.org mapping should the review approve?

- **A.** Article schema for the blog posts, Product schema for catalog items, and Organization schema for the company about page.  ✅
- **B.** WebPage schema for every route, since one generic type covers all page kinds and avoids any schema validation errors across the site.
- **C.** FAQ schema on every page, because FAQ markup earns the most rich result space regardless of the actual content type.
- **D.** Product schema everywhere, since Google prioritizes commerce markup and treats articles as products without a price.

> **Answer:** A

### Q9. A publication adds several posts a day, and the builder wants each new article in the sitemap without manual steps. The AI proposed a hand maintained XML file. What should the builder direct instead?

- **A.** Keep the XML file but add a weekly calendar reminder to append any new article URLs before each scheduled deployment.
- **B.** Skip the sitemap entirely, since search engines discover new articles through internal links quickly enough for most sites.
- **C.** Generate the sitemap in the browser with client JavaScript so it always reflects whatever posts users can currently see.
- **D.** Use sitemap.ts to build the URL list in code, pulling article routes from the data source so new posts appear automatically.  ✅

> **Answer:** D

### Q10. Weeks after launch, a marketing site has zero search impressions. The builder audits and finds robots.txt contains a disallow-all rule. What most likely happened, and why does it matter?

- **A.** A disallow-all rule only affects image crawling, so the missing impressions must come from thin content on key pages.
- **B.** The AI carried a staging disallow-all config into production, deindexing the entire site, and recovery can take weeks.  ✅
- **C.** Search engines ignore robots.txt for small sites, so the file is harmless and the real issue is a missing analytics tag.
- **D.** robots.txt only matters for paid search placements, so organic listings are unaffected and the sitemap needs review.

> **Answer:** B

### Q11. Lighthouse reports that a blog's main hero content takes 4.8 seconds to appear, and the builder needs to explain the failing metric to a client. Which statement is accurate?

- **A.** That reflects CLS, which measures the load time of the largest page element and should stay under 2.5 for a passing score.
- **B.** That reflects FID, which measures how quickly the main content paints and should stay under 0.1 seconds to pass.
- **C.** That reflects LCP, which measures how fast the main content appears, and it should be under 2.5 seconds to pass.  ✅
- **D.** That reflects INP, which measures the total page weight expressed in seconds and has no fixed passing threshold.

> **Answer:** C

### Q12. Users of a dashboard complain that buttons jump just as they tap them, because content shifts while the page loads. Which Core Web Vital captures this problem, and what is its passing threshold?

- **A.** LCP captures all layout movement during page load, and the page passes as long as all shifting finishes within 2.5 seconds.
- **B.** CLS, Cumulative Layout Shift, measures how much the page jumps while loading, and it should stay under 0.1 to pass.  ✅
- **C.** FID measures visual stability after the first paint, and pages pass when the shift score stays under 2.5 overall.
- **D.** INP measures the cumulative movement of images only, so shifts caused by text are excluded from the passing score.

> **Answer:** B

### Q13. A builder reviewing a Core Web Vitals report sees responsiveness metrics and asks the AI to explain FID and its modern successor. Which explanation is correct?

- **A.** FID measures how fast custom fonts load, and its successor INP measures image paint time across the whole session.
- **B.** FID measures layout stability on first scroll, and INP replaced it because scrolling metrics proved too inconsistent.
- **C.** FID measures the delay before the page responds to a user's first interaction, and INP is its modern successor.  ✅
- **D.** FID measures the full page load time, and INP is a simplified version that tracks only the initial HTML response.

> **Answer:** C

### Q14. An AI built a gallery with plain img tags, and content jumps downward as each photo loads. The builder asks why switching to next/image fixes the shift. What is the mechanism?

- **A.** next/image reserves layout space for each image before it loads, so surrounding content never moves when photos arrive.  ✅
- **B.** next/image loads every photo before showing any content, so the page appears only after all images have arrived.
- **C.** next/image converts each photo into an inline CSS background image, which browsers exempt from layout shift measurement rules.
- **D.** next/image delays all rendering until the browser goes idle, which prevents shift by pausing layout work entirely.

> **Answer:** A

### Q15. A landing page's hero image is the largest element on screen, but Lighthouse flags a slow LCP because the image lazy loads. What should the builder direct the AI to change?

- **A.** Remove next/image from the hero and use a plain img tag, since the optimization pipeline is what delays the paint.
- **B.** Add the priority prop to the hero image so it loads eagerly instead of lazily, protecting the LCP element's paint.  ✅
- **C.** Shrink the hero to a small thumbnail so it is no longer the largest element and LCP measures the headline instead.
- **D.** Move the hero image below the fold so lazy loading becomes correct behavior and the metric no longer applies to it.

> **Answer:** B

### Q16. A builder notices text flashing and shifting as a custom Google font loads from an external request on every page view. What does next/font do that addresses this?

- **A.** It swaps custom fonts for system fonts on slow connections, sacrificing branding whenever the network quality dips.
- **B.** It self-hosts the font at build time, eliminating the render-blocking external request and the font-swap layout shift.  ✅
- **C.** It inlines the entire font file into every HTML response, trading much larger pages for stable text rendering.
- **D.** It preloads fonts through a third party CDN at runtime, which speeds up the request but keeps the external dependency alive.

> **Answer:** B

### Q17. An app feels sluggish on first load, and the builder suspects the AI shipped far too much JavaScript but cannot tell what is inside the bundle. Which toolkit step fits this situation?

- **A.** Run the Google Rich Results Test, which lists every JavaScript dependency alongside its structured data validation output.
- **B.** Check Search Console, which reports full bundle composition for any site verified with a submitted production sitemap.
- **C.** Run next/font analysis, which reports each library's byte size as part of its build time font subsetting pass.
- **D.** Run @next/bundle-analyzer to visualize what is in the JavaScript bundles and spot oversized libraries the AI imported.  ✅

> **Answer:** D

### Q18. Bundle analysis shows a 300 KB charting library loading on every page, though only the dashboard uses it. Landing page visitors pay the cost too. What should the builder direct the AI to do?

- **A.** Move the chart code into the root layout so it is cached once globally and no individual route pays for it again.
- **B.** Inline the charting library into the HTML response so it arrives with the page instead of as a separate download.
- **C.** Load the chart component with a dynamic import so the library splits out of the initial bundle and loads on demand.  ✅
- **D.** Rewrite the charts as static screenshots for everyone, since interactive charts cannot leave the main bundle.

> **Answer:** C

### Q19. Before calling a build done, a builder wants a concrete audit that scores Core Web Vitals and lists specific failures to hand back to the AI. Which tool fits this step of the workflow?

- **A.** The Google Rich Results Test, which measures LCP and CLS on every page and produces prioritized performance fixes.
- **B.** @next/bundle-analyzer, which scores each route's Core Web Vitals and flags any images missing the priority prop for LCP.
- **C.** Lighthouse or PageSpeed Insights, Google's free auditing tools that score Core Web Vitals and list specific failures.  ✅
- **D.** The sitemap.ts build log, which reports each route's performance score alongside its inclusion in the sitemap file.

> **Answer:** C

### Q20. An AI generated Product JSON-LD for a store, and the builder wants confirmation the markup is valid and eligible for enhanced listings before shipping. What is the right verification step?

- **A.** Run Lighthouse, which validates schema.org syntax as part of its accessibility scoring and flags invalid markup.
- **B.** Share a product URL on social media and check whether the preview card renders, which proves the schema is valid.
- **C.** Open the page in a browser and confirm the script tag appears in the source, which guarantees rich result eligibility.
- **D.** Run the Google Rich Results Test, the validator that confirms JSON-LD is correct and eligible for rich listings.  ✅

> **Answer:** D

### Q21. A ten page services site gets impressions only on its homepage, and every search listing shows the identical title and description. What should the builder's audit conclude?

- **A.** Every route inherits the root layout's generic metadata, so nothing ranks for specific queries until pages get unique tags.  ✅
- **B.** Search engines throttle new domains to one ranking page, so the pattern is normal and resolves on its own with age.
- **C.** Identical listings mean the sitemap submitted duplicate URLs, so regenerating the XML file will restore the rankings.
- **D.** The site needs more backlinks, since titles and descriptions have no influence on which queries a page can rank for.

> **Answer:** A

### Q22. Reviewing an AI built marketing page, a builder finds plain img tags used for every visual, including the hero. What metric damage should the builder predict from this single choice?

- **A.** Only SEO metadata suffers, because plain img tags block crawlers from reading alt text while leaving speed untouched.
- **B.** Nothing measurable changes, since browsers optimize images natively and next/image adds only developer convenience.
- **C.** Inflated LCP from unoptimized eagerly loaded images plus layout shift, since no space is reserved before they load.  ✅
- **D.** Only the bundle size grows, because plain img tags force image bytes into the JavaScript bundle sent to the client.

> **Answer:** C

### Q23. Months after launch, a site's articles were rewritten but their hand typed JSON-LD still describes the old headlines, and rich results disappeared. What lesson should the builder take?

- **A.** Structured data should only be updated quarterly, since frequent JSON-LD changes trigger spam checks in search engines.
- **B.** Rich results rotate between competing sites automatically, so the loss is unrelated to the stale structured data.
- **C.** JSON-LD belongs in a separate CMS field that editors must update manually whenever they change an article's content.
- **D.** Generate JSON-LD from the same data source as the page content so it can never drift out of sync as content changes.  ✅

> **Answer:** D

### Q24. A builder is writing the first prompt for a new SaaS marketing site and debates whether to mention SEO and performance now or clean them up before launch. What does this module advise?

- **A.** Put the metadata strategy and performance budget in the first prompt, since these fixes are cheap early and costly later.  ✅
- **B.** Wait until after launch, because real user traffic data is required before any meaningful optimization work can start.
- **C.** Handle performance first and defer all metadata until the design is final, since head tags depend on the visuals.
- **D.** Leave both to the AI's defaults, since Next.js ships with complete SEO and performance coverage out of the box.

> **Answer:** A

### Q25. Which statement best captures the governing principle of Module 5, SEO, Metadata and Performance?

- **A.** SEO and performance are architecture decisions specified from the first prompt, not polish added at the end of a build.  ✅
- **B.** Search rankings are earned mainly through content volume, so publishing cadence outweighs technical implementation.
- **C.** Performance work belongs to hosting providers, so builders should pick platforms rather than direct optimizations.
- **D.** Metadata is a compliance formality for crawlers, separate from the user experience concerns that drive conversions.

> **Answer:** A


---
_Take it in the browser: https://the-faction.mn.co/posts/106186617_
