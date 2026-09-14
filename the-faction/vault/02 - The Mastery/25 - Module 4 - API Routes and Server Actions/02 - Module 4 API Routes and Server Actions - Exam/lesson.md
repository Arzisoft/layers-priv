---
course: "The Mastery"
module: "Module 4 — API Routes and Server Actions"
lesson: "Module 4: API Routes and Server Actions — Exam"
type: "course_quiz"
post_id: 106186246
space_id: 24191170
source: "https://the-faction.mn.co/posts/106186246"
updated: "2026-08-21T15:18:34Z"
---

# Module 4: API Routes and Server Actions — Exam

> Exam for **Module 4 — API Routes and Server Actions** (The Mastery) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. Your AI scaffolds a billing endpoint for a partner integration, but it returns 404 in testing. You suspect the file convention is wrong. Which setup correctly exposes /api/invoices?

- **A.** A file at app/invoices/api.ts exporting a default handler function that receives the request and response objects
- **B.** A file at pages/api/invoices.ts exporting a handler, since the app directory only serves React components to browsers
- **C.** A file at app/api/invoices/route.ts exporting functions named after HTTP methods such as GET and POST for each verb  ✅
- **D.** A file at app/api/invoices/index.ts exporting a single handleRequest function that switches on the incoming method

> **Answer:** C

### Q2. You ask AI to wire a feedback form so it saves to the database without any fetch calls. It proposes a Server Action. Reviewing the code, what actually marks a function as a Server Action?

- **A.** An export from any route.ts file inside the app directory, which Next.js automatically registers as a callable server action
- **B.** A special serverAction() wrapper imported from next/server that converts a plain function into a submission target
- **C.** A config entry in next.config.js listing each action file, so the bundler keeps that code out of the client build
- **D.** The use server directive at the top of the function or file, making it run on the server while called like a function  ✅

> **Answer:** D

### Q3. Your AI-built SaaS needs to receive Stripe webhook events confirming payments. The AI suggests handling them with a Server Action since actions are simpler. What should you direct it to build instead?

- **A.** A Server Action with an exported URL alias, since actions can accept external POST requests when given a public name
- **B.** A Route Handler, because external callers like Stripe need a stable URL with standard HTTP semantics to deliver events  ✅
- **C.** A middleware function that intercepts Stripe requests before routing, since webhooks should never reach handler code
- **D.** A client component that polls the Stripe API on a timer, avoiding inbound webhooks and the security risk they carry entirely

> **Answer:** B

### Q4. Reviewing an AI build, you find a simple settings form in your own dashboard submitting through a hand-rolled /api/settings endpoint with fetch boilerplate. Per the module's decision rule, what is the better direction?

- **A.** Use a Server Action, because forms and mutations triggered by your own UI are its default case and cut the boilerplate  ✅
- **B.** Keep the Route Handler, because forms always need standard HTTP endpoints so browsers can submit them without any scripts
- **C.** Move the logic into middleware so the settings update happens before routing and no endpoint is exposed to any caller
- **D.** Use a Route Handler but rename the file settings.action.ts so Next.js treats it as internal with no public URL at all

> **Answer:** A

### Q5. An AI-generated Server Action deletes projects and has no session check. The AI argues it is safe because the action has no visible URL and is only called from a button shown to admins. Why is this wrong?

- **A.** Server Actions run on the client in production builds, so any user can read the code and reuse the deletion logic
- **B.** The admin button could be rendered by mistake, so UI visibility checks should be duplicated across the component tree
- **C.** Session checks belong in middleware only, and skipping middleware here leaves the app no place to verify its callers
- **D.** Next.js exposes every Server Action as a POST endpoint under the hood, so it needs auth inside it like any API route  ✅

> **Answer:** D

### Q6. You prompt AI for a signup endpoint and it reads the request body straight into a database insert. Following the module's validation guidance, what should you direct it to do first?

- **A.** Parse the input through a schema library like Zod before any database work, rejecting bad shapes with a 400 response  ✅
- **B.** Add a try catch around the insert so malformed payloads throw safely, then return the raw error text for debugging
- **C.** Validate the form fields in the React component before submission, since catching bad input early keeps servers simple
- **D.** Sanitize strings by stripping HTML tags on the client, because the main risk from untrusted input is rendered markup

> **Answer:** A

### Q7. A tester sends your AI-built endpoint a payload missing required fields, and the handler returns 500 with a stack trace. Which status code should schema validation failures return to the caller?

- **A.** 500, because the request caused the server code to fail and server failures are conventionally reported as 5xx codes
- **B.** 400, signaling a bad request so the caller knows the payload shape was rejected before any business logic executed  ✅
- **C.** 200 with an error flag in the JSON body, so clients can handle failures without special status code branching logic
- **D.** 401, because a payload that fails validation cannot be trusted and untrusted requests are authentication failures

> **Answer:** B

### Q8. Reviewing an AI-built invoice endpoint, you see it verifies the session but then lets any logged-in user fetch any customer's invoices. Which distinction from the module does this build miss?

- **A.** Validation versus sanitization: the handler confirms the input shape but never strips dangerous values from the query
- **B.** Authentication versus rate limiting: it knows who is calling but never checks how often that caller hits the endpoint
- **C.** Authentication versus authorization: it confirms who is asking but never checks the caller may access this resource  ✅
- **D.** Sessions versus tokens: cookie sessions cannot scope data access, so the endpoint needed bearer tokens per customer

> **Answer:** C

### Q9. An AI-built profile update action reads userId from the submitted form data and updates that row. Testing works fine. What is the security flaw the module warns about here?

- **A.** Form data arrives unencrypted, so the userId can be intercepted in transit and the fix is enforcing HTTPS on the form
- **B.** Any caller can impersonate any user by sending a different userId, so identity must come from the verified session  ✅
- **C.** Reading form data bypasses Next.js caching, so repeated updates hit the database directly and inflate hosting costs
- **D.** The userId should be stored in localStorage and read on the client, keeping identity handling out of the server code

> **Answer:** B

### Q10. Your app needs to redirect unauthenticated visitors away from all /dashboard pages and set security headers on every response. Where does the module say this cross-cutting logic belongs?

- **A.** Inside each Route Handler and Server Action individually, since duplicating checks per endpoint keeps every file honest
- **B.** In the root layout component, which wraps every page and can inspect cookies before rendering protected content
- **C.** In middleware, which runs before requests reach your routes and is built for gatekeeping paths and setting headers  ✅
- **D.** In a Vercel dashboard setting, since redirects and headers are infrastructure concerns handled outside application code

> **Answer:** C

### Q11. Days after launch, a script starts hammering your AI-built login endpoint with password guesses and your Vercel bill climbs. What does the module recommend for this class of abuse?

- **A.** Move the login route to a Server Action, since actions have no public URL and scripts cannot discover them to attack
- **B.** Add rate limiting backed by a store like Upstash Redis, applied to auth endpoints and anything expensive or abusable  ✅
- **C.** Add a CAPTCHA to the login form component, since blocking bots in the UI stops scripted traffic before it starts
- **D.** Return 500 errors after repeated failures so attacking scripts assume the server is down and move to other targets

> **Answer:** B

### Q12. You are directing AI to standardize error responses. A request with no valid session hits a protected endpoint, and a logged-in user requests a resource they do not own. Which status code pair fits?

- **A.** 400 for the missing session and 401 for the forbidden resource, since both stem from problems in the incoming request itself
- **B.** 403 for the missing session and 401 for the forbidden resource, since forbidden covers requests lacking credentials
- **C.** 401 for the missing session and 403 for the forbidden resource, separating who are you from are you allowed to do this  ✅
- **D.** 429 for both cases, since repeated unauthorized attempts are abuse and abuse responses should share a single code

> **Answer:** C

### Q13. A database insert fails in production and your AI-built handler sends the raw Postgres error, table names included, to the browser. What does the module direct you to do instead?

- **A.** Return the full error only to logged-in users, since authenticated sessions have already proven they can be trusted
- **B.** Silently return 200 so attackers learn nothing, and rely on frontend retry logic to smooth over the failed operation
- **C.** Log the details server side and return a generic message, since raw errors hand attackers a map of your system  ✅
- **D.** Encode the error in base64 before sending, so the client can decode details for support without exposing plaintext

> **Answer:** C

### Q14. You have adopted the module's endpoint review pass as a fixed habit after every AI generation. Which four things does it check, in order?

- **A.** Naming, folder structure, TypeScript types, and test coverage, confirming generated code matches project conventions
- **B.** Caching, bundle size, cold start time, and database indexes, since performance regressions are the main AI blind spot
- **C.** Auth, deployment config, logging, and documentation, covering the operational concerns AI omits from generated code
- **D.** Validation, auth, error handling, and rate limits, covering the gaps AI-generated endpoints most often ship with  ✅

> **Answer:** D

### Q15. Your AI-built contact form has thorough React validation with helpful inline errors, so the AI skipped server-side checks as redundant. How does the module frame frontend validation?

- **A.** It is a courtesy for users, not a defense, because attackers call your endpoints directly and skip the frontend entirely  ✅
- **B.** It is sufficient when paired with HTTPS, since encrypted transport prevents any tampering with the validated payload
- **C.** It is the primary defense layer, with server checks as an optional backup for teams that have extra engineering time
- **D.** It is a performance feature only, and validation of any kind matters far less than rate limiting on form endpoints

> **Answer:** A

### Q16. You direct AI to add a limiter to your email-sending endpoint. A client exceeds its allowance and the handler must respond. Which status code tells the caller it has been rate limited?

- **A.** 403, since a caller over its allowance is no longer permitted to use the endpoint until its request window resets
- **B.** 503, since the endpoint is effectively unavailable to that caller and availability codes live in the 5xx range
- **C.** 408, since the caller should treat the block as a timeout and retry the request after a reasonable waiting interval
- **D.** 429, the too many requests code, signaling the caller exceeded its allowance and should back off before retrying  ✅

> **Answer:** D

### Q17. Your AI proposes hand-rolling session management with custom cookies and its own password hashing for your SaaS. Per the module's toolkit guidance, how should you redirect it?

- **A.** Integrate Auth.js or Clerk instead, since both give a server-side helper to verify the caller in every action and route  ✅
- **B.** Accept the custom build but require AI to add extensive tests, since tested custom auth beats adding third party dependencies
- **C.** Use middleware-only auth with no session library, since path gatekeeping removes the need for per-route verification
- **D.** Store a signed userId in localStorage and send it with each request, keeping session state fully under your control

> **Answer:** A

### Q18. An AI-generated endpoint works perfectly in your testing: data saves, the UI updates, no errors appear. The module still warns against shipping it as is. Why?

- **A.** AI-generated code is usually too slow for production traffic, so every endpoint needs a performance pass before launch
- **B.** Tutorial-trained models omit auth and validation by default, so an endpoint that works is not an endpoint that is safe  ✅
- **C.** Passing tests prove correctness only on Vercel previews, and production runtime behavior differs enough to require QA
- **D.** Endpoints must be manually registered in next.config.js before deploy, and unregistered routes fail silently in prod

> **Answer:** B

### Q19. You want a newsletter signup form handled with the least boilerplate the platform allows. Per the module, how does a form connect to a Server Action?

- **A.** Pass the action to the form's action prop, and the framework wires submission to the server function with no fetch code  ✅
- **B.** Register the action under an /api path and point the form's method attribute at it, letting the browser POST to it normally
- **C.** Call the action inside a useEffect hook that watches form state, submitting whenever every field passes validation
- **D.** Add an onSubmit handler that serializes fields to JSON and posts them to the action's autogenerated URL with fetch

> **Answer:** A

### Q20. You are splitting responsibilities in an AI-built app: redirecting logged-out users off protected paths, and verifying a caller owns the specific document they are editing. Where does each belong?

- **A.** Both in middleware, since running every security check before routing keeps handlers free of duplicated auth logic
- **B.** Both inside each handler, since middleware runs on the edge where session and database checks are both impossible
- **C.** Ownership checks in middleware and redirects in handlers, since resource logic should run before routing begins
- **D.** Redirects in middleware as a cross-cutting concern, and ownership checks inside the handler touching the resource  ✅

> **Answer:** D

### Q21. Budget for rate limiting is limited, so you direct AI to protect only the endpoints the module flags as prime abuse targets. Which set should get limits first?

- **A.** Static asset routes and image endpoints, since bandwidth costs are the largest driver of a runaway hosting bill
- **B.** GET routes for public content pages, since they receive the most traffic and traffic volume equals abuse exposure
- **C.** Internal admin endpoints, since they are the highest privilege surface and attackers always target privilege first
- **D.** Auth endpoints, anything that sends email, and expensive queries, the routes brute force and scripts hit hardest  ✅

> **Answer:** D

### Q22. You direct AI to define a Zod schema before building each handler. Beyond rejecting bad input, what extra benefit does the module note from this schema-first approach?

- **A.** Zod schemas compile to database migrations, so the input shape and the table structure can never drift out of sync
- **B.** Zod schemas auto-generate client forms, so the frontend and backend share one definition of every field and label
- **C.** One schema defines the input shape and doubles as TypeScript types, keeping validation and typing in one source  ✅
- **D.** Zod runs on the edge before your code executes, so invalid requests are rejected without invoking your handler at all

> **Answer:** C

### Q23. Your AI keeps generating full API routes with fetch calls for every simple form in your dashboard. Per the module, what direction should you give it?

- **A.** Redirect it to Server Actions for your own UI's forms and mutations, which cuts the fetch boilerplate roughly in half  ✅
- **B.** Keep the API routes but have AI generate a shared fetch wrapper, since consistent HTTP calls are worth the extra code
- **C.** Ask for GraphQL instead, since a single query endpoint removes the need to choose between actions and route handlers
- **D.** Have AI colocate each route file next to its form component, since proximity is the real problem with the boilerplate

> **Answer:** A

### Q24. Your product is adding an iOS app and a partner integration that both need to read workspace data from your Next.js backend. Which backend flavor does the module prescribe, and why?

- **A.** Server Actions, because they serialize responses automatically and mobile clients prefer the smaller action payloads
- **B.** Route Handlers, because callers outside your app need stable URLs and standard HTTP semantics to consume the API  ✅
- **C.** Middleware endpoints, because edge execution puts responses closer to mobile users than regular route code can
- **D.** Server Actions with a shared secret header, because actions are safer to expose to partners than open HTTP routes

> **Answer:** B

### Q25. Beyond any single technique, what overarching principle does Module 4 teach about directing AI to build the API layer of a Next.js application?

- **A.** The API layer meets a hostile world, so every endpoint must validate, authenticate, and resist abuse before it ships  ✅
- **B.** The API layer should stay as small as possible, because every endpoint you avoid building is one nobody can attack
- **C.** The API layer is where AI outperforms humans, so builders should review the frontend and trust the generated backend
- **D.** The API layer belongs in a separate service, because mixing frontend and backend in one project multiplies the risk

> **Answer:** A


---
_Take it in the browser: https://the-faction.mn.co/posts/106186246_
