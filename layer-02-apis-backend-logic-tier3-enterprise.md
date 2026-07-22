# Layer 2 of 13 — APIs & Backend Logic
**Tier 3 — Enterprise** | Matt Murphy Builder Certification Series

> *Builds on Tiers 1-2 (Solopreneur + Growth). Assumes those concepts and tools are already understood.*

---

## What It Covers

Running a backend operation at enterprise scale. At Tier 3, you're the person responsible for
the whole backend operation — multiple services talk to each other, failures in one system
cascade to others. The job is architecture and governance: making sure the system holds
together under load.

**Core goal:** You can run a backend operation at enterprise scale — overseeing API gateway
architecture, microservices coordination, event-driven systems, and comprehensive monitoring
across a platform that serves thousands of users.

---

## Key Concepts

**API gateways (one front door for everything)** — An API gateway sits in front of all backend
services and acts as a single entry point. Every request comes through the gateway, which
handles authentication, routes the request to the right service, and enforces rate limits — a
receptionist who directs every visitor to the right department.

**Microservices vs. monolith** — A monolith is one big application that does everything.
Microservices split the backend into smaller, independent services — one handles orders,
another payments, another notifications — each built, updated, and scaled separately. Knowing
when this split makes sense vs. creates more problems than it solves is the Tier 3 judgment call.

**Event-driven architecture** — Instead of services calling each other directly, they publish
events ("an order was placed") and other services listen for events they care about. This keeps
services loosely connected — if the email service is down, the order service doesn't break — a
bulletin board where you post a notice and whoever needs it reads it on their own time.

**GraphQL at scale** — An alternative to REST that lets the frontend ask for exactly the data it
needs, no more, no less. At enterprise scale this reduces wasted data transfer but requires
careful management to prevent expensive queries that overload the servers.

**Observability** — At this scale you need more than error logs: tracing a single request as it
flows through multiple services, measuring how long each step takes, and spotting bottlenecks
before they become outages — security cameras in every room, plus a map of which doors people
walk through most.

---

## Toolkit (adds to Tier 2)

- **API gateway (Kong, AWS API Gateway)** — manages all incoming API traffic, authentication, rate limiting, routing, and analytics, from one central control point
- **Event streaming (Kafka, AWS EventBridge)** — handles real-time event publishing and subscription so services can communicate without direct dependencies
- **Distributed tracing (Datadog, Jaeger)** — follows a single request across multiple services to pinpoint exactly where slowdowns or failures happen
- **GraphQL tools (Apollo Server, Hasura)** — tools AI uses to build GraphQL APIs; you direct the schema design and monitor query performance

---

## Certification Exam Topics

- **API gateway architecture** — Can you evaluate how incoming traffic should be routed, authenticated, and rate-limited across multiple backend services?
- **Microservices coordination** — Can you assess when splitting a monolith into microservices is the right call and identify the risks of doing it wrong?
- **Event-driven design** — Can you evaluate whether services are properly communicating through events instead of fragile direct calls?
- **GraphQL governance** — Can you identify when a GraphQL query is too expensive and will overload the server, and describe how to prevent it?
- **Observability setup** — Do you know how to set up tracing, metrics, and logging so you can diagnose issues across a distributed system?
- **Failure isolation** — Can you evaluate whether a failure in one service (like payments) will cascade and take down other services (like orders)?
- **Scalability assessment** — Can you identify bottlenecks in a backend architecture and describe how to handle increased traffic?
- **Safe deployment** — Do you understand canary releases, blue-green deployments, and rollback strategies for backend services that can't afford downtime?

---

## Common Pitfalls

- Only testing the happy path — AI almost never builds error handling unless specifically asked
- Not checking what the API actually returns — it may leak passwords, internal IDs, or data the user shouldn't see
- Skipping authentication on endpoints that need it (e.g. account deletion)
- Building everything as one giant endpoint instead of separate, focused ones
- Not thinking about what happens when the server is slow or down — infinite spinner or silent failure instead of a timeout + clear message
- Treating AI's first backend output as production-ready — it works for the demo, breaks under real conditions

---

## Tier 3 Self-Assessment Checklist

- [ ] Can you describe a backend feature to AI clearly enough that you get a working endpoint on the first or second try?
- [ ] Have you tested your API endpoints with an API testing tool, not just through the app's frontend?
- [ ] Can you read a JSON response and verify it contains the right data in the right structure?
- [ ] Do your endpoints return helpful error messages when something goes wrong, not just a blank 500 error?
- [ ] Have you checked that your endpoints validate incoming data before processing it?
- [ ] Can you open your browser's network tab and trace a request from button click to server response?
- [ ] Do you know the difference between GET, POST, PUT, and DELETE, and can you tell when AI used the wrong one?

---

## AI Audit Prompt (copy into your AI tool)

```
Review my app's backend API and check the following. For each one, tell me
pass or fail with a specific example:
Endpoint organization: Are my API endpoints logically organized with
consistent naming and proper HTTP methods (GET, POST, PUT, DELETE)?
Error handling: Does every endpoint handle errors gracefully, returning
helpful error messages with correct status codes instead of crashing
silently?
Input validation: Does every endpoint check incoming data before processing
it, rejecting missing fields, wrong data types, and invalid values?
Authentication: Are protected endpoints properly checking that the user is
logged in and authorized before allowing the action?
Response quality: Are responses returning only the data the frontend needs,
not leaking sensitive fields like passwords, internal IDs, or private user
data?
Performance: Are there any endpoints that will be slow under load, missing
pagination, loading too much data at once, or making unnecessary database
calls?
Give me an overall score out of 6 and list the top 3 things to fix first.
```

---

## What's Next

Once you've gone through this kit and can answer "yes" to the self-assessment checklist,
you're ready for the Layer 2 certification exam at your target tier.

The best way to prepare: build something real. Pick a project that needs a backend, even a
simple one like a contact form that saves to a database, and go through the full loop.
Describe it to AI. Test the endpoints. Check error handling. Fix the gaps. Ship it. Every
mistake caught during building is exactly what the exam tests.

---

## Certification pathway

Associate Builder = all 13 layers at Tier 1. Certified Builder = all 13 layers at Tier 1 + Tier 2.
MADE Certified = all 39 tier exams + capstone. 80% to pass each exam, 24-hour retake cooldown.
