---
course: "The Mastery"
module: "Module 2 — Server and Client Components"
lesson: "Module 2: Server and Client Components — Exam"
type: "course_quiz"
post_id: 106185847
space_id: 24191170
source: "https://the-faction.mn.co/posts/106185847"
updated: "2026-08-21T15:17:44Z"
---

# Module 2: Server and Client Components — Exam

> Exam for **Module 2 — Server and Client Components** (The Mastery) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. Reviewing an AI build, you find 'use client' at the top of every file, even static text pages. What is the actual default rendering model in the Next.js App Router?

- **A.** Every component renders in the browser by default, and developers opt into server rendering per route with an explicit config flag
- **B.** Every component is a Server Component by default, running on the server and sending finished HTML with almost no JavaScript  ✅
- **C.** Next.js decides per component automatically at build time by scanning each file for hooks and event handler usage
- **D.** Pages render on the server but all shared components render in the browser unless wrapped in a special server tag

> **Answer:** B

### Q2. An audit shows your AI put a Stripe secret key inside a checkout component marked 'use client'. Anyone can now read it in the shipped bundle. What is the right fix to direct?

- **A.** Move the payment logic into a server component so the key stays in server-only code that never reaches the browser  ✅
- **B.** Rename the variable with the NEXT_PUBLIC_ prefix so Next.js knows to encrypt it securely before adding it to the bundle
- **C.** Keep the component client-side but load the key with useEffect after mount so it never appears in the source
- **D.** Obfuscate the key with base64 encoding in the client file so casual viewers cannot recognize it as a secret

> **Answer:** A

### Q3. Your AI added 'use client' to a shared wrapper high in the tree and the bundle size jumped sharply. What does the directive do to that file's imports?

- **A.** Imports are unaffected; the directive only changes where the single marked file itself is rendered and hydrated
- **B.** Imports are split automatically, with interactive ones going to the client and static ones staying on the server
- **C.** Every component that file imports joins the client bundle too, so one high directive drags whole subtrees with it  ✅
- **D.** Imports throw build errors unless each imported file also declares its own matching 'use client' directive at the top

> **Answer:** C

### Q4. Directing AI on a SaaS dashboard, you must flag which pieces genuinely need 'use client'. Which feature list truly requires a Client Component?

- **A.** Rendering fetched data into tables, formatting dates, and composing shared layout sections reused across many different routes
- **B.** Reading environment variables, querying the database, and rendering markdown content into finished static HTML
- **C.** Anything imported by a page file, since pages hydrate in the browser and require their imports to do the same
- **D.** useState and useEffect hooks, click and form event handlers, and browser APIs such as localStorage or direct DOM access  ✅

> **Answer:** D

### Q5. A content site your AI built ranks poorly. Crawlers receive a near-empty HTML shell because every page is client-rendered. Why does a server-first build fix SEO?

- **A.** Server components deliver complete, finished HTML on the first response, so crawlers can index content immediately  ✅
- **B.** Server components attach special metadata headers that tell Google the site is trustworthy and should rank higher
- **C.** Client rendering is invisible to all crawlers forever, so any JavaScript on a page removes it from search results entirely
- **D.** Server rendering compresses pages so aggressively that crawl budget stretches across many more URLs per visit

> **Answer:** A

### Q6. Your AI passes data from a server page into a client chart widget, and the app throws a confusing runtime error about props. What rule governs props crossing the boundary?

- **A.** Props must be wrapped in a special transfer object provided by Next.js before they can leave the server context
- **B.** Any JavaScript value can cross the boundary safely because Next.js serializes functions and class instances automatically
- **C.** Only primitive strings and numbers can cross; arrays and nested objects must be flattened into query parameters
- **D.** Props must be serializable: plain objects, arrays, and strings travel fine, but functions and class instances do not  ✅

> **Answer:** D

### Q7. Your AI insists a server-rendered article must become client code because it sits inside an interactive tab wrapper. What pattern proves that claim wrong?

- **A.** Pass the server component into the client wrapper as children, so it stays server-rendered inside the interactive shell  ✅
- **B.** Import the server component directly into the client file, since imports always preserve original rendering location
- **C.** Duplicate the article into two versions, one server and one client, and swap between them with a media query at render
- **D.** Add both 'use client' and 'use server' directives to the article file so the router can render it in either environment on demand

> **Answer:** A

### Q8. A dashboard page file starts with 'use client' because one dropdown needed state, so the entire subtree ships as browser JavaScript. What placement should you direct instead?

- **A.** Keep the directive on the page but add lazy loading so the subtree downloads only after the visitor first interacts
- **B.** Push 'use client' down to the dropdown leaf itself, leaving the rest of the page server-rendered around the island  ✅
- **C.** Move the directive up to the root layout so the client boundary is declared once and shared consistently by routes
- **D.** Split the dashboard into a separate single-page app so interactive and static content deploy as different projects

> **Answer:** B

### Q9. After an AI change, you suspect a route quietly ships far more JavaScript than before. Which audit step from the module verifies bundle impact?

- **A.** Run the build and read the route-by-route JavaScript sizes Next.js prints, or inspect with the bundle analyzer package  ✅
- **B.** Open the deployed page in a browser and time how long it takes to load on your own laptop over office wifi several times in a row
- **C.** Count the number of files in the components folder, since file count maps directly to shipped JavaScript weight
- **D.** Check the Vercel dashboard billing page, because bundle growth always shows up first as higher hosting charges there

> **Answer:** A

### Q10. Your AI suggests renaming DATABASE_URL to NEXT_PUBLIC_DATABASE_URL to fix an undefined variable error in a client file. What does that prefix actually do?

- **A.** It exposes the variable to the browser bundle, so applying it to a secret hands the value to anyone viewing the code  ✅
- **B.** It marks the variable as safe for the framework to encrypt, letting client components use secrets without exposure
- **C.** It scopes the variable to public marketing pages only while keeping it fully hidden from every authenticated application route
- **D.** It has no runtime effect; the prefix is a naming convention that documents intent for developers reading env files

> **Answer:** A

### Q11. Your AI fixed a build error by importing a server-only data table straight into a client file. The error vanished. What actually happened to that table component?

- **A.** It stayed a server component, because import statements never change where a component renders in the App Router
- **B.** It was silently converted into client code, joining the browser bundle and losing its server-only capabilities  ✅
- **C.** Next.js split it in half automatically, rendering data on the server while hydrating the shell in the browser
- **D.** It now renders twice, once on the server and once in the browser, doubling the work but keeping behavior correct

> **Answer:** B

### Q12. A client component your AI wrote fetches dashboard data with useEffect, causing spinners, layout shift, and an extra round trip. What should you direct instead?

- **A.** Keep the client fetch but add a skeleton loader so users perceive the waiting as intentional design rather than lag
- **B.** Cache the fetch response in localStorage so repeat visitors skip the round trip after their very first page load
- **C.** Move the fetch into a useMemo hook so the request runs during render instead of after the component has mounted
- **D.** Fetch the data in a server component parent and pass it down as serializable props, removing the client round trip  ✅

> **Answer:** D

### Q13. You are auditing an AI-built marketing site and must sort dozens of components into server or client. What single filter question does the module give you?

- **A.** Does this component appear above the fold, where paint speed matters most and server rendering gives the biggest win
- **B.** Does this component need to respond to user interaction in the browser; if not, it belongs on the server by default  ✅
- **C.** Does this component exceed roughly two hundred lines, since larger files justify the cost of client-side hydration
- **D.** Was this component generated by AI or written by hand, since AI output defaults to patterns needing client review

> **Answer:** B

### Q14. Every build error your AI hits, it fixes by adding 'use client' to another file, and the errors do disappear. Why does the module treat this habit as dangerous?

- **A.** It quietly trades server rendering away: crawlers get an empty shell, bundles bloat, and scores crater despite demos  ✅
- **B.** The directive is deprecated in current Next.js releases, so every added instance creates avoidable future migration work later
- **C.** Each added directive slows the build pipeline measurably, and enough of them cause deployment timeouts on Vercel
- **D.** Client components cannot be tested with standard tooling, so coverage drops with every file the AI converts over

> **Answer:** A

### Q15. Your SaaS dashboard shows charts, tables, and one date-range picker. The AI proposes making the whole page a client component for consistency. What split should you direct?

- **A.** Accept the proposal, since dashboards are inherently interactive surfaces and mixed trees confuse later maintenance
- **B.** Make everything a server component including the picker, and handle date changes with full page reloads instead
- **C.** Keep charts and tables server-rendered as the ocean, and wrap only the date picker as a small interactive island  ✅
- **D.** Alternate component types route by route, so interactive pages go client and reporting pages stay on the server

> **Answer:** C

### Q16. Comparing two versions of a pricing page, one server and one client, you list capabilities only the server version has. Which set is exclusive to server components?

- **A.** Responding to user clicks instantly, storing form state between keystrokes, and reading browser APIs like localStorage
- **B.** Rendering JSX markup, receiving props from parent components, and composing children, which clients cannot do
- **C.** Running useEffect after paint, subscribing to window events, and animating layout transitions between routes
- **D.** Querying databases directly, holding secret keys safely, and rendering finished HTML with zero component JavaScript  ✅

> **Answer:** D

### Q17. A build works until a server page passes an onDelete callback into a client list row, then fails at runtime with an error that never names the real cause. What broke?

- **A.** The client row rendered before the server finished streaming, so the prop arrived after the first paint had already completed
- **B.** The callback name collided with a reserved App Router prop, and renaming the function would resolve the failure
- **C.** A function was passed across the server to client boundary, and functions are not serializable so they cannot cross  ✅
- **D.** The list row was missing a React key prop, which blocks its other props from hydrating correctly in the browser

> **Answer:** C

### Q18. Mid-build, your AI casually suggests adding NEXT_PUBLIC_ to your payment provider key so a client component can read it. How does the module say to treat this suggestion?

- **A.** Approve it, because the prefix is the officially supported way for any component type to access configuration values
- **B.** Approve it only in development, then strip the prefix in production where real user traffic makes exposure risky
- **C.** Treat it as a red flag to investigate, since the prefix would compile the secret into JavaScript anyone can read  ✅
- **D.** Defer to the AI, since modern frameworks manage env exposure automatically and manual review adds little value

> **Answer:** C

### Q19. Your app serves 10K daily users, many on phones. After a boundary audit moved most components back to the server, load speed improved sharply. Why?

- **A.** Server components render on faster datacenter CPUs, and raw rendering speed is what visitors experience as page load time
- **B.** Far less client JavaScript ships to each visitor, so phones download, parse, and execute less code on every load  ✅
- **C.** Vercel prioritizes bandwidth for server-first applications, routing their traffic through faster edge locations
- **D.** Server rendering disables images and fonts until interaction, cutting the initial payload visitors must receive

> **Answer:** B

### Q20. Running the module's audit prompt, you find a testimonial card marked 'use client' that has no hooks, no handlers, and no browser APIs. What is the correct verdict?

- **A.** Leave it alone, since removing a working directive risks regressions and client rendering is harmless at this size
- **B.** Convert it back to a server component, because a component that only displays data has no business being client  ✅
- **C.** Add a useEffect hook to justify the directive, so the file matches its declared rendering location going forward
- **D.** Flag it as a security incident, since any unjustified client component means secrets have already been exposed

> **Answer:** B

### Q21. Your AI declares that a server-rendered report has to become a client component because a collapsible panel now wraps it. What does the module say about such claims?

- **A.** They are usually correct, because wrappers control rendering and children must match the parent's environment
- **B.** They are correct only for layouts; for pages, Next.js allows mixed trees without any special composition patterns at all
- **C.** The children pattern usually proves them wrong: the client panel can receive the server-rendered report as children  ✅
- **D.** They signal an outdated framework version, and upgrading Next.js removes the need for any boundary decisions

> **Answer:** C

### Q22. A settings screen must remember a collapsed-sidebar preference using localStorage. Your AI asks whether this piece can stay on the server. What do you tell it?

- **A.** Yes, localStorage is available during server rendering because Next.js emulates browser storage on the server side
- **B.** Yes, as long as the read happens inside an async function, the server can reach the visitor's browser storage
- **C.** No component may ever touch localStorage in Next.js; preferences must be stored in cookies read by middleware
- **D.** No, browser APIs like localStorage only exist in the browser, so this piece needs 'use client' to access them  ✅

> **Answer:** D

### Q23. A week after approving an AI refactor, one route's JavaScript bundle has ballooned even though its features look unchanged. What does the module say this signals?

- **A.** Normal dependency drift, since npm packages grow over time and bundle growth without feature change is expected
- **B.** A caching problem on Vercel, where stale build artifacts get appended to fresh bundles until caches are purged
- **C.** Image assets being inlined into the JavaScript output, which happens automatically once routes exceed a size limit
- **D.** The client boundary moved somewhere it should not have, so audit where 'use client' sits and what it now imports  ✅

> **Answer:** D

### Q24. You are explaining to a teammate why a leaked key in a client component is a critical incident rather than a theoretical risk. How exposed is code in the client bundle?

- **A.** Completely exposed: it compiles into public JavaScript that anyone can read with View Source or simple dev tools  ✅
- **B.** Partially exposed: minification scrambles identifiers, so extracting a working key takes real reverse engineering
- **C.** Exposed only to logged-in users, since Next.js gates hydrated JavaScript behind the application session layer
- **D.** Exposed only during development, because production builds strip environment values from the shipped bundles

> **Answer:** A

### Q25. Beyond any single scenario, what is the governing principle Module 2 teaches for directing AI on Next.js component architecture?

- **A.** Interactivity comes first: users now expect rich client behavior on every surface, so default to client components
- **B.** Balance is the goal: keep roughly half the tree on the server and half on the client so neither side is overloaded
- **C.** Server-first by default: components stay on the server unless interactivity demands a client boundary at a small leaf  ✅
- **D.** Tooling decides: trust the framework and the AI to choose sensible boundaries, intervening only when builds fail outright

> **Answer:** C


---
_Take it in the browser: https://the-faction.mn.co/posts/106185847_
