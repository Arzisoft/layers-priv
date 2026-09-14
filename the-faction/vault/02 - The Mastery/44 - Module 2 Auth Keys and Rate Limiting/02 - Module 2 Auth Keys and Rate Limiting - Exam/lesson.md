---
course: "The Mastery"
module: "Module 2: Auth Keys and Rate Limiting"
lesson: "Module 2: Auth Keys and Rate Limiting — Exam"
type: "course_quiz"
post_id: 106571074
space_id: 24191170
source: "https://the-faction.mn.co/posts/106571074"
updated: "2026-08-28T16:17:57Z"
---

# Module 2: Auth Keys and Rate Limiting — Exam

> Exam for **Module 2: Auth Keys and Rate Limiting** (The Mastery) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. An auditor finds API keys stored in plaintext in the database. Why does this module treat that as a serious lifecycle failure?

- **A.** Plaintext keys cannot be rate limited, since the limiter needs a hashed key to look up the tier and quota associated with the caller
- **B.** Plaintext keys load slowly, since the database must read the full key string on every request instead of comparing a short hash value
- **C.** A database breach hands over every live key at once, so keys must be stored hashed and shown to the developer only once at creation  ✅
- **D.** Plaintext keys break versioning, since the version identifier is normally embedded in the hash and cannot be recovered from raw text

> **Answer:** C

### Q2. A developer needs to replace a key that may have leaked, without taking their integration offline. What does key rotation require the system to support?

- **A.** A single global key, since rotation means replacing the one shared credential that every integration uses at the same moment
- **B.** Multiple active keys during a transition, so the developer can issue a new key and retire the old one with no downtime between them  ✅
- **C.** A full redeploy, since rotating a key requires restarting the service to load the new credential into the application's memory
- **D.** Manual support intervention, since only the API provider can swap a key and the developer must open a ticket to have it done

> **Answer:** B

### Q3. An API acts on behalf of end users who must consent to sharing their data in a third-party app. Which auth mechanism does this module say fits?

- **A.** A single API key, since one shared credential is the simplest way to authorize all calls regardless of which user the data belongs to
- **B.** OAuth tokens, since they represent a specific user's delegated permission and are the right choice when calls carry a user's consent  ✅
- **C.** IP allowlisting, since restricting calls to known addresses is sufficient to represent which users have agreed to share their data
- **D.** A read-only key, since limiting the credential to reads is how you ensure the third-party app cannot exceed what users consented to

> **Answer:** B

### Q4. This module says rate limits should be enforced per key rather than globally. What problem does per-key enforcement prevent?

- **A.** Key leakage, since enforcing limits per key is what stops a stolen credential from being used outside the customer's own infrastructure
- **B.** Billing errors, since a per-key limit is the only mechanism that can tie usage back to the specific customer who should be charged for it
- **C.** Version drift, since per-key limits are recalculated each release and keep the quota aligned with the current version of the API contract
- **D.** One customer's traffic starving another's, since a global limit lets a single heavy caller consume that capacity meant for everyone else  ✅

> **Answer:** D

### Q5. This module says usage tiers turn the API into a product with a pricing page. What mechanism makes upgrading a customer a configuration change rather than a code change?

- **A.** The tier lives in the URL, so moving a customer up a plan means issuing them a new versioned endpoint path with higher limits attached
- **B.** The tier lives in the code, so each pricing level runs a separate deployment that the customer is routed to when they upgrade their plan
- **C.** The tier lives on the key, so free, pro, and enterprise are the same API with different key configurations for limits, scopes, and features  ✅
- **D.** The tier lives in the docs, so upgrading a customer is a matter of granting them access to documentation for the higher-tier features

> **Answer:** C

### Q6. A read-only key issued to an analytics integration leaks. Why does this module say scoping the key limited the damage?

- **A.** A read-only key cannot mutate data if it leaks, which contains the blast radius so a compromise cannot be used to change anything  ✅
- **B.** A read-only key expires faster, since scoped credentials carry a shorter lifetime that closes the exposure window automatically on leak
- **C.** A read-only key is rate limited harder, since scoping a credential to reads automatically lowers its request quota to a safer level
- **D.** A read-only key is stored differently, since scoped credentials are the only keys the system keeps hashed rather than in plaintext

> **Answer:** A

### Q7. A developer hits a rate limit and receives a bare 429 with no headers and no message. What does this module say happens next?

- **A.** The developer churns, since an opaque 429 with no guidance leaves them unable to adapt, where a clear header and backoff path retains them  ✅
- **B.** The developer is protected, since an opaque limit response hides your policy from abusers who might otherwise game the exact thresholds
- **C.** The developer's tooling retries automatically, since a 429 alone is a complete signal that standard client libraries know how to handle
- **D.** The developer is upgraded, since hitting the limit with no explanation is the trigger that automatically moves them to the next paid tier

> **Answer:** A

### Q8. This module says API keys and OAuth tokens solve different problems. When is a plain API key the appropriate choice?

- **A.** Consumer mobile apps, since end users find pasting an API key simpler than completing an OAuth consent flow on a small screen
- **B.** Server-to-server access where one party owns both ends, since a key identifies an application or account without per-user consent  ✅
- **C.** Any case involving user data, since API keys are inherently more secure than tokens and should be preferred wherever data is sensitive
- **D.** High-volume public APIs, since keys are the only credential type that can be rate limited, while OAuth tokens cannot carry a quota

> **Answer:** B

### Q9. This module says rate limits should be enforced at the edge, before expensive work runs. What is the benefit of enforcing limits that early?

- **A.** It improves accuracy, since counting requests at the edge is the only place that limiter can observe the true order of incoming calls
- **B.** It simplifies billing, since edge enforcement is where usage is metered and the two systems must share the same counting location
- **C.** A rejected over-limit request never consumes the costly processing behind it, protecting both cost and capacity from abusive traffic  ✅
- **D.** It enables versioning, since the edge is where the version is parsed and rate limits can only be applied after the version is known

> **Answer:** C

### Q10. This module frames tier design as balancing two goals. What are they?

- **A.** Speed and accuracy, since a free tier must respond quickly while paid tiers can trade latency for more precise and detailed results
- **B.** Simplicity and security, since fewer tiers are easier to secure while more tiers spread risk across a larger number of credentials
- **C.** Cost and compliance, since the free tier must minimize infrastructure spend while paid tiers fund the audits enterprise buyers require
- **D.** A genuinely useful free tier for adoption, and paid tiers unlocking the volume and features serious users need, for revenue  ✅

> **Answer:** D

### Q11. An auditor reviews a key system where a compromised key cannot be killed until the next deployment. What lifecycle capability is missing?

- **A.** Rotation, since the ability to issue a replacement key is what lets a developer move off a compromised credential without downtime
- **B.** Instant revocation, since a compromised or retired key must be killable immediately rather than surviving until a future release  ✅
- **C.** Allowlisting, since restricting the key to known IPs is the mechanism that neutralizes a stolen credential used from elsewhere
- **D.** Scoping, since limiting a key's permissions is what would have prevented the compromise from being exploitable in the first place

> **Answer:** B

### Q12. This module describes IP allowlisting as a containment control. What does allowlisting actually accomplish for a leaked key?

- **A.** It rotates the key, since binding a credential to an address list forces the system to reissue it whenever the customer's IPs change
- **B.** It hashes the key, since allowlisting stores the credential alongside its permitted addresses in a combined hash for verification
- **C.** It renders a stolen key useless outside the customer's known infrastructure, since the key only works from the allowed addresses  ✅
- **D.** It upgrades the key's tier, since restricting a credential to specific IPs signals an enterprise customer and raises its limits automatically

> **Answer:** C

### Q13. This module says key scoping follows the principle of least privilege. What does that principle require of every key?

- **A.** A key should carry only the access its actual job requires, so a credential built for one narrow task cannot be abused for others  ✅
- **B.** A key should carry the maximum access available, since granting broad permissions up front avoids the friction of later scope changes
- **C.** A key should carry no scope at all, since scoping adds complexity and every authenticated key should be able to reach every endpoint
- **D.** A key should carry the same scope as every other key, since uniform permissions make the system easier to reason about and audit

> **Answer:** A

### Q14. This module says transparency is the other half of rate limiting. Which set of surfaces communicates limits to well-behaved developers?

- **A.** The version path, the changelog, and the migration guide, since developers learn their limits from how the API evolves over releases
- **B.** The billing dashboard alone, since a developer's usage limits are a financial concern best surfaced only where they see their invoice
- **C.** Response headers showing remaining quota and reset time, clear documentation, and error messages naming the exact limit that was hit  ✅
- **D.** The status page and postmortems, since rate limits are an operational concern communicated through the same channels as outages

> **Answer:** C

### Q15. An abuse-detection system watches for usage that does not match a customer's tier. Why is that pattern worth flagging?

- **A.** It indicates a versioning error, since usage exceeding a tier means the customer is calling an endpoint from the wrong API version
- **B.** It indicates a billing bug, since any mismatch between tier and usage is always caused by the metering system miscounting requests
- **C.** It indicates a documentation gap, since customers only exceed their tier when the docs fail to explain what their plan actually includes
- **D.** It can signal abuse such as a spike, credential stuffing, or scraping, which is exactly what tier-aware detection exists to catch early  ✅

> **Answer:** D

### Q16. This module says keys should be generated with sufficient entropy. What risk does weak key entropy create?

- **A.** Slow lookups, since low-entropy keys collide in the database index and force the system to scan multiple rows to authenticate a caller
- **B.** Version conflicts, since low-entropy keys reuse identifiers across versions and cause one version's key to authenticate against another
- **C.** Predictable keys an attacker could guess or brute-force, so keys need enough randomness that they cannot be enumerated or forged  ✅
- **D.** Billing drift, since weak keys are harder to attribute to a customer and cause usage to be counted against the wrong account over time

> **Answer:** C

### Q17. This module says the tier is what lets rate limits double as a pricing lever. What makes that dual use possible?

- **A.** The limit is a property of the key's tier rather than a hardcoded value, so pricing changes become configuration, not code changes  ✅
- **B.** Limits are enforced globally, so the single shared cap can be raised for everyone at once whenever the pricing model is adjusted
- **C.** Limits are set in the documentation, so a customer's cap is whatever the published docs state for their plan at the time they signed up
- **D.** Limits are hardcoded constants, so raising a customer's cap requires editing and redeploying the code each time they change plans

> **Answer:** A

### Q18. A developer wants to hand a monitoring tool access to read metrics but never modify anything. Which key capability serves this directly?

- **A.** Rotation support, since being able to replace the key regularly is what limits the monitoring tool's ability to modify data over time
- **B.** Instant revocation, since the ability to kill the key later is what makes it safe to grant the monitoring tool broad access for now
- **C.** IP allowlisting, since binding the key to the monitoring tool's address is what prevents it from writing to protected endpoints
- **D.** Read-only scoping since a key restricted to reads lets the monitoring tool observe data while being unable to mutate anything at all  ✅

> **Answer:** D

### Q19. This module says a rate-limited developer who gets a clear header and documented backoff path behaves differently from one who does not. How?

- **A.** They adapt, since knowing exactly what limit was hit and when it resets lets them implement backoff instead of abandoning the API  ✅
- **B.** They upgrade immediately, since a clear limit message is designed primarily to push developers toward purchasing the next paid tier
- **C.** They file a ticket, since even a well-documented limit prompts developers to confirm with support before adjusting their integration
- **D.** They switch versions, since the reset headers point developers to a newer API version with higher limits than the one they are on

> **Answer:** A

### Q20. An auditor sees that every customer shares one API key embedded in a public client. Which combination of this module's principles does this violate?

- **A.** Versioning and deprecation, since a shared key cannot be tied to a version and therefore cannot be migrated when the API changes
- **B.** Caching and pagination, since a shared key defeats the per-caller cache partitioning that large paginated collections depend upon
- **C.** Latency and throughput, since routing all customers through one key creates a bottleneck that slows every request the client makes
- **D.** Per-key identity, revocation, and least privilege, since a single shared public key cannot isolate customers, be safely revoked, or be scoped  ✅

> **Answer:** D

### Q21. This module says keys are shown once and stored hashed. Why show the key to the developer only at creation?

- **A.** To save space, since displaying the key once means the system never has to allocate storage for the readable version of it again
- **B.** Because the server keeps only a hash, so it cannot redisplay the original later, which is exactly what protects it if the store is breached  ✅
- **C.** To enable rotation, since a key shown only at creation forces the developer to generate a fresh one on a fixed schedule automatically
- **D.** To speed authentication, since a key shown once is cached in the developer's client and never needs to be looked up on the server

> **Answer:** B

### Q22. A prospect asks how your API supports free trials that convert to paid without re-integration. Which mechanism from this module answers that?

- **A.** OAuth tokens, since delegated user consent is what allows a trial account to be converted into a paying account behind the scenes
- **B.** Usage tiers on the key, since a free-tier key can be reconfigured to a paid tier so the customer upgrades without changing their code  ✅
- **C.** IP allowlisting, since binding the trial to known addresses is what lets you safely extend it into a paid relationship over time
- **D.** Sunset headers, since signaling the trial's end date in the response is how the API prompts the customer to convert before access stops

> **Answer:** B

### Q23. A team sets one rate limit in code and applies it to every customer regardless of plan. According to this module, what have they given up?

- **A.** Tiering as a pricing lever, since a limit that is not a property of a key's tier cannot differentiate free, pro, and enterprise plans  ✅
- **B.** Abuse detection, since a uniform limit removes the per-customer baseline the system needs to recognize traffic that looks anomalous
- **C.** OAuth support, since a fixed limit is incompatible with delegated tokens and forces every integration onto plain API keys instead
- **D.** Key rotation, since a single hardcoded limit prevents developers from replacing a credential without also changing their request volume

> **Answer:** A

### Q24. A developer integrating your API asks whether hitting the limit will silently drop their data. What does this module's transparency standard let you promise?

- **A.** That an over-limit request returns a clear 429 with remaining-quota and reset headers, so they can back off rather than lose data blindly  ✅
- **B.** That limits are invisible by design, since a well-built API hides its thresholds so that abusers cannot probe where the caps sit
- **C.** That every over-limit response is unversioned, since rate-limit errors are exempt from the contract and may change shape at any time
- **D.** That the free tier has no limit at all, since transparency means the entry plan must be unlimited to earn a developer's initial trust

> **Answer:** A

### Q25. Looking across everything in this module, what is the governing principle for API keys and rate limiting?

- **A.** Grant every key full access and a shared global limit, because uniform permissions and one cap are the simplest system to operate
- **B.** Prefer OAuth for every integration, because delegated tokens are strictly more secure than keys in all server and client scenarios alike
- **C.** Hide all limits from developers, because revealing quotas and reset times only teaches abusers exactly how to game your thresholds
- **D.** Make access a secure, scoped, tiered, and transparent product surface, because keys and limits are where the API becomes a business  ✅

> **Answer:** D


---
_Take it in the browser: https://the-faction.mn.co/posts/106571074_
