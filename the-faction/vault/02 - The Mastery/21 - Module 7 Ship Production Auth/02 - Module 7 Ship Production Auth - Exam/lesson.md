---
course: "The Mastery"
module: "Module 7: Ship: Production Auth"
lesson: "Module 7: Ship: Production Auth — Exam"
type: "course_quiz"
post_id: 105099135
space_id: 24191170
source: "https://the-faction.mn.co/posts/105099135"
updated: "2026-08-10T20:44:09Z"
---

# Module 7: Ship: Production Auth — Exam

> Exam for **Module 7: Ship: Production Auth** (The Mastery) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. What belongs on the pre-launch checklist for your auth system specifically?

- **A.** The login page's conversion copy, A/B tested against at least two alternative headlines
- **B.** A list of every framework the AI used, filed for the technology audit later on
- **C.** Rate limits live, secrets out of code, flows tested including edges, and monitoring on  ✅
- **D.** A screenshot archive of every auth screen, the baseline for future design regression

> **Answer:** C

### Q2. How should auth-related secrets be handled at and after launch?

- **A.** Frozen permanently, since rotation is what causes most self-inflicted auth outages
- **B.** Emailed to the founding team, guaranteeing recovery access outside the infrastructure
- **C.** Printed and stored physically, the one medium no network attacker can ever reach
- **D.** In protected configuration, rotated on schedule and after departures or incidents  ✅

> **Answer:** D

### Q3. What should auth monitoring actually watch after launch?

- **A.** Login page load speed, the metric that correlates most tightly with user satisfaction
- **B.** Failed logins, reset volume, signup anomalies, and lockouts, against known baselines  ✅
- **C.** The color contrast of error states, since accessibility drift is the silent auth killer
- **D.** Total session count only, since one number is what an on-call human can actually track

> **Answer:** B

### Q4. Where should rate limiting sit for auth endpoints in production?

- **A.** At the edge, in front of the application, so floods are shed before they consume resources  ✅
- **B.** In the database, the layer that ultimately pays the cost of every excess request
- **C.** In the mobile app build, where limits ship signed and cannot be altered by users
- **D.** Nowhere during launch month, since limits would throttle the growth you're paying for

> **Answer:** A

### Q5. A critical vulnerability is announced in the auth library your app uses. What does readiness look like?

- **A.** Waiting for the next quarterly maintenance window, since panic patching breaks more
- **B.** Switching libraries entirely, since a vulnerability reveals the whole dependency as weak
- **C.** Knowing your versions, having a tested update path, and patching within days, not months  ✅
- **D.** Disabling logins until the vendor certifies the fix, the only fully safe posture available

> **Answer:** C

### Q6. What should happen to test accounts, magic backdoors, and debug flags before launch?

- **A.** Removed entirely and verified gone, since forgotten conveniences become entry points  ✅
- **B.** Renamed with production prefixes so their purpose is legible in future audits
- **C.** Password-protected as a group, converting the backdoors into an emergency access tier
- **D.** Documented in the wiki and left alone, since removal risks breaking the test suites

> **Answer:** A

### Q7. Credential stuffing hits your login endpoint on launch week. What determines whether it becomes an incident?

- **A.** The attacker's location, since domestic traffic is filterable and foreign traffic is not
- **B.** Preparation: rate limits, breach-password checks, monitoring, and a response plan ready  ✅
- **C.** Your hosting tier, since enterprise plans absorb attack traffic as a billed service
- **D.** Media attention, since stuffing only matters when a journalist notices the traffic

> **Answer:** B

### Q8. You confirm some user credentials were exposed. What is the professional first response?

- **A.** Silence until the legal team finishes its review, since early statements create legal liability
- **B.** A press release emphasizing that most accounts were untouched by the exposure event
- **C.** A discount offer to affected users, converting the incident into a retention moment
- **D.** Force resets on affected accounts, invalidate sessions, notify honestly, investigate scope  ✅

> **Answer:** D

### Q9. Where do changes to production auth flows prove themselves first?

- **A.** On production during low traffic, the only environment whose behavior actually counts
- **B.** In code review alone, since reading auth changes reveals everything running them would
- **C.** On staging with production-like data and the full flow exercised, edges included  ✅
- **D.** In the AI's own summary, since agents report their confidence levels with each change

> **Answer:** C

### Q10. Is a managed auth provider acceptable for production, or must serious apps self-build?

- **A.** Self-build always; renting the front door means the landlord owns your users forever
- **B.** Managed is often stronger: their security team and uptime likely beat what you'd build  ✅
- **C.** Managed only until ten thousand users, the scale where providers contractually eject apps
- **D.** Neither; auth belongs at the operating system layer, outside application decisions

> **Answer:** B

### Q11. Who should hold access to the production auth dashboard and its user management powers?

- **A.** The minimal set with operational need, reviewed as roles change, with actions logged  ✅
- **B.** The entire engineering team, since auth touches everything and everyone debugs it
- **C.** Only the AI agents, since automated hands make fewer mistakes than people with user records
- **D.** The founder alone, since concentration of access is what accountability really means

> **Answer:** A

### Q12. What does basic compliance ask of your auth system, wherever you operate?

- **A.** A government license for the login system, renewed annually with a security exam
- **B.** Publishing the hashing algorithm publicly, the transparency rule most regions share
- **C.** A physical server for credentials in each country where the app has active users
- **D.** Protecting credentials properly, honest breach disclosure, and honoring deletion requests  ✅

> **Answer:** D

### Q13. Sessions live in one store and the app now runs on several servers. What must be true?

- **A.** Every server reads the same session truth, so users aren't logged out by landing elsewhere  ✅
- **B.** Each server keeps its own sessions, with users pinned to one machine for life
- **C.** Sessions are disabled at multi-server scale, replaced by per-request password entry
- **D.** The session store is duplicated nightly, accepting a day of drift between the copies

> **Answer:** A

### Q14. What must auth logs contain, and what must they never contain?

- **A.** Passwords in hashed form, since hashes are safe to store in any medium
- **B.** Events and metadata only, never passwords, tokens, or codes, because logs leak  ✅
- **C.** Full request bodies for replay debugging, scrubbed quarterly by an automated job
- **D.** Nothing at all, since logging auth events creates a target for exfiltration

> **Answer:** B

### Q15. How should a significant auth change, like a new session model, reach production?

- **A.** Behind a flag, with rollback ready and both paths monitored as traffic shifts gradually  ✅
- **B.** In one deploy during a scheduled maintenance window, the cleanest possible single cutover
- **C.** Through the AI's automatic deployment pipeline, which tests and ships in one step
- **D.** By running both models permanently, letting users choose which one they prefer

> **Answer:** A

### Q16. A locked-out user contacts support, begging for a bypass 'just this once.' What does production-grade process do?

- **A.** Follow verification procedures exactly, because urgency is the attacker's main tool  ✅
- **B.** Grant the bypass but log it, creating accountability for the exception made
- **C.** Escalate to engineering for a direct database unlock, the path with fewest witnesses
- **D.** Reset the account entirely and re-enroll the user, the cleanest fresh start available

> **Answer:** A

### Q17. An enterprise prospect asks whether your auth has been security tested. What is the strong answer?

- **A.** A list of the frameworks and libraries used, since known tools imply tested code
- **B.** A verbal assurance from your engineering lead, since that is the voice enterprise buyers trust
- **C.** An actual review of your auth surface: findings fixed, report available on request  ✅
- **D.** A demo of the login flow, since a working demo is evidence that auth is functional

> **Answer:** C

### Q18. What keeps production auth healthy over months and years?

- **A.** Periodic reviews: access reviews, dependency updates, log audits, and re-testing flows  ✅
- **B.** Avoiding all changes after launch, since the most stable auth is auth that nobody ever touches
- **C.** Annual penetration tests alone, the industry-standard cadence for auth verification
- **D.** Automated AI scans that replace human review with faster, broader pattern matching

> **Answer:** A

### Q19. A provider outage takes down the managed auth service your app uses. What determined whether this is a crisis?

- **A.** The provider's SLA, since contractual guarantees are what keep your users logged in
- **B.** Your database backups, since restoring from backup is the standard auth failover
- **C.** Earlier thinking: knowing your blast radius, what degrades versus breaks, and your user message  ✅
- **D.** Nothing; managed auth outages are the provider's problem and not yours to plan for

> **Answer:** C

### Q20. Your AI reports that the auth system is 'complete and secure.' What is the professional response?

- **A.** Ship it, since the AI has tested more scenarios than a human reviewer ever could
- **B.** Request a second AI opinion to cross-check the first agent's confidence level
- **C.** Verify with evidence: run the flows, attempt the abuses, read the checks yourself  ✅
- **D.** Ask the AI to rate its own confidence, then ship whenever it clears a set threshold

> **Answer:** C

### Q21. What is the governing principle for production auth over the life of the app?

- **A.** Move fast and fix forward, since speed matters more than caution in competitive markets
- **B.** Automate everything, since human involvement in auth operations introduces human error
- **C.** Trust but verify quarterly, the cadence that balances vigilance with operational cost
- **D.** The front door never sleeps: proven parts, tested edges, watched always, changed with care  ✅

> **Answer:** D

### Q22. How does auth connect to the business beyond security?

- **A.** It does not; auth is a pure security function with no business metrics attached
- **B.** Auth connects through pricing alone, since login features determine which tier users buy
- **C.** Auth matters only at enterprise scale, where compliance requirements create buying signals
- **D.** Every auth decision is also a funnel decision, and friction data shows where signups leak  ✅

> **Answer:** D

### Q23. What does 'boring' mean as the goal state for production auth six months after launch?

- **A.** Nobody on the team remembers the auth system exists or could describe its architecture
- **B.** Monitored, patched, rehearsed, and changed only through process, with no surprises  ✅
- **C.** No logins have failed in six months, proving the system is frictionless and invisible
- **D.** The auth codebase has not been touched in six months, proving its stability conclusively

> **Answer:** B

### Q24. When real key rotation happens in production, what makes it work without an outage?

- **A.** Rotating only during zero-traffic windows, the safest time to swap any credential
- **B.** Delegating rotation entirely to the AI, which coordinates the swap across all services
- **C.** Notifying all users of the rotation schedule so they can re-authenticate on the new key
- **D.** Overlap windows where both keys work, dependents updated, old keys verified dead after  ✅

> **Answer:** D

### Q25. What is the correct log rule when auth events must be recorded for future investigations?

- **A.** Log everything including tokens, since investigations need the full credential context
- **B.** Log events and metadata with timestamps and account IDs, never credentials or secrets  ✅
- **C.** Log only failures, since successful logins do not contribute to incident investigation
- **D.** Log to a public audit chain for transparency, the strongest form of accountability

> **Answer:** B


---
_Take it in the browser: https://the-faction.mn.co/posts/105099135_
