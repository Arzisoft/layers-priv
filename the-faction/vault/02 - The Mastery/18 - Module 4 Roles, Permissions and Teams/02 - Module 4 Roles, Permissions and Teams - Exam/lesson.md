---
course: "The Mastery"
module: "Module 4: Roles, Permissions and Teams"
lesson: "Module 4: Roles, Permissions and Teams — Exam"
type: "course_quiz"
post_id: 105098748
space_id: 24191170
source: "https://the-faction.mn.co/posts/105098748"
updated: "2026-08-10T20:44:09Z"
---

# Module 4: Roles, Permissions and Teams — Exam

> Exam for **Module 4: Roles, Permissions and Teams** (The Mastery) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. What question does authorization answer on every request?

- **A.** Whether this specific identity may do this specific thing to this specific resource  ✅
- **B.** Whether the request arrived over an encrypted connection from a supported browser
- **C.** Whether the user's subscription payment cleared within the current billing period
- **D.** Whether the server has capacity to process the request within its response target

> **Answer:** A

### Q2. What is the practical difference between a role and a permission?

- **A.** Roles are stored in the database while permissions live only in the application code
- **B.** Permissions expire with the session while roles persist for the life of the account
- **C.** A permission is one allowed action; a role is a named bundle of permissions assigned  ✅
- **D.** They are interchangeable terms, kept distinct only by older frameworks' naming habits

> **Answer:** C

### Q3. Where must permission checks actually run to count as security?

- **A.** In the mobile app binary, where compiled code protects the logic from casual inspection
- **B.** On the server, on every protected action, since everything sent to clients can be altered  ✅
- **C.** In the frontend router, which decides which screens each role is able to navigate to
- **D.** At the load balancer, the single choke point through which every request must pass

> **Answer:** B

### Q4. Your AI hides the delete button from non-admins and calls the feature secure. What is wrong?

- **A.** Hidden buttons confuse screen readers, creating an accessibility gap larger than the risk
- **B.** Buttons should be disabled rather than hidden, the pattern users actually understand
- **C.** Nothing is wrong; if the interface exposes no path, the action cannot be performed
- **D.** The API behind the button still accepts the request; hiding the trigger secures nothing  ✅

> **Answer:** D

### Q5. What should a brand-new user's default access look like?

- **A.** The minimum needed to start: default deny everywhere, with access granted deliberately  ✅
- **B.** Full access for the first week, so evaluation isn't blocked, then trimmed afterward
- **C.** A mirror of the most recently created account, keeping team permissions consistent
- **D.** Read access to everything and write access to nothing, the universal safe baseline

> **Answer:** A

### Q6. What does a team or workspace model add to a multi-user app?

- **A.** A billing discount tier, since providers price grouped accounts well below individual ones
- **B.** A boundary that owns members, data, and roles, so collaboration stays inside its walls  ✅
- **C.** A shared password among members, simplifying access without per-person credentials
- **D.** A visual grouping in the interface, cosmetic structure with no security significance

> **Answer:** B

### Q7. Owner, admin, member: what actually separates the owner role?

- **A.** Owners get priority support and early features; the roles are otherwise identical inside
- **B.** Owners are billed personally, while admin and member charges route to the company card on file
- **C.** Control over the workspace's existence and riskiest actions: billing, deletion, transfer  ✅
- **D.** Nothing enforced; the label exists so teams know who convened the workspace originally

> **Answer:** C

### Q8. A user is allowed to edit documents. What must the check on "edit document 4571" still confirm?

- **A.** That the document loads within the latency budget before any edit gets accepted
- **B.** That the edit arrives during business hours, when document changes are legitimate
- **C.** That the document is under its revision limit, since histories cap at fifty entries
- **D.** That this user may edit that particular document, not just documents in general  ✅

> **Answer:** D

### Q9. Your AI checks "is admin" in the frontend only. What is the correct direction?

- **A.** Enforce the check on the server for every admin action; the client copy is convenience  ✅
- **B.** Add the same check to a second frontend component, so a single bypass is insufficient
- **C.** Encrypt the admin flag in the browser, converting the client check into real security
- **D.** Accept it for now; frontend checks hold until the app is big enough to attract attackers

> **Answer:** A

### Q10. What makes a team invitation flow safe?

- **A.** Sending invitations only to addresses already registered, closing the door on strangers
- **B.** Printing invitation codes for physical delivery, which keeps the tokens off the network entirely
- **C.** Expiring single-use tokens tied to the invited address, with the role set by the inviter  ✅
- **D.** Letting any member forward their own login link, since trust inside a team is transitive

> **Answer:** C

### Q11. A member is removed from a team. What must the system actually revoke?

- **A.** Their marketing emails and notifications, the touchpoints that define membership
- **B.** Only their next login, since active sessions are contractually allowed to complete
- **C.** Their profile photo and display name, scrubbing the departed identity from view
- **D.** Live sessions, API keys, shares, and tokens they hold, not just the roster entry  ✅

> **Answer:** D

### Q12. Why log every permission and role change with who, whom, and when?

- **A.** Change logs are billable events in most platforms, so complete logs maximize revenue
- **B.** When access is abused or disputed, the grant trail is the evidence you will actually need  ✅
- **C.** Logs slow permission changes slightly, discouraging admins from casual role churn
- **D.** Storage vendors require audit tables before enabling their compliance dashboard tier

> **Answer:** B

### Q13. The team asks for a new role for every job title, fifteen roles and counting. What is the discipline?

- **A.** Keep roles few and meaningful; model differences as permissions rather than new roles  ✅
- **B.** Grant the fifteen roles, since organizational charts are the truest security model
- **C.** Cap roles at ten by policy, merging the two least used whenever an eleventh role appears
- **D.** Replace all roles with one shared admin level, ending the taxonomy debate entirely

> **Answer:** A

### Q14. Your own staff needs to access customer workspaces for support. How is this modeled safely?

- **A.** A shared staff account inside every workspace, present from creation for convenience
- **B.** A separate, logged, time-limited internal access path, never membership in customer teams  ✅
- **C.** Staff use the customer's owner credentials, borrowed through the support ticket thread
- **D.** No access ever, since support can be delivered entirely through screenshots users send

> **Answer:** B

### Q15. In a multi-tenant app, what is the catastrophic authorization failure?

- **A.** A role name colliding between two teams, confusing the interface labels temporarily
- **B.** A permission check running twice, wasting compute on requests that were already cleared
- **C.** An admin seeing a feature a day before its announcement, spoiling a marketing launch
- **D.** Data crossing tenants: one company's user reading another company's records at all  ✅

> **Answer:** D

### Q16. How do you actually test an authorization system?

- **A.** Log in as an admin and confirm every screen renders with all of its buttons visible
- **B.** Read the AI's code and confirm the role names match the ones in the specification
- **C.** Attempt forbidden actions as each role, including direct API calls, and confirm denial  ✅
- **D.** Measure response times per role, since authorization failures appear first as added latency

> **Answer:** C

### Q17. Permission logic is scattered across forty route handlers. Why direct consolidation?

- **A.** Scattered checks drift and develop gaps; one policy layer means one place to reason  ✅
- **B.** Consolidated checks compile smaller, trimming the deploy artifact by useful margins
- **C.** Route-level checks are deprecated in modern frameworks and will stop passing builds
- **D.** Auditors bill by file count, so consolidation reduces the direct cost of certification

> **Answer:** A

### Q18. The last owner tries to leave the team. What must the flow force?

- **A.** Automatic deletion of the workspace, since ownerless teams cannot legally hold data
- **B.** The departure to complete silently, with ownership defaulting to the oldest member
- **C.** An explicit transfer of ownership first, so the workspace never exists uncontrolled  ✅
- **D.** A thirty-day cooling period during which the departing owner may return and cancel the exit

> **Answer:** C

### Q19. What does "default deny" mean as an authorization posture?

- **A.** New users are rejected at signup until an admin manually approves each account by hand
- **B.** Anything not explicitly granted is refused, so forgotten configuration fails closed  ✅
- **C.** All requests are denied once per session to verify the error path renders correctly
- **D.** The app denies service during deploys, guaranteeing no request meets mixed code

> **Answer:** B

### Q20. Your app offers "anyone with the link" sharing. What keeps this from becoming a leak?

- **A.** A visual watermark on shared pages, discouraging recipients from spreading them on
- **B.** Limiting links to ten opens, after which the content re-locks until manually renewed
- **C.** Registering every recipient silently, converting anonymous viewers into tracked users
- **D.** Scoped, expiring, revocable link tokens, plus awareness that links forward to anyone  ✅

> **Answer:** D

### Q21. An admin is demoted to member, but their open session still carries admin claims. What did the design miss?

- **A.** Permission changes must take effect on the next request, not when the session refreshes  ✅
- **B.** Demotion should be scheduled for midnight, when session refresh cycles naturally align anyway
- **C.** Sessions and roles are separate systems, and syncing them is a known impossibility
- **D.** The demotion email, which is what actually informs the session layer of the change

> **Answer:** A

### Q22. Seats are billed per member. What must the roles system coordinate with billing?

- **A.** Nothing; billing and access are separate concerns joined only in the monthly invoice itself
- **B.** Adds, removals, and role changes that affect seat counts must reflect in billing truly  ✅
- **C.** Role names must match invoice line items exactly, or accounting reconciliation fails
- **D.** Billing must approve each new member before the invitation email is even sent out

> **Answer:** B

### Q23. A request arrives at your API with a valid session. What is the full check before acting?

- **A.** Valid session is the full check; authentication and authorization are the same gate
- **B.** Session validity plus request size, the two properties attackers reliably get wrong
- **C.** Who they are, what they're asking, and whether that identity may do it to that resource  ✅
- **D.** Session validity plus geographic origin, since location is the strongest single fraud signal

> **Answer:** C

### Q24. Support wants an "impersonate user" feature for debugging. What are the mandatory guardrails?

- **A.** None; impersonation is read-only by nature and therefore carries no meaningful risk
- **B.** A separate paid tier for impersonated accounts, converting a risk into extra revenue instead
- **C.** Restricting impersonation to weekends, when customers are least likely to be active
- **D.** Explicit logging, visible indication, time limits, and no dangerous actions while inside  ✅

> **Answer:** D

### Q25. Which principle should govern every permissions decision you direct?

- **A.** Default deny, check on the server, scope to the resource, leave a trail: access is granted, never assumed  ✅
- **B.** Trust the team: internal users are allies, and friction between allies is pure wasted effort
- **C.** Roles mirror titles: the org chart is the security model, updated whenever HR updates it
- **D.** Check once at login: a verified identity at the door secures everything that sits behind it

> **Answer:** A


---
_Take it in the browser: https://the-faction.mn.co/posts/105098748_
