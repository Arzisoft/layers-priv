---
course: "The Mastery"
module: "Module 5 — Storage Realtime and Edge Functions"
lesson: "Module 5: Storage Realtime and Edge Functions — Exam"
type: "course_quiz"
post_id: 106187780
space_id: 24191170
source: "https://the-faction.mn.co/posts/106187780"
updated: "2026-08-21T15:20:13Z"
---

# Module 5: Storage Realtime and Edge Functions — Exam

> Exam for **Module 5 — Storage Realtime and Edge Functions** (The Mastery) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. Your client portal stores signed contracts. The AI created a public bucket so uploads worked on the first try. What is the core risk of leaving it this way?

- **A.** Public buckets skip Supabase's CDN, so every contract download hits the database directly and slows the whole app.
- **B.** Public buckets cannot store PDFs reliably, so contracts will intermittently fail to upload for some client accounts over time.
- **C.** Every contract becomes reachable by anyone who obtains or guesses its URL, since no policy check guards public files.  ✅
- **D.** Public buckets bypass your storage quota, so the project accrues surprise bandwidth charges as clients download.

> **Answer:** C

### Q2. Reviewing an AI-built marketplace, you find a storage policy granting read access to any authenticated user on the private dispute-evidence bucket. Why should you reject it?

- **A.** Authenticated reads are fine for private buckets; the real problem is that the policy also needs a matching insert rule.
- **B.** The policy should check the user's email domain instead, since auth.uid() values can be spoofed by a modified client.
- **C.** It checks login but not ownership, so any signed-in buyer can read another buyer's dispute files by requesting the path.  ✅
- **D.** Private buckets ignore policies entirely, so this rule does nothing and the bucket stays locked for every client request.

> **Answer:** C

### Q3. Your client portal must deliver a private contract PDF to its owner without exposing the bucket. Which approach matches the module's guidance?

- **A.** Flip the bucket to public just before each download, then flip it back to private once the client confirms receipt.
- **B.** Generate a short-lived signed URL for the authorized user, so the link is tamper-proof and expires after a set window.  ✅
- **C.** Embed the service role key in the frontend so the client can fetch any file directly while bypassing bucket policies entirely.
- **D.** Copy the PDF into a public bucket under a randomized filename, relying on the unguessable name to keep it protected.

> **Answer:** B

### Q4. Your marketplace grid loads 8MB original product photos and feels sluggish. The seller photos live in Supabase Storage. What does the module recommend?

- **A.** Request thumbnails through Supabase image transformation parameters on the URL so the grid serves small resized copies.  ✅
- **B.** Enable realtime on the photos table so the grid streams image bytes progressively instead of downloading whole files.
- **C.** Move the originals into a public bucket, since public files are cached by browsers and load faster than private ones in practice.
- **D.** Write an edge function that opens each image and recompresses it on every page load before returning it to the grid.

> **Answer:** A

### Q5. You are adding a typing indicator to your support chat. The AI proposes writing every keystroke to a table and streaming it out with Postgres Changes. What should you direct instead?

- **A.** Use presence, since typing status is a form of row-level data that presence persists to the database automatically for you.
- **B.** Keep Postgres Changes but add an index on the keystroke table so the insert volume does not slow down the stream.
- **C.** Use polling every few seconds, because realtime channels cannot deliver messages fast enough for typing indicators.
- **D.** Use broadcast, which sends ephemeral client-to-client messages without touching the database, a cheaper better fit.  ✅

> **Answer:** D

### Q6. Your SaaS document editor should show a '3 teammates viewing' indicator on each open doc. Which realtime mode fits this feature best?

- **A.** Postgres Changes on a viewers table, since online status must be written to the database rows to be trustworthy.
- **B.** Presence, which tracks who is currently online in a channel and is built for viewing indicators exactly like this.  ✅
- **C.** Broadcast, since viewer counts are ephemeral messages that each connected client should compute and send itself periodically.
- **D.** A signed URL issued per viewer, since storage access logs already record exactly who has each document open now.

> **Answer:** B

### Q7. In your 50-tenant SaaS, a dashboard subscribes to Postgres Changes with a tenant_id=eq.12 filter in JavaScript. What must you verify before calling this secure?

- **A.** That RLS on the underlying table restricts rows server-side, because the client filter can be edited in DevTools.  ✅
- **B.** That the filter uses the tenant's UUID rather than a numeric ID, since UUIDs cannot be altered in browser tooling.
- **C.** That the channel name includes the tenant ID, because Supabase derives row visibility from the channel's name string.
- **D.** That the subscription uses websockets rather than polling, since polling responses are easier for users to intercept.

> **Answer:** A

### Q8. Your admin dashboard shows a report refreshed once per day by a nightly job. The AI wired a realtime subscription to the reports table. What is the right call?

- **A.** Keep the subscription, since realtime connections are free and the dashboard will always show the freshest numbers.
- **B.** Keep the subscription but add broadcast as a fallback so the report still updates when the socket drops overnight.
- **C.** Replace it with presence so the dashboard only opens a connection when an admin is actually viewing the report.
- **D.** Drop realtime here; data that changes daily needs a refetch, and every subscription burns connection overhead.  ✅

> **Answer:** D

### Q9. An AI-built edge function that emails your users was deployed with --no-verify-jwt to ease testing and never changed back. What is the exposure?

- **A.** Nothing yet; unverified functions still require the anon key, which is secret enough to keep strangers from calling it.
- **B.** Anyone on the internet can invoke the endpoint anonymously and send email on your behalf, so re-enable verification.  ✅
- **C.** The function will silently fail in production because Supabase blocks unverified functions from outbound requests.
- **D.** Only rate limits are affected; unverified functions run in a throttled tier that slows email delivery for real users.

> **Answer:** B

### Q10. During review you spot the Supabase service role key in your frontend's committed .env file, referenced by client code. Why is this a launch blocker?

- **A.** The service role key expires monthly, so shipped clients will break when it rotates and force an emergency release.
- **B.** That key bypasses all RLS, so anyone extracting it from the client can read and write every row despite your policies.  ✅
- **C.** Frontend env vars are encrypted at build time, so the key will be corrupted and all storage uploads will start failing.
- **D.** The key only works from Deno, so client calls will throw errors that flood your logs and mask real production issues.

> **Answer:** B

### Q11. Your edge function calls Stripe with a secret key. The AI wrote the key directly into the function's source file in the repo. What do you direct it to do?

- **A.** Move the key to an environment variable set with supabase secrets set, and keep every secret out of committed code.  ✅
- **B.** Wrap the key in base64 within the source file, which the module treats as adequate obfuscation for server-side code.
- **C.** Move the key into a private storage bucket and have the function download it with a signed URL on every invocation.
- **D.** Store the key in a database table protected by RLS, since policies will stop anyone but the function reading it.

> **Answer:** A

### Q12. Your marketplace needs order totals recalculated across three tables inside one transaction whenever line items change. No secrets or external APIs are involved. Where does this logic belong?

- **A.** An edge function, because multi-table writes must run in Deno where you can retry each statement individually.
- **B.** A frontend API route, since the recalculation should live next to the checkout UI code that triggers it most often in practice.
- **C.** The browser client, because totals are display logic and the database should only store what the client computes.
- **D.** A database function, since the logic is pure data: transactional, multi-table, needing no secrets or outside calls.  ✅

> **Answer:** D

### Q13. You need to charge cards through Stripe when an order is placed in your marketplace. Where does the module say this logic belongs, and why?

- **A.** A database function, because payment amounts come from order rows and data logic should stay inside Postgres itself.
- **B.** An edge function, because it needs a secret key and a third-party API, neither of which can live in the browser.  ✅
- **C.** The frontend, because Stripe's client library is designed to accept secret keys safely from live browser sessions.
- **D.** A storage bucket webhook, because file-style event triggers are how Supabase routes calls to outside services.

> **Answer:** B

### Q14. Your AI claims live order updates are working, but the dashboard never receives events and the subscription code looks right. Per the module's toolkit, what do you check first?

- **A.** Whether the orders table has a primary key of type UUID, since realtime silently ignores integer-keyed tables.
- **B.** Whether the frontend framework supports websockets, since most build tools strip socket code out in production builds.
- **C.** The Dashboard Realtime panel, confirming the table actually has realtime enabled versus what the AI claimed it did.  ✅
- **D.** Whether the anon key was rotated recently, since stale keys receive events but cannot acknowledge them back.

> **Answer:** C

### Q15. Sellers report uploads to your new private product-photos bucket fail from the app, though the bucket exists in the dashboard. The AI wrote no storage policies. What explains this?

- **A.** A private bucket with no policies on storage.objects is unusable from the client, so every upload request is refused.  ✅
- **B.** Private buckets accept uploads only through the CLI, so the app must proxy files through supabase functions serve instead.
- **C.** The bucket needs realtime enabled before accepting uploads, since storage events flow through the realtime engine.
- **D.** New buckets stay read-only for a day while Supabase provisions storage, so the uploads will start working soon.

> **Answer:** A

### Q16. You direct AI to secure a private tenant-files bucket in your 50-tenant SaaS. Which storage policy pattern does the module teach as the standard?

- **A.** Store files under a path prefixed by the tenant's ID and write policies checking that prefix against the user's identity.  ✅
- **B.** Name each file with a UUID and rely on unguessable names, since policies on storage.objects cannot read file paths at all.
- **C.** Create one bucket per tenant and make each public, since bucket-level separation replaces the need for any policy.
- **D.** Grant all authenticated users access and filter files by tenant in the frontend after the full list is downloaded.

> **Answer:** A

### Q17. Your AI generated signed URLs for private invoices that expire in one year, arguing clients hate broken links. What is the module-aligned review?

- **A.** Approve it; signed URLs are tamper-proof, so the expiry window has no effect on how exposed the file actually is.
- **B.** Reject it; signed URLs should never exceed 60 seconds, the maximum window Supabase supports for private buckets.
- **C.** Reject it; signed URLs should be short-lived, since a year-long link shared or leaked works like a public file.  ✅
- **D.** Approve it, but move the invoices to a public bucket so the links keep working even after the signature expires.

> **Answer:** C

### Q18. Your SaaS dashboard should show a live feed of new orders as rows land in the orders table. Which realtime mode matches this feature?

- **A.** Postgres Changes, which streams inserts from tables you explicitly enable, delivering database events to subscribers.  ✅
- **B.** Broadcast, since order events should be sent client to client without ever involving the database or its policies at any point.
- **C.** Presence, since a feed of activity is really a record of which users are currently online inside the shared channel.
- **D.** Signed URLs refreshed on an interval, since storage links are the module's standard transport for order events.

> **Answer:** A

### Q19. An AI session just wired storage, realtime, and an edge function, and reports everything is secure. Per the module, what do you do before accepting that claim?

- **A.** Accept it if the demo works end to end, since runtime behavior is stronger evidence than reading configuration.
- **B.** Ask the AI to summarize its own security posture in a paragraph, approving if no risks appear in its summary.
- **C.** Rerun the same build prompt a second time and compare outputs, keeping whichever version has fewer lines of code overall.
- **D.** Run the AI Audit Prompt so it verifies buckets, policies, subscriptions, and functions against actual configuration.  ✅

> **Answer:** D

### Q20. Your edge function verifies the JWT and then immediately refunds whatever order ID arrives in the request body. Verification passes. What is still wrong?

- **A.** Nothing; a valid JWT proves the caller owns the order, since Supabase encodes ownership claims into every token.
- **B.** The function should also check the anon key, since JWTs alone cannot confirm the request came from your frontend.
- **C.** Refunds must run in the browser instead, since edge functions are only meant for reads and third-party lookups.
- **D.** It authenticates but never authorizes; it must confirm this user may refund this specific order before acting.  ✅

> **Answer:** D

### Q21. In your multi-tenant SaaS, you enable Postgres Changes on the messages table. With everything configured properly, what determines which rows each subscriber receives?

- **A.** The table's RLS policies; subscribers only receive rows they could SELECT, enforcing isolation on the server side.  ✅
- **B.** The order of subscription; earlier subscribers claim rows first and later clients receive whatever remains unread afterward.
- **C.** The channel topic string; Supabase parses tenant IDs out of the topic and routes rows to matching clients only.
- **D.** The client library version; newer supabase-js releases filter rows locally while older ones receive everything.

> **Answer:** A

### Q22. Your Next.js app needs a server endpoint that reformats dashboard data in ways tightly coupled to that app, and you already deploy a Next.js server. Which layer fits?

- **A.** A database function, since anything running on a server belongs in Postgres regardless of coupling to the frontend app.
- **B.** A frontend API route, since the logic is tightly coupled to this app and you already deploy a server alongside it.  ✅
- **C.** An edge function, since Deno endpoints are required whenever server-side JavaScript runs in a Supabase project.
- **D.** A realtime broadcast channel, since reformatted data can be pushed to clients without any server logic at all.

> **Answer:** B

### Q23. You want to scaffold and test a new edge function locally before deploying, and set its Stripe secret. Which toolkit workflow does the module describe?

- **A.** Write the function in the Dashboard SQL editor and deploy it with a database migration, storing secrets in a table.
- **B.** Create the function inside supabase-js on the client, since functions.invoke() compiles and uploads it on first call for you.
- **C.** Use the Supabase CLI: supabase functions new to scaffold, functions serve to run locally, and secrets set for the key.  ✅
- **D.** Upload the TypeScript file to a private storage bucket, where Supabase automatically detects and deploys functions.

> **Answer:** C

### Q24. Your marketplace has two upload types: seller product photos shown to all visitors, and buyer dispute evidence. How should the buckets be set up?

- **A.** Both public, since the marketplace is a public-facing app and mixed buckets simplify the upload code your AI generates.
- **B.** Both private with signed URLs for everything, since the module says public buckets are never acceptable to ship.
- **C.** Product photos private and evidence public, so sellers' commercial images get the stronger protection of the two.
- **D.** Product photos in a public bucket, since all visitors may see them; dispute evidence private with ownership policies.  ✅

> **Answer:** D

### Q25. Which statement best captures the governing principle of Module 5: Storage, Realtime and Edge Functions?

- **A.** Realtime should replace polling everywhere, since live features are what separate production apps from mere demos.
- **B.** Storage, realtime, and functions are frontend concerns, so security for them belongs in the client, not the database.
- **C.** These features often demo correct but ship insecure, so audit that every layer enforces access rules server-side.  ✅
- **D.** Edge functions should hold all business logic, since centralizing code in Deno keeps policies out of the database.

> **Answer:** C


---
_Take it in the browser: https://the-faction.mn.co/posts/106187780_
