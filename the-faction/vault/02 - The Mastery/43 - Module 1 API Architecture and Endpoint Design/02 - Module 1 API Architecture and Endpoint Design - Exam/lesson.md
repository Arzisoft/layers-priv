---
course: "The Mastery"
module: "Module 1: API Architecture and Endpoint Design"
lesson: "Module 1: API Architecture and Endpoint Design — Exam"
type: "course_quiz"
post_id: 106570938
space_id: 24191170
source: "https://the-faction.mn.co/posts/106570938"
updated: "2026-08-28T16:16:09Z"
---

# Module 1: API Architecture and Endpoint Design — Exam

> Exam for **Module 1: API Architecture and Endpoint Design** (The Mastery) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. A team argues their internal API is fine to expose to external developers as-is. What core reframing does this module say they are missing?

- **A.** The API is now a product whose endpoints are the user interface, so every casual decision becomes a permanent public contract  ✅
- **B.** The API needs a faster database, since external traffic will immediately overwhelm infrastructure that was sized for internal use only
- **C.** The API should be rewritten in a compiled language, since interpreted internal services cannot handle the load a public launch brings
- **D.** The API must move to a different cloud region, since serving external developers requires infrastructure closer to their own systems

> **Answer:** A

### Q2. A developer sees the endpoint /customers/{id}/invoices and immediately guesses /customers/{id}/payments exists. What design property produced that correct guess?

- **A.** Aggressive caching, since cached routes respond fast enough that developers can discover adjacent endpoints by trial and error
- **B.** Consistent, hierarchical resource naming, which makes the URL read like a path to a thing and lets developers predict siblings  ✅
- **C.** Header versioning, since keeping the version out of the URL is what leaves the path clean enough to reason about structurally
- **D.** Rate-limit headers, since the quota information returned on each call is what tells a developer which endpoints are available to them

> **Answer:** B

### Q3. An API returns HTTP 200 with a body containing an error message when a request fails. Why does this module treat that as an amateur signal?

- **A.** It slows the response, since packing an error into a success body forces the client to parse a larger payload than a plain failure
- **B.** It breaks caching, since a 200 with an error body gets cached as a valid response and served again to later callers incorrectly
- **C.** It forces every consumer to write custom handling, because the status code no longer signals success or failure the way tooling expects  ✅
- **D.** It leaks internals, since returning any body on failure exposes stack information the client was never supposed to be able to read

> **Answer:** C

### Q4. An auditor reviews an endpoint that returns an entire customer list with no pagination. What does this module say is wrong with that design?

- **A.** The endpoint should return XML, since large customer lists are more efficiently serialized in a markup format than in plain JSON
- **B.** The endpoint should require authentication, since listing customers is a sensitive operation that must always sit behind a login
- **C.** The endpoint should be a POST, since retrieving large collections is a write-like operation that does not fit the semantics of GET
- **D.** No product endpoint should return an unbounded list, since an ungated collection breaks as soon as the underlying dataset grows large  ✅

> **Answer:** D

### Q5. This module says the version should be part of the contract from the first request. What does choosing a versioning strategy up front actually protect against?

- **A.** The pain of retrofitting versioning onto a live API, since adding a version scheme after developers depend on the API is difficult  ✅
- **B.** Excessive latency, since a version chosen early lets the router cache each version's responses separately for faster delivery overall
- **C.** Documentation drift, since committing to a version number early is what keeps the generated reference synchronized with the code
- **D.** Key leakage, since embedding the version in the URL is what allows per-version key scoping to contain a compromised credential

> **Answer:** A

### Q6. A team wants to add a new optional field to an existing response. According to this module's compatibility rules, how should this change be classified?

- **A.** Breaking, since any change to a response shape forces existing consumers to update their parsing before they can call the endpoint again
- **B.** Non-breaking, since adding an optional field does not disturb existing integrations that simply ignore the fields they do not read  ✅
- **C.** Breaking, since adding a field changes the payload size and therefore invalidates any client that validated the response length strictly
- **D.** Non-breaking only if versioned, since even additive changes require a new version number to remain safe for existing consumers

> **Answer:** B

### Q7. A developer lands on your API with three competing APIs open in other tabs. How does this module say you should design for that developer?

- **A.** Design for maximum feature coverage, since the API with the longest capability list is the one a comparing developer ultimately selects
- **B.** Design for the lowest price, since a developer evaluating several APIs side by side decides primarily on the per-call cost of each option
- **C.** Design for your own team first, since an API that is comfortable for internal engineers will naturally be comfortable for outsiders too
- **D.** Design for a person who has never seen your system, so the endpoints, errors, and docs make that stranger successful as fast as possible  ✅

> **Answer:** D

### Q8. An API uses GET to create a resource and returns 200 whether or not the creation succeeded. Which two REST conventions has it violated?

- **A.** It should use GET but return 204, since creation endpoints should acknowledge success without returning a body to the caller at all
- **B.** It should use PUT to create and return 200 always, since idempotent creation is the only correct pattern for a product-grade API
- **C.** It should use POST to create and return 201 on success, since methods and status codes carry semantics developers already rely on  ✅
- **D.** It should use DELETE to create and return 202, since asynchronous resource creation is the expected default for external APIs

> **Answer:** C

### Q9. This module distinguishes cursor-based from offset-based pagination. When does it say cursor-based pagination is the better choice?

- **A.** For large or shifting datasets, since cursors stay stable as data changes where offsets drift and skip or repeat rows under mutation  ✅
- **B.** For small, stable datasets, since cursors add complexity that only pays off when the collection is tiny and rarely changes at all
- **C.** For write-heavy endpoints, since cursor pagination is the only scheme compatible with resources that are frequently created and deleted
- **D.** For authenticated endpoints, since cursors encode the caller's identity and therefore cannot be used on any public unauthenticated route

> **Answer:** A

### Q10. A developer proposes making a previously optional request parameter required. Why does this module classify that as a breaking change?

- **A.** It changes the response, since requiring a parameter alters the shape of the data the endpoint returns to every existing caller
- **B.** It affects only new integrations, since existing callers already send the parameter and are therefore unaffected by the requirement
- **C.** Existing callers that omit the parameter suddenly fail, since code that worked yesterday now sends an invalid request without changing  ✅
- **D.** It breaks caching, since a newly required parameter changes the cache key and invalidates every previously stored response at once

> **Answer:** C

### Q11. This module recommends URL path versioning as the common product choice over header versioning. What is the stated advantage?

- **A.** It is faster, since routing on the URL path lets the server dispatch versions without parsing any of the request headers at all
- **B.** It is transparent and easy to route, since a developer can see exactly which version a request targets directly in the URL itself  ✅
- **C.** It is more secure, since embedding the version in the path prevents attackers from downgrading requests to an older vulnerable version
- **D.** It is required by REST, since the specification mandates that version identifiers appear in the resource path rather than in headers

> **Answer:** B

### Q12. An API names its endpoints with verbs like /getCustomer and /createInvoice and mixes camelCase with snake_case. What REST naming principle does this violate?

- **A.** Endpoints should return 201, since verb-named routes cannot signal resource creation without a status code that indicates it explicitly
- **B.** Endpoints should be versioned, since inconsistent naming can only be corrected safely by bumping the version and renaming everything
- **C.** Endpoints should be cached, since consistent naming exists primarily to give the caching layer predictable keys to store responses under
- **D.** Resources should be nouns named consistently, so the URL reads as a path to a thing and developers can predict adjacent endpoints  ✅

> **Answer:** D

### Q13. This module says status codes are a contract developers' tooling already understands. What is the practical benefit of using 429 correctly for rate limiting?

- **A.** That developer's existing tooling and instincts recognize rate limiting without translation, so their retry logic behaves as expected  ✅
- **B.** It reduces server load, since a 429 response is smaller than a normal payload and therefore costs less bandwidth to return to abusers
- **C.** It hides the limit, since 429 is an opaque code that lets you throttle abusive callers without revealing your actual rate-limit policy
- **D.** It bypasses versioning, since rate-limit responses are exempt from the version contract and can change shape freely between releases

> **Answer:** A

### Q14. A team plans to rename a response field in the next release because the new name reads better. What does this module advise, given developers depend on the API?

- **A.** Rename it freely, since field names are internal implementation details that external consumers should never have hardcoded anyway
- **B.** Do not rename it silently, since renaming a field breaks every integration reading it, so the change belongs in a new version  ✅
- **C.** Rename it only in the documentation, since updating the docs to the clearer name leaves the actual response untouched and safe
- **D.** Rename it but keep the old name as a comment, since documenting the former name is sufficient to protect existing integrations

> **Answer:** B

### Q15. This module says the free experience of guessing the next endpoint is a feature you design for deliberately. What underlying design choice makes guessability possible?

- **A.** Uniform pagination, since a developer who learns the paging scheme once can predict how any collection endpoint will behave next
- **B.** Aggressive rate limiting, since limits force developers to plan their calls and that planning naturally reveals the endpoint structure
- **C.** Predictable, consistent resource hierarchy, so knowing one endpoint's shape lets a developer infer the shape of related endpoints  ✅
- **D.** Detailed error messages, since a developer can enumerate the full endpoint surface by triggering errors on paths they guess at random

> **Answer:** C

### Q16. An API returns 200 for a not-found resource, 200 for an auth failure, and 200 for a server crash. What is the downstream cost this module identifies?

- **A.** Every consumer must write custom logic to detect failures, since that status code no longer tells them whether the call succeeded  ✅
- **B.** The responses are cached incorrectly, since a uniform 200 means the caching layer stores failures and serves them to later callers
- **C.** The API cannot be versioned, since consistent status codes are a prerequisite for expressing version differences across releases
- **D.** The rate limiter fails, since throttling depends on distinguishing 200 from 429 and a uniform code disables the limit enforcement

> **Answer:** A

### Q17. This module says adding is safe while changing and removing are not. What is the reasoning behind treating additive changes as non-breaking?

- **A.** Additive changes are cached separately, since new fields generate new cache keys that isolate them from previously stored responses
- **B.** Additive changes are smaller, since adding a field touches less code than removing one and therefore carries less risk of a regression
- **C.** Additive changes are versioned automatically, since any new field is placed under a new version path that existing callers never reach
- **D.** New endpoints and optional fields do not disturb existing integrations, since consumers ignore what they were not written to read  ✅

> **Answer:** D

### Q18. A developer complains that each of your collection endpoints paginates differently: one uses page numbers, another uses cursors, a third uses limit and offset. Why is this a design failure?

- **A.** It slows the API, since supporting three pagination schemes forces the server to run three separate code paths on every collection call
- **B.** A developer should learn your pagination once and have it work everywhere, so per-endpoint variation is exactly the friction to avoid  ✅
- **C.** It breaks versioning, since inconsistent pagination cannot be expressed in a single version and requires a separate version per scheme
- **D.** It exposes internals, since revealing which pagination scheme each endpoint uses tells an attacker how the underlying storage is indexed

> **Answer:** B

### Q19. This module says you should design the first version assuming you will live with its shape for years. What habit does that assumption instill?

- **A.** Shipping fast and fixing later, since the assumption of longevity means early mistakes can always be corrected in a later version anyway
- **B.** Deferring documentation, since a long-lived shape can be documented later once the design has proven itself stable across many releases
- **C.** Only ever adding, never quietly changing, once developers depend on that API, so the original contract stays intact over its long life  ✅
- **D.** Avoiding pagination, since long-lived endpoints accumulate too much data to page reliably and should return complete datasets instead

> **Answer:** C

### Q20. An enterprise prospect asks how your API handles being depended on by their production systems. Which answer reflects this module's product mindset?

- **A.** The endpoints are versioned and backwards-compatible by design, so their integration keeps working as the product evolves around it  ✅
- **B.** The API is rewritten frequently, so they always get the newest implementation and never have to worry about running on stale code
- **C.** The API returns 200 for everything, so their systems never have to branch on error codes and the integration logic stays simple
- **D.** The endpoints change names as they improve, so their engineers stay engaged by keeping the integration continuously up to date

> **Answer:** A

### Q21. This module says a product API's endpoints are its user interface. What follows from taking that claim seriously?

- **A.** The endpoints should be hidden behind a graphical dashboard, since a real user interface means developers interact through a UI, not URLs
- **B.** The endpoints should require no documentation, since a well-designed interface is self-evident and any need for docs signals a design flaw
- **C.** The endpoints should change often, since a good user interface is continuously redesigned to reflect the latest usability research findings
- **D.** The endpoints, errors, and docs are the surfaces developers judge you by, so they get the care a consumer product's interface receives  ✅

> **Answer:** D

### Q22. A team ships what they believe is a harmless update: they tighten validation on an existing endpoint to reject a format they used to accept. Why might this break integrations?

- **A.** It changes the response shape, since stricter validation returns additional error fields that existing parsers were not written to handle
- **B.** Existing callers sending the old format suddenly fail, since tightening validation is a breaking change even though nothing was removed  ✅
- **C.** It affects only new callers, since existing integrations already send correctly formatted data and are therefore immune to the change
- **D.** It requires a new key, since stricter validation invalidates previously issued credentials that were scoped to the looser format

> **Answer:** B

### Q23. This module frames pagination, filtering, sorting, and field selection as things a developer should learn once. What is the unifying design discipline behind all four?

- **A.** Predictable query parameters that behave the same on every endpoint, so a developer's knowledge transfers across the whole API surface  ✅
- **B.** Aggressive defaults, since setting strict limits on every collection parameter is what prevents developers from overloading the server
- **C.** Per-endpoint customization, since each collection has unique needs that are best served by tailoring its query parameters individually
- **D.** Header-based configuration, since moving pagination and filtering into headers keeps the URLs clean and the parameters out of sight

> **Answer:** A

### Q24. A team nests resources five levels deep, producing URLs like /orgs/{id}/teams/{id}/projects/{id}/tasks/{id}/comments. What does product-API design suggest about this depth?

- **A.** Deeper is always better, since maximally nested URLs encode the full relationship graph and free developers from ever reading the docs
- **B.** Depth should match the database, since the URL hierarchy is correct precisely when it mirrors how the tables are joined underneath
- **C.** Excessive nesting hurts usability, so a product API keeps hierarchies shallow and lets developers reach deep resources by direct identifier  ✅
- **D.** Depth is a security control, since each additional path segment adds an authorization checkpoint that narrows the attack surface further

> **Answer:** C

### Q25. Looking across everything in this module, what is the governing principle for designing a product API?

- **A.** Maximize the number of endpoints, because a larger API surface signals a more capable product that developers will prefer to adopt
- **B.** Optimize for your internal team, because an API that serves your own engineers efficiently will naturally serve outside developers too
- **C.** Ship the minimum and iterate rapidly, because breaking changes are cheap early and developers expect a new API to change constantly
- **D.** Treat the API as a product for a stranger using consistent conventions and add-only evolution so integrations stay reliable for years  ✅

> **Answer:** D


---
_Take it in the browser: https://the-faction.mn.co/posts/106570938_
