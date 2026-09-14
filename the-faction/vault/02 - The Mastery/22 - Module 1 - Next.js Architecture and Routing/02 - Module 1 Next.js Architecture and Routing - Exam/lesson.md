---
course: "The Mastery"
module: "Module 1 — Next.js Architecture and Routing"
lesson: "Module 1: Next.js Architecture and Routing — Exam"
type: "course_quiz"
post_id: 106185663
space_id: 24191170
source: "https://the-faction.mn.co/posts/106185663"
updated: "2026-08-21T15:17:22Z"
---

# Module 1: Next.js Architecture and Routing — Exam

> Exam for **Module 1 — Next.js Architecture and Routing** (The Mastery) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. A builder reviews an AI-scaffolded SaaS dashboard and finds the folder app/dashboard/settings containing a page.tsx file. What does this structure produce in the running app?

- **A.** A component library entry that must be registered in a central routes config file before any URL will render it
- **B.** The URL /app/dashboard/settings, because every folder in the project tree, including app, becomes a URL segment
- **C.** The URL /dashboard/settings, rendered by that page.tsx, because folders define routes and page.tsx defines what renders  ✅
- **D.** The URL /settings only, because Next.js flattens nested folders and uses just the deepest folder name for the final route

> **Answer:** C

### Q2. A builder directs AI to add a blog to a content site that needs to rank. The AI creates app/blog/[slug]/page.tsx. What does the square bracket folder do?

- **A.** It creates a dynamic segment, so that single page.tsx handles every blog post URL, with the slug value available to the page  ✅
- **B.** It marks the folder as a private implementation detail that Next.js excludes from routing until the brackets are removed
- **C.** It creates a catch-all route that also matches /blog itself plus any depth of nested paths beneath every blog post URL
- **D.** It tells Next.js to statically generate one HTML file named [slug] that client-side JavaScript rewrites per post at runtime on load

> **Answer:** A

### Q3. Reviewing an AI-built SaaS dashboard, a builder finds a layout.tsx inside app/dashboard. What behavior should the builder expect from this file?

- **A.** It replaces the root layout entirely for dashboard routes, so the HTML shell and fonts must be redeclared inside it
- **B.** It wraps every page beneath app/dashboard in the tree, nesting automatically inside the root layout above it  ✅
- **C.** It renders only on /dashboard itself, and each deeper settings or billing page must import it manually to share the sidebar
- **D.** It applies globally to every route in the app, because Next.js merges all layout files into one shared wrapper at build

> **Answer:** B

### Q4. A builder's app serving 10K daily users shows a blank area while slow data loads on the reports route. Which fix uses the App Router convention?

- **A.** Add a useEffect spinner in the root layout that watches navigation events and paints a global overlay during any fetch
- **B.** Move all data fetching into getServerSideProps so the browser never renders until the reports data has fully arrived
- **C.** Wrap the reports page in a custom HOC that reads router events and toggles a spinner flag stored in global client state
- **D.** Add a loading.tsx in that route folder, which gives an instant loading UI backed by React Suspense while data resolves  ✅

> **Answer:** D

### Q5. In production, a failed fetch on one dashboard route crashes an entire AI-built app to a white screen. Which App Router file should the builder direct AI to add?

- **A.** An error.tsx in that route folder, creating an error boundary that catches the failure without crashing the whole app  ✅
- **B.** A not-found.tsx in the root, which intercepts all runtime exceptions and renders a fallback page for every failure type
- **C.** A route.ts beside the page that retries the fetch server-side so errors never reach the browser rendering layer at all
- **D.** A global try-catch inside the root layout component so every child page's exceptions resolve to a shared fallback view

> **Answer:** A

### Q6. One codebase must serve a public marketing site and an authenticated SaaS dashboard with completely different shells. What should the builder direct AI to use?

- **A.** Two separate Next.js projects deployed to subdomains, since a single App Router tree cannot hold two distinct layouts
- **B.** A conditional in the root layout that checks the pathname and swaps navigation shells on every client-side render
- **C.** Route groups like (marketing) and (app), which assign different layouts to each area without changing any public URL  ✅
- **D.** Middleware that rewrites marketing URLs into a hidden folder so each area resolves to its own top-level directory

> **Answer:** C

### Q7. Auditing an AI-scaffolded project, a builder finds shared buttons, cards, and utility helpers scattered inside route folders across the app directory. What should the builder direct the AI to do?

- **A.** Leave them in place, since colocation with the routes that use them is the App Router's recommended default for all code
- **B.** Move them into the root layout file so every route can reach them through props without any import statements at all
- **C.** Wrap each one in a route group folder so the shared code stops generating URLs while staying inside the app directory
- **D.** Move shared components and utilities to top-level directories like components and lib, keeping app a clean map of URLs  ✅

> **Answer:** D

### Q8. A builder reviews AI output for an App Router project and spots getServerSideProps in a new file. What does this signal, and what should the builder do?

- **A.** It is the App Router's standard data fetching hook, so the builder should accept it and simply move on to reviewing the layouts
- **B.** It is a harmless legacy alias that Next.js silently maps onto Server Components, so no correction is actually required
- **C.** It is a performance optimization AI adds for slow routes, worth keeping as long as the file also exports a page component
- **D.** It is a Pages Router pattern leaking in; direct the AI to replace it with App Router conventions before the drift spreads  ✅

> **Answer:** D

### Q9. A client wants a content site whose organic search ranking will drive the whole business. The builder must pick the stack before directing AI. Which choice fits the module's guidance?

- **A.** Next.js, because SEO and first-load performance matter here, which is exactly where the framework earns its complexity  ✅
- **B.** A plain React SPA, since modern search crawlers execute JavaScript well enough that rendering strategy no longer matters
- **C.** Any framework works equally, because ranking depends only on content quality and backlinks, never on the delivery stack
- **D.** A React SPA behind a CDN, because caching static bundles at the edge outperforms server rendering for search crawlers

> **Answer:** A

### Q10. A builder is asked to create an internal admin tool that lives behind a login and will never be indexed by search engines. What does the module say about framework choice?

- **A.** Next.js is still mandatory, because Server Components are the only safe way to keep admin data off the client entirely
- **B.** Next.js is required whenever an app has authentication, since login flows depend on server-side route protection
- **C.** A static site generator is the best fit, because admin tools mostly display fixed pages that rarely change between builds
- **D.** A plain React SPA can be the right call, since server rendering and SEO tooling add complexity this tool never uses  ✅

> **Answer:** D

### Q11. A builder is about to prompt AI to scaffold a new SaaS project. According to the module, what belongs in that first scaffolding prompt?

- **A.** Explicit instructions: create-next-app, TypeScript, the App Router named outright, and a written route map to follow  ✅
- **B.** Only the product description, since modern AI reliably infers current Next.js conventions from context without direction
- **C.** A request for both routers scaffolded side by side so the builder can compare outputs and delete the weaker structure
- **D.** The finished database schema first, because routing structure should always be derived from data models, not specified

> **Answer:** A

### Q12. An AI-built app demos perfectly, then at 10K daily users shows blank screens on slow data and white screens on failures. Which audit finding most likely explains both symptoms?

- **A.** Routes are missing loading.tsx and error.tsx files, so there is no loading UI and no boundary to catch failures  ✅
- **B.** The root layout lacks a not-found.tsx, so unmatched URLs cascade into rendering failures across all healthy routes
- **C.** The project uses route groups, which strip error handling from grouped routes unless each group redeclares it
- **D.** Server Components are overused, and only converting routes to client components restores the loading behavior

> **Answer:** A

### Q13. A builder audits an AI-scaffolded project's root layout before approving the structure. Per the module, what belongs in the root layout?

- **A.** Every data fetch in the app, centralized so child pages receive all content as props and never fetch on their own
- **B.** The HTML shell, fonts, and global navigation that every route in the application shares from the top of the tree  ✅
- **C.** The dashboard sidebar and marketing header together, with pathname checks deciding which one renders per request
- **D.** Nothing but a passthrough of children, because shells belong in each route folder to keep the root file minimal

> **Answer:** B

### Q14. A builder notices an AI-built SaaS dashboard feels instant when users move between child pages under the same section. Which App Router behavior explains this?

- **A.** Next.js ships zero JavaScript on every navigation, so nothing on the page can re-render regardless of structure
- **B.** The browser caches full HTML snapshots of each page, and Next.js swaps them without running any React code at all
- **C.** Layouts preserve state and do not re-render on navigation between their child pages, so the shell never rebuilds  ✅
- **D.** Each child page is preloaded into memory at login, so navigation just toggles visibility of already-rendered pages

> **Answer:** C

### Q15. Before reviewing any code in an AI-scaffolded project, the module recommends a five-minute check that catches most architectural drift. What is it?

- **A.** Run the full test suite, since failing tests are the fastest reliable indicator that the routing structure is incorrect
- **B.** Open every page in a browser and click through the app, because rendering issues always surface visibly within minutes
- **C.** Diff the package.json against the official starter template to confirm dependencies exactly match a known-good official baseline
- **D.** Read the app directory tree top to bottom, confirming every route, layout, loading state, and error boundary is placed right  ✅

> **Answer:** D

### Q16. A builder finds an AI-built content site where every page file includes its own copy of the site navigation instead of using a layout. Why does the module flag this?

- **A.** It is purely a style concern, since Next.js deduplicates identical JSX at build time and output stays byte-identical
- **B.** State preservation is lost and the shell re-renders on every navigation, and any design change touches dozens of files  ✅
- **C.** Duplicated navigation breaks static generation, forcing every page in the site onto slower server rendering paths
- **D.** Search engines penalize repeated markup blocks, so duplicated navigation directly reduces the site's ability to rank well

> **Answer:** B

### Q17. During a structure audit of an App Router project, a builder discovers a pages directory that AI quietly added. What does the module call this?

- **A.** The clearest sign of architectural drift, since Next.js will try to honor both routers and behavior becomes unpredictable  ✅
- **B.** A standard compatibility shim that create-next-app includes by default, safe to leave in place through the production launch
- **C.** A required location for API endpoints, since the App Router still depends on the pages directory for backend routes
- **D.** A performance optimization, since routes in pages skip the Server Component pipeline and render faster for most users

> **Answer:** A

### Q18. Reviewing an AI-scaffolded App Router project, a builder finds a file named route.ts inside a folder under app. What is that file's role?

- **A.** It lists the folder's child routes in a manifest file that Next.js requires before nested folders appear as URLs
- **B.** It defines an API style route handler at that path, letting the folder serve requests instead of rendering a page  ✅
- **C.** It overrides the folder's URL segment name, letting the public path differ from the folder name on the disk
- **D.** It registers client-side redirects for that route, replacing middleware for any path rewrites beneath it there

> **Answer:** B

### Q19. AI output includes an unfamiliar routing convention the builder has never seen. Per the module, what is the right verification move before accepting it?

- **A.** Ask the same AI to confirm its own pattern, since a second pass reliably surfaces mistakes in the first response
- **B.** Accept it if the project builds cleanly, because a passing compile proves the convention is currently supported
- **C.** Search old forum threads for the pattern, since community posts document conventions faster than official channels
- **D.** Check nextjs.org/docs as the source of truth, because AI training data lags releases while the docs stay current  ✅

> **Answer:** D

### Q20. A builder wonders why the module insists on writing a project structure spec into the scaffolding prompt. What is the stated reason?

- **A.** Specs let AI skip its planning phase, cutting scaffold generation time roughly in half on large multi-route projects
- **B.** AI fills unspecified decisions with training-data habits, and a written spec replaces its defaults with the builder's own  ✅
- **C.** Next.js refuses to compile projects whose structure is undocumented, so the spec doubles as a required config file
- **D.** Prompts without specs are rejected by most coding assistants, which require an explicit file plan before generating any code

> **Answer:** B

### Q21. A builder wants to confirm the AI is targeting the modern standard before a SaaS build starts. Which statement about the App Router is accurate?

- **A.** Introduced as an experiment, it still requires a feature flag in production and most teams still remain on the Pages Router
- **B.** It lives in the src/routes directory and relies on a central routing configuration file listing every URL by hand
- **C.** Stable since Next.js 13.4, it lives in the app directory and supports Server Components, nested layouts, and streaming  ✅
- **D.** It replaces file conventions with decorators, so routes are declared in code annotations rather than folder names

> **Answer:** C

### Q22. A stakeholder asks why the builder spends so much time on route structure before letting AI write features. Per the module, why is architecture the priority?

- **A.** Routing is the only part of a Next.js app AI cannot generate, so it is the one place builder time directly adds value
- **B.** Refactoring routing in a live app touches every URL, link, and layout at once; right on day one costs an hour, wrong costs weeks  ✅
- **C.** Route structure determines hosting cost on Vercel, and early mistakes permanently lock projects into far more expensive pricing tiers
- **D.** Investors and clients audit folder structure first, so a clean tree is mainly a presentation and credibility concern here

> **Answer:** B

### Q23. An AI-built codebase has app/(marketing)/pricing/page.tsx. A builder checking the live content site wants to know the URL. What does that file serve?

- **A.** /marketing/pricing, because every folder under app contributes a segment to the final URL regardless of its name
- **B.** /(marketing)/pricing, with the parentheses encoded, which is exactly why group folders are discouraged on marketing sites
- **C.** /pricing, because parenthesized group folders organize routes and layouts without ever appearing in the public URL  ✅
- **D.** No URL at all, since parenthesized folders are private and their pages render only when imported by other routes

> **Answer:** C

### Q24. A local bakery needs a five-page brochure site: menu, hours, location, about, contact. Content changes twice a year. What does the module suggest?

- **A.** A static site generator can be the right call, since this project does not need the complexity Next.js brings along  ✅
- **B.** Next.js is required, because any site that wants to appear in search results depends on its server rendering pipeline
- **C.** A React SPA is ideal, since five pages fit in one bundle and client-side routing keeps the experience feeling native
- **D.** The choice is irrelevant at this size, so the builder should pick whichever stack the AI scaffolds fastest by default

> **Answer:** A

### Q25. Which statement best captures the governing principle of Module 1, Next.js Architecture and Routing?

- **A.** Speed of shipping outweighs structure early on, because routing can be refactored cheaply once a product finds traction
- **B.** The builder's job is to memorize framework internals so AI assistance becomes unnecessary for architectural decisions
- **C.** Architecture is the hardest thing to fix later, so direct AI to get the App Router structure right before feature code  ✅
- **D.** Every project should adopt the newest framework features immediately, since conventions age quickly in the Next.js world

> **Answer:** C


---
_Take it in the browser: https://the-faction.mn.co/posts/106185663_
