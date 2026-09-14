---
course: "The Mastery"
module: "Module 5: Versioning and Error Design"
lesson: "Module 5: Versioning and Error Design — Exam"
type: "course_quiz"
post_id: 106571042
space_id: 24191170
source: "https://the-faction.mn.co/posts/106571042"
updated: "2026-08-28T16:21:47Z"
---

# Module 5: Versioning and Error Design — Exam

> Exam for **Module 5: Versioning and Error Design** (The Mastery) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. This module frames an API as a promise you must keep while still improving the product. What two disciplines does it say let you evolve without betrayal?

- **A.** Versioning and error design, since versioning lets you ship new behavior without forcing existing integrations to change on your schedule  ✅
- **B.** Caching and rate limiting, since controlling traffic and storing responses is what keeps an evolving API stable enough for developers
- **C.** Metering and billing, since accurate usage tracking is what preserves the trust an API needs to introduce new behavior over time
- **D.** Monitoring and SLAs, since reliability guarantees are what allow an API to change while developers continue to depend on its uptime

> **Answer:** A

### Q2. This module recommends URL path versioning as the common product choice. What is its stated advantage over header versioning?

- **A.** It is visible and unambiguous, since a developer can see exactly which version a request targets right there in the URL they are calling  ✅
- **B.** It is more secure, since placing the version in the URL prevents an attacker from downgrading a request to an older, weaker version
- **C.** It is faster, since parsing the version from the path lets the server route requests without reading any of the request headers at all
- **D.** It is required by REST, since the specification mandates that version identifiers live in the resource path rather than in request headers

> **Answer:** A

### Q3. This module gives a rule of thumb for classifying changes. What is it?

- **A.** Public is safe, private is not, since changes to documented behavior break integrations while internal refactors never reach consumers
- **B.** Adding is safe, changing and removing are not, since additive changes leave existing integrations intact while the others break them  ✅
- **C.** Small is safe, large is not, since minor changes rarely disturb consumers while large ones almost always require a new version bump
- **D.** Fast is safe, slow is not, since changes shipped quickly reach developers before they integrate while slow ones strand existing callers

> **Answer:** B

### Q4. A team removes an endpoint abruptly with no notice. What does this module say a deprecation policy and sunset headers would have provided?

- **A.** Lower latency, since announcing a removal in advance lets the router drop the deprecated endpoint from its table and speed up dispatch
- **B.** Better security, since sunset headers signal to attackers that a vulnerable endpoint is being retired before it can be further exploited
- **C.** A scheduled migration instead of a surprise outage, since the API itself would have told developers the endpoint was deprecated and when it stops  ✅
- **D.** Reduced storage, since a published deprecation timeline lets the team delete the old endpoint's data ahead of the actual removal date

> **Answer:** C

### Q5. This module says every error response should have the same shape. What does a consistent error structure let a developer do?

- **A.** Write error handling once and have it work everywhere, since a uniform envelope means they do not need custom handling per endpoint  ✅
- **B.** Cache errors safely, since a consistent structure lets the caching layer store failed responses and reuse them for later callers
- **C.** Skip the documentation, since errors with a predictable shape are self-explanatory and remove the need for any reference material
- **D.** Bypass rate limits, since a uniform error format lets the client distinguish a throttled response and retry it outside the normal quota

> **Answer:** A

### Q6. This module lists the components of a good error structure. Which set matches?

- **A.** A timestamp, a request ID, and a retry count, so the developer can trace the failure across their logs and the provider's own systems
- **B.** An HTTP status, a stack trace, and a server hostname, so the developer can see exactly where inside the provider's system the call failed
- **C.** A machine-readable code, a human-readable message, and often a link to the relevant documentation, so the developer knows what and how to fix  ✅
- **D.** An encrypted token, a signature, and a nonce, so the error payload cannot be forged or replayed by an attacker probing the endpoint

> **Answer:** C

### Q7. This module classifies changing a field's type as which kind of change?

- **A.** Non-breaking, since a type change preserves the field name and existing consumers continue to find the data where they expect it
- **B.** Breaking only for writes, since a type change affects request bodies but leaves the response parsing on existing integrations untouched
- **C.** Non-breaking if documented, since noting the new type in the changelog is enough to keep existing integrations working correctly
- **D.** Breaking, since consumers parsing the old type suddenly fail so a type change requires a new version like renaming or removing a field  ✅

> **Answer:** D

### Q8. This module says a migration guide should let a developer move to a new version without breaking mid-migration. What does that require the API to support?

- **A.** A single cutover date, since forcing every developer to migrate at the same moment is what keeps the transition clean and unambiguous
- **B.** Both versions during the transition window, so developers migrate on their own schedule rather than being forced onto yours all at once  ✅
- **C.** Automatic translation, since the API should silently rewrite old-version requests into new-version calls so no developer effort is needed
- **D.** A frozen changelog, since halting all other changes during a migration is what prevents a developer's integration from breaking partway

> **Answer:** B

### Q9. This module divides errors into categories that map to how a developer should respond. What should a 429 rate-limit error tell the developer to do?

- **A.** Fix their request, since a 429 indicates the request itself was malformed and needs correction before it will be accepted by the server
- **B.** Re-authenticate, since a 429 signals the developer's credentials have expired and a fresh key must be obtained before retrying the call
- **C.** Back off, since a 429 means they are over their limit, and the response should carry headers telling them exactly when to retry  ✅
- **D.** Change nothing and retry immediately, since a 429 is a transient server fault the developer should retry without any backoff at all

> **Answer:** C

### Q10. This module says a 5xx server error signals something different from a 4xx client error. What does a 5xx tell the developer about fault and response?

- **A.** The fault is the client's, so the developer must correct their own request before retrying, since a 5xx indicates a malformed call they sent
- **B.** The fault is yours, not the client's, so the developer should retry rather than change their request, which was well-formed to begin with  ✅
- **C.** The fault is the network's, so the developer should switch regions, since a 5xx means the request never reached the API server at all
- **D.** The fault is the version's, so the developer should upgrade, since a 5xx indicates they are calling a deprecated version being retired

> **Answer:** B

### Q11. This module says consistency matters more than the specific versioning mechanism. Why is consistency the higher priority?

- **A.** Because a consistent scheme is faster to route, since the server can hardcode one version-parsing path rather than supporting several at once
- **B.** Because a consistent scheme ranks better in search, since documentation with one uniform version format is favored by search engines
- **C.** Because the version is part of the contract every request carries, so mixing mechanisms makes the targeted version ambiguous to developers  ✅
- **D.** Because consistency lowers storage cost, since a single versioning mechanism lets the provider keep fewer copies of the reference docs

> **Answer:** C

### Q12. A team believes they shipped a harmless update, but developers report broken integrations. This module names a common cause. What is it?

- **A.** They shipped a breaking change believing it was small, since misjudging breaking versus non-breaking is how APIs break integrations unknowingly  ✅
- **B.** They improved performance, since faster responses arrive before the client is ready and cause existing integrations to time out early
- **C.** They added a new optional endpoint, since introducing routes competes with existing ones and confuses the client's request router
- **D.** They updated the documentation, since changing the docs without changing the code misleads developers into calling endpoints incorrectly

> **Answer:** A

### Q13. This module distinguishes a machine-readable code from a human-readable message in an error. What is the machine-readable code for?

- **A.** A billing reference, since the code ties the failed call to a line item so the customer is not charged for requests that errored out
- **B.** A localized phrase the developer reads, since the code exists to explain the failure in the developer's own spoken language clearly
- **C.** A search keyword, since the code's purpose is to help the developer find the matching page in the provider's documentation quickly
- **D.** A stable string the developer's code can branch on, so their integration can react programmatically to a specific error condition  ✅

> **Answer:** D

### Q14. This module lists auth errors as a category. Which status codes and meaning belong to auth errors?

- **A.** 429, meaning the caller has exceeded their allotted request quota and should wait for the window to reset before trying the call again
- **B.** 301 and 302, meaning the resource has moved, so the developer should update their integration to call the new location going forward
- **C.** 500 and 503, meaning the server encountered a fault or is temporarily unavailable, so the developer should retry that same request later
- **D.** 401 and 403, meaning a key is missing, invalid, or lacks permission, so the developer must fix their credentials or their access scope  ✅

> **Answer:** D

### Q15. This module says an API where every endpoint returns errors in a different shape signals carelessness. What concrete burden does it place on consumers?

- **A.** It slows every call, since the client must inspect each endpoint's unique error format before it can parse the response it received back
- **B.** It forces custom error handling per endpoint, since inconsistent error shapes mean a developer cannot reuse one handler across the API  ✅
- **C.** It breaks caching, since varied error shapes cannot share a cache key and force the client to store each endpoint's errors separately
- **D.** It exposes the backend, since differing error formats reveal which internal service produced each response to anyone probing the API

> **Answer:** B

### Q16. This module says removing an endpoint is a breaking change. Which other change does it also classify as breaking?

- **A.** Adding a new optional query parameter, since any new parameter alters the request signature that existing integrations depend upon
- **B.** Adding a new response field, since expanding the payload changes its overall structure and forces existing parsers to be fully rewritten to match
- **C.** Adding a new endpoint, since introducing a route changes the API surface that existing integrations were originally written against
- **D.** Making an optional parameter required, since callers that previously omitted it suddenly send an invalid request without changing anything  ✅

> **Answer:** D

### Q17. This module describes sunset and deprecation headers as in-band communication. What does in-band mean in this context?

- **A.** The API itself tells the developer, in the response, that the endpoint is deprecated and when it will stop working, rather than only via email  ✅
- **B.** The headers are encrypted, since in-band signaling means the deprecation notice travels inside a secured channel only the client can read
- **C.** The headers appear only in the sandbox, since in-band communication is limited to the testing environment before a change reaches production
- **D.** The headers replace the changelog, since in-band means the response is the only place a deprecation is ever announced to developers at all

> **Answer:** A

### Q18. This module says signaling the right error category tells the developer whether to do one of three things. Which three?

- **A.** Upgrade, downgrade, or stay, since the category tells the developer which API version their failing request should be moved to next
- **B.** Fix their code, back off, or simply retry, since that is exactly the information a developer needs when a call fails unexpectedly  ✅
- **C.** Cache, refresh, or expire, since the category tells the client how long to store the failed response before attempting the call again
- **D.** Log, alert, or ignore, since the category tells the developer's monitoring system how loudly to escalate the failure internally

> **Answer:** B

### Q19. This module says a version cutover with no overlap and no guide has a specific consequence. What is it?

- **A.** You lose the developers who trusted you most, since forcing an abrupt migration breaks the integrations of your most committed users  ✅
- **B.** You improve performance, since retiring the old version immediately frees the capacity that maintaining two versions would have consumed
- **C.** You simplify the docs, since removing the old version at once lets you delete its entire reference and present only the current API
- **D.** You strengthen security, since a clean cutover eliminates the older version's attack surface faster than a gradual migration would

> **Answer:** A

### Q20. This module lists query-parameter versioning as one option. What downside does it note?

- **A.** It is invisible, since placing the version in a query parameter hides it from the developer more thoroughly than header versioning does
- **B.** It breaks caching, since a version query parameter changes the cache key on every request and prevents any response from being reused
- **C.** It is insecure, since query-parameter versions appear in server logs where an attacker could read them and target older versions
- **D.** It clutters requests, since carrying the version as a query parameter adds noise to every URL even though the approach is simple  ✅

> **Answer:** D

### Q21. This module says you design the error envelope once and apply it universally. What is the payoff of a single universal envelope?

- **A.** Lower latency, since one envelope format lets the server serialize every error through a single fast code path rather than many
- **B.** A developer writes error handling once and it works across every endpoint, since consistency is the entire point of the shared envelope  ✅
- **C.** Smaller payloads, since a universal envelope compresses better than any per-endpoint formats and reduces the bandwidth each error consumes
- **D.** Automatic versioning, since a single envelope encodes the version in every error and pins the client to the release it first called

> **Answer:** B

### Q22. This module says a deprecation policy states how much notice developers get. Why publish that timeline rather than removing things when convenient?

- **A.** It turns removal from a surprise outage into a scheduled migration developers can plan around, preserving their trust in the platform  ✅
- **B.** It lowers cost, since a published timeline lets the provider batch removals together and retire multiple endpoints in a single release
- **C.** It improves ranking, since documenting deprecation timelines produces pages that rank for version-related developer search queries
- **D.** It satisfies REST, since the specification requires a formal deprecation policy before any endpoint may be removed from a public API

> **Answer:** A

### Q23. A developer asks whether adding a brand-new endpoint to your API will affect their existing integration. How does this module classify that change?

- **A.** Breaking, since any addition to the API surface changes the contract and requires existing consumers to update before calling again
- **B.** Breaking unless versioned, since even a new endpoint must be placed behind a fresh version number to remain safe for current callers
- **C.** Non-breaking only in beta, since additive changes are safe before general availability but require a version bump once the API is stable
- **D.** Non-breaking, since a new endpoint does not disturb existing integrations, which simply continue calling the routes they already use  ✅

> **Answer:** D

### Q24. A developer receives a failure and cannot tell whether to correct their request, wait, or just try again. This module says the API failed to do what?

- **A.** Encrypt the response, since the developer's confusion stems from an error payload that was not signed and therefore could not be trusted
- **B.** Cache the error, since a cached failure would have carried the guidance the developer needed to decide how to respond to the problem
- **C.** Signal the right category with the right status code, since the category is exactly what tells a developer to fix, back off, or retry  ✅
- **D.** Rate-limit the caller, since only a throttled response carries the headers a developer reads to decide whether to retry the failed call

> **Answer:** C

### Q25. Looking across everything in this module, what is the governing principle for versioning and error design?

- **A.** Version aggressively and often, because shipping frequent new versions signals an actively maintained API that developers prefer to adopt
- **B.** Hide the version from developers, because a clean URL with no visible version is what makes an API feel modern and simple to integrate
- **C.** Evolve without betrayal: version deliberately, classify changes honestly, and return consistent actionable errors so integrations keep working  ✅
- **D.** Return one generic error for all failures, because a single uniform message is the simplest contract for a developer to handle in code

> **Answer:** C


---
_Take it in the browser: https://the-faction.mn.co/posts/106571042_
