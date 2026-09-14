---
course: "The Foundation"
module: "Layer 2: APIs & Backend Logic"
lesson: "Layer 2: APIs & Backend Logic — Study Guide"
type: "course_lesson"
post_id: 102891560
space_id: 23777123
source: "https://the-faction.mn.co/posts/102891560"
updated: "2026-08-10T17:50:13Z"
---

# Layer 2: APIs & Backend Logic — Study Guide

## Layer 2: APIs & Backend Logic

How Your App Talks to Itself Behind the Scenes

This is the study guide. Everything for APIs & Backend Logic is on this page — there's nothing to download.

## What This Study Guide Covers

This study guide covers Layer 2: APIs & Backend Logic—how your app talks to itself behind the scenes.

When a user taps "Place Order" in your app, something has to happen between that tap and the order actually showing up in your system. That something is the backend. It's the invisible machinery that receives requests, runs business logic, talks to the database, and sends answers back to the screen.

You're not going to write server code by hand. You're going to describe what your app needs to do—"when someone submits this form, save their info and send them a confirmation"—and let your AI coding tool build the backend for you. Your job is to understand what's supposed to happen, check that it actually works, and catch mistakes before your users do. That's what this certification proves you can do.

This study guide walks you through the concepts, tools, and checkpoints you need to pass the Layer 2 certification exam.

## Why It Matters

If your frontend is the face of your app, the backend is the brain. When it breaks, nothing works —forms don't submit, data doesn't save, payments don't process. And here's the painful part:

your users see a blank screen or a spinning wheel, and they blame your entire product. A broken backend is invisible until it ruins someone's experience.

Here's the thing about AI coding tools: they're great at building backend endpoints and connecting things together. But they consistently make choices you didn't ask about—like not handling what happens when a request fails, or not validating the data that comes in, or creating an endpoint that returns way too much information to anyone who asks. AI builds exactly what you describe. If you don't know what to check for, you get gaps that turn into outages. This study guide teaches you what to check for.

## CERTIFICATION GOAL

You can describe what your app needs to do behind the scenes, use an AI coding tool to build the backend logic, test that it actually works, and ship an app where the frontend and backend talk to each other correctly.

## What You Need to Know

You don't need to memorize how servers work. You need to understand a handful of concepts so you can describe what you want clearly and catch problems in what AI gives you back.

**How requests and responses work:** Every time your app needs data or needs to save something, it sends a request to the server, and the server sends back a response. Think of it like ordering at a counter—you ask for something (the request), someone in the back makes it, and they hand it to you (the response). If you don't understand this loop, you can't tell AI what to build.

**What an API endpoint is:** An API endpoint is a specific address on your server that does one thing. For example, /api/orders might be the address that handles everything about orders— creating them, listing them, updating them. When you tell AI "create an endpoint for managing orders," this is what gets built. Think of endpoints as doors into your app's backend—each one leads to a specific room.

**REST basics (the most common pattern):** REST is a set of rules for how your frontend talks to your backend. It uses simple actions: GET means "give me data," POST means "save new data," PUT means "update existing data," DELETE means "remove this." Your AI tool will build REST APIs by default. You need to know these four words so you can check that AI used the right one.

**What happens when things go wrong:** Your backend needs to handle errors—what happens when someone sends bad data, or the database is down, or a user asks for something that doesn't exist? AI often builds the "happy path" (everything works perfectly) and skips the error handling. You need to check for this every time.

**The vibecoder workflow for backends:** Describe what should happen when a user takes an action → AI builds the endpoint → you test it by sending a request and checking the response → you tell AI what to fix → repeat until it works → ship it. Same loop as frontend, but you're checking behavior instead of appearance.

## Your Toolkit

Your AI coding tool builds the backend. These tools help you test and verify it.

**AI coding tool (pick one):** Cursor, Lovable, Bolt, Claude Code, Windsurf, or whatever AI- assisted builder you prefer. This is where you'll describe your backend logic and iterate on the output.

**An API testing tool:** Postman or Thunder Client lets you send requests to your API and see exactly what comes back—without using your app's frontend. Think of it as a way to talk directly to your backend and check its answers.

**Your browser's network tab:** Chrome DevTools has a Network tab that shows every request your app makes behind the scenes. When something isn't working, this is where you look first— it shows you exactly what was sent and what came back.

## Certification Exam Topics

Every exam question is scenario-based. You'll see a situation and need to identify what's right, what's wrong, or what to do next. Here's what gets tested:

**Request and response basics:** Can you identify what type of request (GET, POST, PUT, DELETE) your app should use for a given action?

**Endpoint design:** Can you tell whether AI organized your API endpoints in a clean, logical way —or created a confusing mess of URLs?

**Error handling:** Can you spot when AI built an endpoint that only works when everything goes perfectly and breaks silently when something goes wrong?

**Data validation:** Can you identify when an endpoint accepts any data without checking it first— like saving an order with no price or a user with no email?

**Status codes:** Do you know what it means when your API returns a 200 (success), 404 (not found), or 500 (server broke)—and can you check that AI uses the right ones?

**Request/response format:** Can you read a JSON response from your API and verify it contains the right data in the right structure?

**Server-side logic:** Can you describe a business rule (like "don't let users order more than 10 items") and verify AI implemented it correctly?

**Your AI workflow:** Can you describe a backend feature clearly, test the result with an API tool, give AI useful feedback when the output is wrong, and iterate to a working result?

## Common Pitfalls

These are the mistakes vibecoders make most often at this layer. No judgment—they're easy to make. But if you recognize any of them in your own workflow, fix them before sitting for the exam.

Only testing the happy path. Your endpoint works when you send perfect data. What about empty fields, missing values, or someone sending the wrong data type? AI almost never builds error handling unless you specifically ask for it.

Not checking what your API actually returns. AI built the endpoint, you see it "works," but you never looked at the actual response data. It might be returning sensitive information like passwords, internal IDs, or data the user shouldn't see.

Skipping authentication on endpoints that need it. AI creates an endpoint for deleting accounts but doesn't check if the person making the request is actually allowed to do that. Always verify that protected actions require a logged-in, authorized user.

Building everything as one giant endpoint instead of separate, focused ones. If your /api/do- everything endpoint handles orders, users, and payments, you have a maintenance nightmare.

Each endpoint should do one clear thing.

Not thinking about what happens when your server is slow or down. Your frontend shows a loading spinner forever, or worse, silently fails. Every request needs a timeout and a clear "something went wrong" message.

Treating AI's first backend output as production-ready. Backend code has the same first-draft problem as frontend code—it works for the demo but breaks under real conditions. Always test with realistic data and edge cases.

## Self-Assessment Checklist

Before you take the exam, run through these questions. Every "no" is something to work on.

Can you describe a backend feature to AI clearly enough that you get a working endpoint on the first or second try?

Have you tested your API endpoints with an API testing tool (not just through your app's frontend)?

Can you read a JSON response and verify it contains the right data in the right structure?

Do your endpoints return helpful error messages when something goes wrong—not just a blank 500 error?

Have you checked that your endpoints validate incoming data before processing it?

Can you open your browser's network tab and trace a request from button click to server response?

Do you know the difference between GET, POST, PUT, and DELETE—and can you tell when AI used the wrong one?

## AI Audit Prompt Template

Copy this prompt into your AI coding tool to get a quick health check on your backend. It checks the same things the certification exam covers.

> Review my app's backend API and check the following. For each one, tell me pass or fail with a specific example:
>
>
>
> Endpoint organization: Are my API endpoints logically organized with consistent naming and proper HTTP methods (GET, POST, PUT, DELETE)?
>
>
>
> Error handling: Does every endpoint handle errors gracefully—returning helpful error messages with correct status codes instead of crashing silently?
>
>
>
> Input validation: Does every endpoint check incoming data before processing it—rejecting missing fields, wrong data types, and invalid values?
>
>
>
> Authentication: Are protected endpoints properly checking that the user is logged in and authorized before allowing the action?
>
>
>
> Response quality: Are responses returning only the data the frontend needs— not leaking sensitive fields like passwords, internal IDs, or private user data?
>
>
>
> Performance: Are there any endpoints that will be slow under load—missing pagination, loading too much data at once, or making unnecessary database calls?
>
>
>
> Give me an overall score out of 6 and list the top 3 things to fix first.

## What’s Next

Once you've gone through this study guide and can answer "yes" to the self-assessment checklist, you're ready for the Layer 2 certification exam at your target tier.

The best way to prepare: build something real. Pick a project that needs a backend—even a simple one like a contact form that saves to a database—and go through the full loop. Describe it to AI. Test the endpoints. Check error handling. Fix the gaps. Ship it. Every mistake you catch during building is exactly what the exam tests.

## Certification Pathway

Associate Builder: Pass all 13 layers at Tier 1 Certified Builder: Pass all 13 layers at Tier 1 + Tier 2 MADE Certified: Pass all 39 tier exams + capstone project Each exam requires 80% to pass. You can retake after a 24-hour cooldown. No rush—take the time to build something real first.

———

Ready? Take the [Layer 2: APIs & Backend Logic Exam →](https://the-faction.mn.co/posts/the-foundation-layer-2-apis-backend-logic-exam)

---

## Discussion

**Awie Hoh** · 2026-07-01

> This is my own take on layer 2:
> 
> **02. Backend / API**
> 
> PURPOSE
> 
> The backend is the trusted control layer. It receives requests, verifies them, runs business rules, talks to database/storage, and returns safe responses.
> 
> PRINCIPLE
> 
> Treat every request as untrusted until proven safe (Principle 4). No protected action runs until identity, permission, scope, input, and business rules are all verified. Identity itself is established by Auth & Permissions (#4); this layer enforces what a verified identity may do.
> 
> ENDPOINT CONTRACT — every endpoint declares
> 
> - Purpose (the one thing it does)
> 
> - Method and path
> 
> - Required input
> 
> - Returned output
> 
> - Access rule (who may call it, on which records)
> 
> - Validation rule
> 
> - Business rule
> 
> - Failure behavior
> 
> Keep each endpoint to one clear job. Use clean, predictable, resource-based paths. No catch-all endpoints like /api/do-everything. Naming stays consistent across the app.
> 
> REQUEST METHODS
> 
> GET reads. POST creates or starts an action. PUT replaces a full record. PATCH updates part. DELETE removes. Never use GET for anything that changes data.
> 
> ACCESS CONTROL (FIRST LOCK)
> 
> Every route, server action, webhook, file action, admin endpoint, and background trigger must check: who is calling, what they may do, and which user/team/project/account/record/file they may touch. Reject unauthorized requests before reading, changing, or exposing anything. Never trust frontend state, hidden routes, client checks, or user-submitted ownership fields. Backend checks AND database rules (#8) are both required — one lock is not enough (Principle 3).
> 
> INPUT VALIDATION
> 
> Validate all input on the server before use — route values, query values, form fields, JSON bodies, file data, webhook payloads. Reject anything missing, malformed, oversized, unsafe, or out of scope. Never accept sensitive fields from the client: user ID, owner ID, team ID, role, permission level, price, status, payment state, admin flags. Frontend validation is for experience; server validation is the protection.
> 
> REQUESTS AND RESPONSES
> 
> Clear, consistent JSON. Requests carry only the fields the endpoint needs. Responses return only the fields the requester is allowed to see. Never return secrets, passwords, tokens, keys, stack traces, internal details, or data outside the requester's scope.
> 
> BUSINESS LOGIC
> 
> Important rules live on the server, never the frontend — order limits, ownership of edits, payment steps, protected status changes. Keep rules centralized, reusable, testable. Use transactions when multiple changes must succeed or fail together. Repeated or retried requests must not double-create, double-charge, double-send, or corrupt data.
> 
> DATA ACCESS
> 
> Every query is scoped to the correct user/team/project/account/record/file. List, search, export, and reporting endpoints are high-risk — they can leak many records at once. Return the minimum data needed; paginate large lists; load only needed fields.
> 
> FILES
> 
> Uploads and downloads are protected actions. Check identity, permission, ownership, file type, file size, and destination before allowing access. Private files never sit behind public URLs unless intentionally public.
> 
> EXTERNAL SERVICES
> 
> Keep keys, secrets, and credentials on the server only. Verify webhooks before trusting them. Time out external calls and handle their failures safely. Never let an outside service corrupt internal data.
> 
> STATUS CODES
> 
> 200 succeeded. 201 created. 204 succeeded, no body.
> 
> 400 bad request. 401 not logged in. 403 logged in but not allowed. 404 not found.
> 
> 409 conflict with current state. 422 valid shape, invalid business data. 429 too many requests.
> 
> 500 server error.
> 
> Never return 200 for a failed action. Never use 500 for an expected user mistake.
> 
> FAILURE TAXONOMY — every endpoint must handle, and be tested against, each case
> 
> 1. Happy path (success)
> 
> 2. Missing input
> 
> 3. Invalid input or wrong type
> 
> 4. Oversized input
> 
> 5. Not logged in (401)
> 
> 6. Logged in but forbidden / wrong owner (403)
> 
> 7. Missing record (404)
> 
> 8. Duplicate or retried request
> 
> 9. Conflict with current state (409)
> 
> 10. Third-party failure or timeout
> 
> 11. Database failure
> 
> 12. Unexpected server error
> 
> Handle every case safely: clear, safe messages to the user; useful detail in logs. Never expose stack traces, secrets, or database errors to users — and never write secrets or sensitive personal data into logs either. No endpoint may work on the happy path alone.
> 
> PERFORMANCE
> 
> Avoid wasteful queries, repeated calls, and oversized responses. Move long-running work to background jobs. Rate limiting is #9; caching is #10.
> 
> TESTING
> 
> Test with an API tool, not only through the frontend. Run every case in the failure taxonomy, inspect the actual JSON, and confirm the data is correct, safe, and properly shaped. Use the browser network tab to trace a request from click to response.
> 
> AI WORKFLOW
> 
> Give the AI the full endpoint contract above, then iterate against the failure taxonomy — test it, read the JSON, check status codes, check denied access, check edge cases, give specific feedback, repeat until it is safe, correct, and predictable.
> 
> SHIP GATE — do not ship unless all are true
> 
> ☐ Access enforced on every route, action, webhook, and trigger
> 
> ☐ All input validated server-side; no sensitive fields trusted from client
> 
> ☐ Business rules run server-side
> 
> ☐ Responses leak no secrets or out-of-scope data
> 
> ☐ Correct status codes; never 200 on failure
> 
> ☐ Every failure-taxonomy case handled and tested
> 
> ☐ No secrets in responses or logs
> 
> ☐ Protected actions cannot bypass Backend/API (#2), Auth (#4), Database (#3), or RLS (#8)

**Morten Skandshus** · 2026-07-26

> When reading this I’m unsure if this webpage is the actual study guide or if it’s just summarizing what the topics are and then we are supposed to look elsewhere on the website for it? Or is every tier just a single page like this one here?

  ↳ **Matt Murphy** · 2026-07-26

  > You are correct this is the actual study guide. There’s nothing else to download, you can take this study guide, copy the contents, drop it into your AI assistant and it will take you through the process of understanding, configuring, and testing an API and then prepare you for the exam, which is the next step in the process.

  ↳ **Morten Skandshus** · 2026-07-26

  > Ooh so there is no specific (read this) ?? We’re just supposed to read the single page and then go at it in our own Claude sessions? Well that’s a different approach :-)

  ↳ **Matt Murphy** · 2026-07-26

  > [Morten Skandshus](https://the-faction.mn.co/members/40706738) it is designed for you to use the guide and your AI Assistant to follow the steps in the guide while building something simultaneously, the way an AI directed engineer works.

  ↳ **Matt Murphy** · 2026-07-27

  > [Morten Skandshus](https://the-faction.mn.co/members/40706738) thank you again for your feedback, with it we made some updates to the messaging on this page to improve the process.


---
_Source: https://the-faction.mn.co/posts/102891560_
