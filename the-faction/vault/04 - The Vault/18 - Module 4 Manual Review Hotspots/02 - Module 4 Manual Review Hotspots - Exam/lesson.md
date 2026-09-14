---
course: "The Vault"
module: "Module 4: Manual Review Hotspots"
lesson: "Module 4: Manual Review Hotspots — Exam"
type: "course_quiz"
post_id: 106568629
space_id: 24302166
source: "https://the-faction.mn.co/posts/106568629"
updated: "2026-08-28T16:28:10Z"
---

# Module 4: Manual Review Hotspots — Exam

> Exam for **Module 4: Manual Review Hotspots** (The Vault) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. An auditor explains that scanners cannot find a checkout that accepts a negative quantity to generate a credit. Why is this class of flaw invisible to automated tools?

- **A.** The flaw requires understanding the business rule and its intent, which a pattern-matching scanner has no way to model  ✅
- **B.** The flaw lives in minified frontend code, which scanners cannot parse until it has been fully expanded and beautified
- **C.** The flaw only appears under production load, which the scanner never reproduces during a static analysis of the code
- **D.** The flaw is a dependency vulnerability, and scanners only report dependency issues that already exist in a public database

> **Answer:** A

### Q2. The method calls one manual test the single highest-yield check in vibebuilt apps. Which test is it?

- **A.** Confirming the login page rejects an empty password, since weak password handling is the most common vibecode flaw overall
- **B.** Verifying that the homepage loads over HTTPS, since transport misconfiguration is the fastest finding to confirm in nearly any audit
- **C.** Testing whether user A can access user B's data by identifier, since AI checks that you are logged in but not that it is yours  ✅
- **D.** Checking that the error page hides stack traces, since verbose errors are the most frequently replicated configuration issue

> **Answer:** C

### Q3. An auditor finds that user A can load user B's invoice by changing a number in the URL. Given Module 1's lessons, what is the auditor's immediate next move?

- **A.** Report the single endpoint and stop, since one confirmed access-control flaw is a complete and self-contained finding
- **B.** Test the same cross-user access across every resource-fetching route, since replication means the flaw is rarely alone  ✅
- **C.** Rerun the dependency scanner, since broken access control usually originates in an outdated authorization library upstream
- **D.** Downgrade it to medium, since accessing another user's invoice requires knowing their specific identifier number first

> **Answer:** B

### Q4. The method warns that the documented API is a subset of the real one. What does directing endpoint enumeration actually involve?

- **A.** Reading the API documentation carefully, since a thorough read of the docs reveals every route the application exposes
- **B.** Examining the frontend bundle and route definitions, then probing common admin and debug conventions for hidden endpoints  ✅
- **C.** Asking the founder for a route list, since the person who built the app is the authoritative source on its endpoint surface
- **D.** Running the dependency scanner in verbose mode, since it lists each route that every imported framework registers internally

> **Answer:** B

### Q5. An auditor treats any authorization decision made only in frontend code as a suggestion rather than a control. What justifies that stance?

- **A.** Frontend code is harder to scan, so client-side authorization is simply the portion tools are least able to verify reliably
- **B.** Frontend code loads slower than backend code, so authorization there introduces a delay that attackers exploit through timing
- **C.** Frontend frameworks change often, so client-side authorization logic becomes outdated faster than the server equivalent does
- **D.** The browser is attacker-controlled territory, so a check that lives only client-side can be bypassed by calling the endpoint directly  ✅

> **Answer:** D

### Q6. An auditor is hunting for a race condition in a coupon-redemption flow. What defines the race-condition class of business logic flaw?

- **A.** Two requests fired together that both pass a check meant to allow only one, such as redeeming a single coupon twice at once  ✅
- **B.** A single request that carries a manipulated price field the server trusts without recomputing the amount independently itself
- **C.** A multi-step workflow whose final step never rechecks the authorization that its first step originally established for the user
- **D.** An undocumented endpoint that returns sensitive data without any authentication because the route shipped outside the docs

> **Answer:** A

### Q7. The method describes privilege escalation through a workflow. What does that specific flaw look like?

- **A.** A login form that accepts SQL in the username field, escalating a guest directly into an administrator through injection
- **B.** A dependency with a known CVE that grants remote code execution once an attacker reaches the vulnerable code path in it
- **C.** A multi-step process where a later step fails to re-check what an earlier step authorized letting a user exceed their role  ✅
- **D.** A cached response that serves one user's elevated session to another, handing over admin rights through stale authorization

> **Answer:** C

### Q8. An auditor reviewing configuration flags production debug mode as a finding. What makes an enabled debug mode dangerous in production?

- **A.** Debug mode turns every error into an information leak, exposing stack traces, queries, and internals to anyone who triggers one  ✅
- **B.** Debug mode disables the cache, so the origin server absorbs traffic it was never provisioned to handle at production scale
- **C.** Debug mode changes the routing, so undocumented endpoints become reachable that would otherwise stay carefully hidden from attackers
- **D.** Debug mode slows the application, so every request handled in production runs measurably slower and frustrates real users

> **Answer:** A

### Q9. The method frames the auditor's organizing question as: if I wanted to steal data, money, or access, what would I try first? Why is this mindset directable but still demanding?

- **A.** You can prompt AI to enumerate attack scenarios per feature, but applying it deliberately requires thinking about what the builder did not  ✅
- **B.** You can automate it entirely with the right scanner, so the only demand is configuring the tool correctly the first time around
- **C.** You can delegate it to the client, but they must be trained to think adversarially before the results become trustworthy at all
- **D.** You can apply it only to the frontend, so the demand is limited to whichever attack surface the browser happens to expose directly

> **Answer:** A

### Q10. An auditor discovers an admin panel that ships in the route table but appears in no documentation, and it returns data without authentication. Why does the method prize this finding?

- **A.** It confirms the dependency scanner missed a package, since undocumented routes always trace to an unscanned framework internal
- **B.** It is a finding no scanner will hand you since discovering an unauthenticated undocumented endpoint requires manual enumeration  ✅
- **C.** It proves the frontend bundle is exposed, since admin routes only appear in bundles that were shipped without minification first
- **D.** It shows the CORS policy is too open, since undocumented endpoints are reachable only when cross-origin requests are permitted

> **Answer:** B

### Q11. An auditor sees a disabled button in the UI and, rather than trusting it, calls the underlying endpoint directly. What client-side trust assumption is being tested?

- **A.** Whether the button's styling is consistent, since inconsistent disabled states signal rushed frontend work worth flagging later
- **B.** Whether the disabled state persists after refresh, since a button that re-enables on reload indicates a broken caching layer beneath
- **C.** Whether the button triggers an analytics event, since disabled elements that still fire events leak user behavior to third parties
- **D.** Whether the endpoint enforces the same restriction server-side, since a disabled button is not a control if the endpoint still accepts the call  ✅

> **Answer:** D

### Q12. The method lists price manipulation as a business logic flaw. What is the underlying mistake that makes price manipulation possible?

- **A.** The price is stored in an outdated format, so currency rounding errors accumulate into a manipulable discrepancy over time
- **B.** The price is cached too aggressively, so a stale price is served long after the real catalog amount has already changed
- **C.** The price endpoint lacks rate limiting, so an attacker can brute-force different amounts until one is finally accepted by the server
- **D.** A quantity or amount the client controls is trusted by the server, which never independently recomputes the real total itself  ✅

> **Answer:** D

### Q13. An auditor finds permissive CORS accepting any origin during the configuration review. Why does the method treat this as a manual-pass configuration finding?

- **A.** Open CORS disables HTTPS, so the configuration review is the only place transport downgrades of this kind ever become visible
- **B.** Open CORS lets any origin make cross-origin requests against the API, which a code-only review can easily overlook in context  ✅
- **C.** Open CORS increases latency, so the finding belongs in the manual pass because performance is judged by hand rather than by tools
- **D.** Open CORS removes rate limits, so it is reviewed manually alongside the throttling configuration it is functionally part of

> **Answer:** B

### Q14. The method says these manual flaw classes end up on the front page and yet are invisible to every tool. What single reason unifies why tools miss all of them?

- **A.** The tools were misconfigured, since a correctly tuned scanner suite would in fact catch business logic and access-control flaws
- **B.** The tools run too infrequently, since these flaws only appear between scans when new code is generated in a fresh session
- **C.** The tools lack cloud access, since business logic and auth boundaries can only ever be tested from inside the deployment environment
- **D.** They require understanding intent, and a tool cannot know your business rules, your ownership model, or your real endpoint surface  ✅

> **Answer:** D

### Q15. An auditor confirms a user can view their own data and is tempted to move on. What does the method insist they do before considering the boundary tested?

- **A.** Confirm the data loads quickly, since slow self-access indicates a query flaw that often accompanies broken access control
- **B.** Attempt to access another user's data as that same user, since seeing your own records proves nothing about others' records  ✅
- **C.** Verify the data is encrypted at rest, since readable self-data is only safe if the underlying storage is also protected properly
- **D.** Check that the self-access route is documented, since undocumented self-access routes are the ones most likely to lack auth

> **Answer:** B

### Q16. The method says the highest-severity findings in vibebuilt apps consistently live in the manual pass. What structural reason does it give for that concentration?

- **A.** Manual review takes longer, so auditors naturally invest more effort there and therefore record more findings by sheer time spent
- **B.** Automated tools handle the severe findings first, so only the leftover critical issues remain by the time manual review begins
- **C.** AI builds the requested feature and never asks what an adversary would do, leaving those exact gaps for the manual pass to find  ✅
- **D.** Manual findings are rated higher by convention, so the same issue scores more severely when a human rather than a tool reports it

> **Answer:** C

### Q17. An auditor is directing AI to enumerate attack scenarios per feature but keeps their own judgment central. Why does the method insist judgment cannot be fully delegated here?

- **A.** The whole point is thinking about what the builder did not, so the auditor steers the enumeration rather than accepting a default list  ✅
- **B.** AI enumerates too slowly, so the auditor must lead to keep the manual pass within the time budgeted for the engagement overall
- **C.** AI cannot execute the attacks, so a human must manually perform every scenario the model proposes before it counts as tested
- **D.** AI refuses adversarial prompts, so the auditor must rephrase each attack scenario until the model agrees to enumerate it fully

> **Answer:** A

### Q18. An auditor finds a client-computed order total submitted to the server at checkout. What is the correct assessment under this module?

- **A.** Acceptable, since the client and server compute the same total and any tampering would produce an obvious mismatch on submission
- **B.** A performance win, since computing totals client-side offloads work from the server and speeds up the checkout flow for users
- **C.** A finding, since the browser is attacker-controlled and any total it computes can be altered before it reaches the server  ✅
- **D.** A minor issue, since manipulating a total still requires bypassing the payment processor's own independent fraud checks anyway

> **Answer:** C

### Q19. The method describes probing common admin and debug conventions as part of enumeration. What is the auditor trying to discover through that probing?

- **A.** The rate-limit thresholds, since admin endpoints are throttled differently and probing them measures the limits precisely
- **B.** The framework version in use, since admin route conventions differ by framework and reveal which one the app was built on
- **C.** The caching configuration, since debug endpoints expose cache headers that reveal how aggressively responses are stored
- **D.** Undocumented routes that ship in an app but appear nowhere in the docs, then testing each one for missing authentication  ✅

> **Answer:** D

### Q20. An auditor reads through frontend code asking one question at each protection: is this also enforced server-side? What recurring vibebuilt instance does this catch?

- **A.** Slow-rendering components, since a protection that delays the interface indicates client-side logic that belongs on the server
- **B.** Untranslated strings, since a protection missing its localization reveals which sessions generated which parts of the frontend
- **C.** Hidden UI elements that still work when their endpoints are called directly since the gate was only ever drawn in the browser  ✅
- **D.** Deprecated libraries, since a client-side protection built on an old package signals training-data leakage in that component

> **Answer:** C

### Q21. The method lists default credentials on admin tooling as a configuration finding. Why is this routinely rated RED when found?

- **A.** Default credentials slow authentication, since the tooling rechecks them against a remote list on every single admin login attempt
- **B.** Default credentials break the audit log, since actions taken under a shared default account cannot be attributed to any real person
- **C.** Default credentials expire quickly, so the tooling locks out legitimate admins while leaving a brief window open to attackers only
- **D.** Default credentials are publicly known so anyone who reaches the admin tool can log in with them and take full control immediately  ✅

> **Answer:** D

### Q22. An auditor walks the application as an adversary rather than a user. At each input, what is the specific question the method tells them to ask?

- **A.** What happens if I send something unexpected, since inputs that assume well-behaved data are where injection and manipulation begin  ✅
- **B.** How fast does this input validate, since slow validation reveals the server is doing expensive work that can be abused for cost
- **C.** Which session generated this input handler, since knowing the session narrows down where replicated flaws are most likely to cluster
- **D.** Does this input appear in the documentation, since undocumented inputs are the only ones worth testing during a manual pass

> **Answer:** A

### Q23. An auditor tests one auth boundary, finds it solid, and is inclined to trust the rest. Why does the method reject that inference specifically in the manual pass?

- **A.** Boundaries are graded collectively, so one solid boundary raises the grade of every other boundary in the same layer automatically
- **B.** Manual testing is unreliable, so any single boundary result must be confirmed by an automated scanner before it can be trusted at all
- **C.** Replication means the other boundaries were likely built the same way so one tested boundary says little about its untested siblings  ✅
- **D.** Boundaries change between sessions, so a boundary that is solid today will likely differ by the time the report reaches the client

> **Answer:** C

### Q24. An auditor submits an extra hidden field, role set to admin, in a profile-update request that the form never displayed. What business logic weakness is this probing for?

- **A.** Whether the form validates on blur, since fields validated only on submit let an attacker skip the client-side checks entirely
- **B.** Whether the server rejects unknown fields, since an endpoint that silently accepts unexpected parameters may bind them to real records  ✅
- **C.** Whether the request is cached, since a cached profile update could serve one user's elevated role to a different user later on
- **D.** Whether the endpoint is rate limited, since an unthrottled update lets an attacker brute-force field names until one is accepted

> **Answer:** B

### Q25. Looking across everything in this module, what is the governing principle for the manual review pass?

- **A.** Think like an attacker and verify server-side enforcement, because the worst findings live where the builder never considered an adversary  ✅
- **B.** Trust the automated pass to have found the severe issues, since manual review exists mainly to confirm what the scanners flagged
- **C.** Accept client-side controls when they are consistent, since a uniformly applied frontend gate is evidence of deliberate design
- **D.** Review only the documented surface thoroughly, since undocumented routes fall outside the scope a manual pass should commit to

> **Answer:** A


---
_Take it in the browser: https://the-faction.mn.co/posts/106568629_
