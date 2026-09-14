---
course: "The Vault"
module: "Module 2: The 13-Layer Audit Framework"
lesson: "Module 2: The 13-Layer Audit Framework — Exam"
type: "course_quiz"
post_id: 106568627
space_id: 24302166
source: "https://the-faction.mn.co/posts/106568627"
updated: "2026-08-28T16:26:08Z"
---

# Module 2: The 13-Layer Audit Framework — Exam

> Exam for **Module 2: The 13-Layer Audit Framework** (The Vault) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. An auditor is about to begin a 13-layer walk. What is the defining purpose of following the same layer stack in the same order on every engagement?

- **A.** It satisfies a compliance mandate, because certification bodies require the thirteen layers in a fixed sequence
- **B.** It shortens the audit, because a fixed order lets the auditor skip layers that were clean on prior engagements
- **C.** It guarantees coverage, so nothing is skipped because it was boring, unfamiliar, or invisible from the code alone  ✅
- **D.** It impresses the client, because a rigid framework signals thoroughness even when several layers go unexamined

> **Answer:** C

### Q2. A codebase has no caching layer at all, and the founder assumed one existed. How does the framework say the auditor should handle that layer?

- **A.** Skip it silently, since a layer that does not exist cannot contain any findings worth documenting in the report
- **B.** Grade it explicitly, because a missing layer the business assumed it had is itself a finding worth surfacing  ✅
- **C.** Defer it to the next audit, since absent layers are out of scope until the business decides to build them out
- **D.** Merge it into the hosting layer, since caching and hosting concerns are functionally identical for a small app

> **Answer:** B

### Q3. An auditor is walking the Database layer of a multi-tenant application. Which concern is most central to this layer?

- **A.** Whether the database uses that newest engine version, since older engines are the primary source of tenant leakage
- **B.** Whether row-level security or equivalent tenant isolation prevents one tenant from reading another's data records  ✅
- **C.** Whether database queries are commented clearly, since undocumented queries slow the remediation sprint later on
- **D.** Whether the database is hosted in the same region as the app, since cross-region latency degrades user experience

> **Answer:** B

### Q4. When auditing the APIs layer, an auditor insists on checking authentication on every endpoint, not just the documented ones. What risk does this address?

- **A.** Documented endpoints change often, so re-verifying only the documented set keeps the audit report current over time
- **B.** Rate limits apply only to documented endpoints, so undocumented ones silently bypass the abuse controls in place
- **C.** Undocumented endpoints load faster, so attackers prefer them, making their performance the real audit concern here
- **D.** Undocumented endpoints often ship with no auth, and the real API surface is always larger than the documented one  ✅

> **Answer:** D

### Q5. The four user-facing layers, Frontend, APIs, Database, and Auth, carry most Critical findings in vibebuilt apps. Why do they concentrate the worst issues?

- **A.** They are built last in most projects, so they inherit the accumulated technical debt of every layer beneath them
- **B.** They are the only layers automated scanners can examine, so findings there are simply detected more often than elsewhere
- **C.** They are where AI builds fastest and replicates hardest, so flawed patterns propagate widely across those layers  ✅
- **D.** They are the layers clients care about most, so auditors look there hardest and naturally record more findings

> **Answer:** C

### Q6. An auditor reviewing the CI/CD layer treats template-inherited configuration with particular suspicion. What is the reasoning the framework gives?

- **A.** The posture was chosen by whoever wrote the template, not by anyone actually defending this particular business  ✅
- **B.** Templates are always outdated, so any configuration inherited from one is guaranteed to contain known vulnerabilities
- **C.** Templates cannot be scanned, so inherited configuration must always be reviewed entirely by hand at great expense
- **D.** Template configuration overrides application code, so it silently disables every protection the developers wrote

> **Answer:** A

### Q7. An auditor grades the Caching layer and focuses on more than cache poisoning. What cache-specific data exposure does the framework single out?

- **A.** Cached responses that leak one user's data to another or serve stale authorization from the previous session state  ✅
- **B.** Cache size limits, since an undersized cache evicts entries too quickly and forces expensive repeated recomputation
- **C.** Cache misses that slow the application, since degraded performance under load is the main caching-layer risk to flag
- **D.** Cache warming schedules, since a cold cache after deployment briefly exposes the origin server to direct traffic

> **Answer:** A

### Q8. On the Rate Limiting layer, why does the framework treat an unthrottled endpoint attached to a paid API as a specific category of risk?

- **A.** Unthrottled endpoints respond slower, so paid API calls time out and customers are billed for failed requests anyway
- **B.** An unthrottled endpoint attached to a paid API is a billing attack surface, where abuse directly runs up real cost  ✅
- **C.** Unthrottled endpoints violate the API provider's terms, so the account is suspended before any abuse even occurs
- **D.** Unthrottled endpoints skew analytics, so the business cannot accurately measure genuine demand for the paid feature

> **Answer:** B

### Q9. An auditor grades the Availability layer GREEN after confirming automated backups run nightly. What did the framework warn they must still check before that grade holds?

- **A.** Whether backups run more than nightly, because a full day of data loss is unacceptable for any modern application
- **B.** Whether the backups are encrypted, because unencrypted nightly backups are the single most common breach vector today
- **C.** Whether a restore has actually been tested, because an unrestorable backup is a company-ending event with no attacker  ✅
- **D.** Whether the backups are stored off-site, because same-region backups are the only real availability concern that matters

> **Answer:** C

### Q10. How does the framework define the difference between a YELLOW and a RED grade on a layer?

- **A.** YELLOW means the auditor is uncertain and RED means confirmed, so the grades track auditor confidence rather than risk
- **B.** YELLOW means fewer than five findings and RED means five or more, so the grades are a simple count of issues per layer
- **C.** YELLOW means the layer is deprecated and RED means it is missing, so the grades describe architectural completeness
- **D.** YELLOW means gaps needing scheduled remediation; RED means exploitable now or one failure from disaster, fix immediately  ✅

> **Answer:** D

### Q11. The framework calls for RED thresholds to differ between a solo founder's side project and a healthcare platform. What principle does this reflect?

- **A.** Healthcare platforms are always graded one level worse than other apps, as a fixed regulatory penalty on the scorecard
- **B.** Grades are calibrated to the business, so the same gap earns a different grade based on stage and data sensitivity  ✅
- **C.** Solo projects skip the RED grade entirely, since a single-person business has no attack surface worth escalating over
- **D.** Grades depend on codebase size, so larger healthcare systems automatically accumulate more RED layers than small ones

> **Answer:** B

### Q12. An auditor examining the Security layer treats a CORS policy set to a wildcard as a finding. What does a wildcard CORS policy actually permit?

- **A.** It disables HTTPS on cross-origin requests, so any data sent to another origin travels unencrypted over the network
- **B.** It caches responses across origins, so one site's authenticated response can be served to a completely different site
- **C.** It allows any origin to make cross-origin requests, rather than restricting access to a real, intended allowlist  ✅
- **D.** It removes rate limits on cross-origin calls, so external origins can flood the API without any throttling applied

> **Answer:** C

### Q13. On the Error Tracking layer, an auditor finds stack traces with database queries reaching end users. Why does the framework classify this as a real security finding?

- **A.** Exposed traces and queries hand an attacker a map of the system's internals, PII, and structure they should never see  ✅
- **B.** Stack traces overwrite the error log, so the operations team loses the diagnostic history it needs to resolve incidents
- **C.** Stack traces slow the error page, so users abandon the app when an error exposes a lengthy diagnostic trace to them
- **D.** Stack traces confuse non-technical users, so the finding is really about user experience rather than security posture

> **Answer:** A

### Q14. An auditor reaches the Cloud layer of an app deployed on a major provider. Which set of concerns belongs to this layer?

- **A.** Security headers, HTTPS enforcement, and CORS configuration on the application's public-facing responses to the browser
- **B.** Session persistence and health-check behavior when one instance fails behind the traffic distribution mechanism
- **C.** IAM over-permissioning, public storage buckets, and network exposure across the provider's account resources and services  ✅
- **D.** Password storage, session handling, and privilege escalation paths through the application's authentication flows

> **Answer:** C

### Q15. The framework runs the audit walk from the user-facing layers down toward the operational ones. What logic drives that ordering?

- **A.** It runs alphabetically by layer name, so any auditor can reproduce the exact same sequence without a reference sheet
- **B.** It runs from cheapest to most expensive to audit, so the engagement can stop early once the budget is fully consumed
- **C.** It runs from most to least likely to contain findings, so the report's worst issues always appear in its opening pages
- **D.** It runs from what the user touches down through what the business depends on, moving surface to foundation in order  ✅

> **Answer:** D

### Q16. An auditor cannot verify a layer because they were not granted the cloud account access it requires. How does the framework say that layer should appear on the scorecard?

- **A.** Graded GREEN, since the absence of any visible finding is reasonable grounds to treat the layer as passing for now
- **B.** Graded RED, since any layer the auditor cannot inspect should be assumed exploitable until proven otherwise entirely
- **C.** Marked UNVERIFIED with that access that would be needed, because grading on absence of evidence is never acceptable  ✅
- **D.** Omitted from the scorecard, since a layer without evidence cannot be represented fairly among the graded ones shown

> **Answer:** C

### Q17. On the Hosting layer, an auditor probes for admin panels reachable from the public internet. Why is this a hosting-layer priority?

- **A.** An internet-reachable admin panel is a direct entry point, and default or exposed admin access is a recurring hosting flaw  ✅
- **B.** Public admin panels break the CORS policy, since admin origins are rarely included in the application's allowlist config
- **C.** Public admin panels violate backup schedules, since administrative traffic interferes with the nightly snapshot window
- **D.** Public admin panels slow the host, since bots that discover them generate load that degrades legitimate traffic speeds

> **Answer:** A

### Q18. The framework describes the RED/YELLOW/GREEN scorecard as both a summary and a communication tool. What makes it effective for a non-technical founder?

- **A.** It hides the failing layers behind a single overall score, so the founder is not alarmed by individual RED results
- **B.** It lists every finding in full technical detail, so the founder can personally verify each grade against the raw code
- **C.** It ranks the founder's app against competitors, so they understand their security posture relative to the whole market
- **D.** It compresses the entire audit into just thirteen grades the founder can grasp in seconds and see where the fire is  ✅

> **Answer:** D

### Q19. An auditor is tempted to skip the Load Balancing layer because the app currently runs on a single small instance. What does the framework advise?

- **A.** Grade the layer rather than skip it, because session persistence and failover behavior still warrant an explicit judgment  ✅
- **B.** Merge it into availability, since a single-instance app treats load balancing and availability as one identical concern
- **C.** Skip it, since load balancing concerns are entirely irrelevant until an application scales to multiple running instances
- **D.** Defer it to a specialist, since load balancing sits outside the thirteen layers a standard code audit is scoped to cover

> **Answer:** A

### Q20. An auditor is deciding between RED and YELLOW for an Auth-layer finding: a privilege escalation path that is exploitable right now. Which grade applies and why?

- **A.** YELLOW, because auth findings are scheduled for the next remediation cycle rather than treated as immediate emergencies
- **B.** GREEN, because the presence of an auth layer at all is sufficient to pass, with escalation paths noted only as observations
- **C.** YELLOW, because privilege escalation requires an authenticated account, which counts as a specific precondition that lowers it
- **D.** RED, because the path is exploitable now, which is the defining threshold for a RED grade that must be fixed immediately  ✅

> **Answer:** D

### Q21. The framework insists every layer grade trace to logged findings rather than the auditor's overall impression. What failure does this rule prevent?

- **A.** It prevents the report from becoming too long, since evidence-linked grades are more concise than narrative descriptions
- **B.** It prevents grading a layer GREEN after looking at nothing, since a grade with no evidence behind it is not a real grade  ✅
- **C.** It prevents disagreement between auditors, since two people reviewing identical evidence always reach the same grade exactly
- **D.** It prevents the client from seeing raw findings, since only summarized grades belong in a report meant for a founder

> **Answer:** B

### Q22. Why does the framework warn that one dramatic RED layer can cause auditors to under-weight the quiet YELLOW layers around it?

- **A.** YELLOW layers are always false positives, so an experienced auditor learns to disregard them once a RED is confirmed nearby
- **B.** The YELLOWs become next quarter's REDs, so letting one dramatic finding crowd them out stores up the future emergencies  ✅
- **C.** RED layers consume the entire remediation budget, so the YELLOW layers are deferred indefinitely as a matter of economics
- **D.** YELLOW layers cannot be fixed until the RED is resolved, so documenting them early wastes effort the client will not use

> **Answer:** B

### Q23. An auditor is defining GREEN for a given layer. What does GREEN actually assert in this framework?

- **A.** No material findings, and the layer meets that security baseline appropriate for this business's current stage and risk  ✅
- **B.** The layer is perfectly secure against every possible attack, present and future, with no residual risk of any kind remaining
- **C.** The layer was not examined, so GREEN is the neutral default assigned to any layer the audit did not have time to reach
- **D.** The layer passed automated scanning, regardless of whether the manual review found business logic flaws within the same layer

> **Answer:** A

### Q24. An auditor on the Database layer checks connection security in addition to isolation and injection. What connection-level exposure is the framework pointing at?

- **A.** Connection pool size, since an undersized pool drops requests under load and creates an availability problem downstream
- **B.** Query comment density, since undocumented connection logic slows the remediation team during a later fixing sprint
- **C.** Connection latency, since a slow database link degrades user experience more than any other database-layer concern
- **D.** Credentials and transport for the database link, since exposed connection strings or unencrypted links open the data directly  ✅

> **Answer:** D

### Q25. Looking across everything in this module, what is the governing principle of the 13-layer audit framework?

- **A.** Systematic coverage with evidence-backed, business-calibrated grades, so that whole system is visible and nothing is skipped  ✅
- **B.** Weight the scorecard toward the layers the client already understands, because comprehension matters more than completeness
- **C.** Grade only the layers most likely to fail, because a focused audit of the risky layers delivers more value than a full walk
- **D.** Prioritize speed over completeness, because a fast partial audit that ships beats a thorough one that arrives too late to act on

> **Answer:** A


---
_Take it in the browser: https://the-faction.mn.co/posts/106568627_
