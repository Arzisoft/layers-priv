---
course: "The Mastery"
module: "Module 4 — Access Control & Permissions"
lesson: "Module 04: Users, Teams & RBAC — Exam"
type: "course_quiz"
post_id: 103821123
space_id: 24191170
source: "https://the-faction.mn.co/posts/103821123"
updated: "2026-08-20T23:41:29Z"
---

# Module 04: Users, Teams & RBAC — Exam

> Exam for **Module 4 — Access Control & Permissions** (The Mastery) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. Your AI built a signup flow with individual user accounts. Your fifth customer wants 8 team members. There is no concept of organizations — just users with subscriptions. What is the gap?

- **A.** Users don't need an organization layer — just share login credentials across the team
- **B.** An org layer between users and subscriptions that supports multiple users per account  ✅
- **C.** Create eight separate subscriptions with individual billing for each team member
- **D.** Add a team_name column to the user table and filter all queries by that field

> **Answer:** B

### Q2. An admin invites someone who already has an account on a different org. Your system creates a duplicate user record with two logins for two orgs. What should happen instead?

- **A.** Link the user to the new org via a membership table — one account, multiple org memberships  ✅
- **B.** Duplicate accounts are the expected approach for users active in multiple organizations
- **C.** Block the invitation because the email address is already registered under another organization
- **D.** Delete the user's existing account entirely and create a brand-new one under the inviting org

> **Answer:** A

### Q3. Your role system has Admin and User only. A customer wants a Billing Manager who can view invoices and update payment but cannot access product data or manage team. What is needed?

- **A.** Two simple roles — admin and non-admin — is generally sufficient for access control in any SaaS app
- **B.** Create a custom API endpoint that only returns billing data and restrict access to that URL
- **C.** A granular permission system where roles define specific capabilities — not just admin-or-not  ✅
- **D.** Let the Billing Manager log into the Stripe dashboard directly to handle all payment tasks

> **Answer:** C

### Q4. Your API checks roles in the frontend only. A member opens DevTools, changes their role to admin, and refreshes. They see admin settings. What is broken?

- **A.** DevTools access should be disabled for non-admins to prevent frontend role inspection
- **B.** Role checks must be enforced on the backend API — frontend-only checks are easily bypassed  ✅
- **C.** The role value should be stored in an encrypted cookie instead of localStorage for better security
- **D.** Add obfuscation to the role value stored in the browser so users can't easily modify it directly

> **Answer:** B

### Q5. An admin removes a team member but their session token remains valid for 24 hours. During that time they can still access the product and see company data. What needs to change?

- **A.** 24-hour token expiry is industry standard and acceptable for most SaaS applications
- **B.** Session tokens are immutable and can't be invalidated before their natural expiry date arrives
- **C.** The removed member should receive an email notification asking them to log out voluntarily
- **D.** Removing a team member should immediately invalidate their active sessions and tokens  ✅

> **Answer:** D

### Q6. The founding user goes through 5 onboarding steps. An invited user who clicks the invitation link also goes through all 5 steps including create org and choose plan. What is wrong?

- **A.** Invited users should skip org creation, plan selection, and payment — they join an existing org  ✅
- **B.** Consistency in onboarding is important — every user should see the same complete full signup flow
- **C.** Send the invitee a pre-filled registration form with a unique code that links them to the team
- **D.** The invited user should create their own org first, then the admin merges the accounts together

> **Answer:** A

### Q7. Your Viewer role can read all data but not modify. However testing shows a Viewer can call PUT /api/projects/:id and update project data successfully. What is missing?

- **A.** Viewers should be able to edit their own projects — the role should only restrict others' content
- **B.** The frontend should prevent Viewers from seeing the edit button — that's the correct enforcement layer
- **C.** The API endpoint is missing a role check — it should verify edit permission before processing updates  ✅
- **D.** PUT requests should be disabled globally for all Viewer sessions regardless of target resource

> **Answer:** C

### Q8. A user is Admin in Org A and Viewer in Org B. Your app has no active-org tracking. They see Admin controls but API calls affect Org B data because it was last used. What is the bug?

- **A.** The app needs an active org context — permissions should be evaluated per org, not globally  ✅
- **B.** Users shouldn't be allowed in multiple organizations — each user should belong to one org only
- **C.** Admin access should apply universally across all organizations that the user is a part of currently
- **D.** The settings page should show controls for all of the user's organizations simultaneously

> **Answer:** A

### Q9. Your invitation link contains a token that never expires. Someone forwards the invite email 6 months later and an unauthorized person joins the org. What should be different?

- **A.** Invitation forwarding is the sender's responsibility, not a platform security concern
- **B.** Invitations should only work from the original recipient's IP address for security verification
- **C.** The invitation link should require the recipient to enter a password before they can access it
- **D.** Invitation tokens should expire after a set period, be single-use, and be revocable by admins  ✅

> **Answer:** D

### Q10. Your team page lets admins change any role. But there is no restriction on changing the Owner. An admin demotes the Owner to Viewer and nobody can fix it. What guardrail is needed?

- **A.** Admins should be able to change any role including Owner for maximum organizational flexibility
- **B.** The Owner role should be protected — only the current Owner can transfer ownership to someone  ✅
- **C.** Add a confirmation dialog before role changes to prevent accidental admin modifications
- **D.** Create a Super Admin role with privileges above Owner to provide an additional oversight layer

> **Answer:** B

### Q11. Your Member role can create, edit, and delete projects. A customer wants some members to create and edit but not delete. Your fixed roles cannot do this. What needs to change?

- **A.** Add a new Limited Member role with hardcoded permissions to handle the finance team's current needs
- **B.** Deletion should require admin approval via a request workflow instead of introducing a new role
- **C.** Move from fixed roles to configurable permissions — let admins define custom roles per team  ✅
- **D.** Members should never have delete permissions — only admins should be allowed to delete

> **Answer:** C

### Q12. Your signup creates user and org in one API call. If org creation fails the user account is created but orphaned — no org, no subscription, no role. What is the fix?

- **A.** Wrap user and org creation in a transaction — if either step fails, both operations roll back  ✅
- **B.** Orphaned accounts are cleaned up automatically by the system over time via a background process
- **C.** Create the organization record first and then the user record as a separate sequential operation
- **D.** Add error handling that deletes the user record if the subsequent org creation step fails

> **Answer:** A

### Q13. Your invitation email has the subject line and a link but no context — who invited them, what the product does, or what happens when they click. What should the email include?

- **A.** The invitation link alone is sufficient — the invitee can figure out the rest once they click through
- **B.** Who invited them, which org they're joining, and what role they'll have — set expectations first  ✅
- **C.** The invitation email should contain a temporary password for login without registration
- **D.** Include a link to the product's pricing page so the invitee understands the plan they're joining now

> **Answer:** B

### Q14. Your JWT contains the user role as a claim. The system never re-checks against the database. An admin is demoted to member but their token still says admin for 24 hours. What is the risk?

- **A.** JWT claims are tamper-proof, so the role stored inside the token is always reliable and current
- **B.** Add the updated role to the token refresh logic only — the current token doesn't need to be invalidated
- **C.** A 24-hour delay is an acceptable window for role changes to take effect given how infrequently they happen
- **D.** A demoted user keeps admin access until token expiry — role changes must invalidate tokens right away  ✅

> **Answer:** D

### Q15. Your app creates a full user account with a temporary password when an invite is sent. The invitee gets an email with login credentials before accepting. What is the security concern?

- **A.** Temporary passwords are a standard invitation pattern used by most enterprise-grade SaaS applications
- **B.** The temporary password should be significantly longer and more complex for stronger security assurance
- **C.** Pre-created accounts with temp passwords are active before opt-in — pending invites are the safer path  ✅
- **D.** Email the invitee's manager instead of the invitee directly so the manager coordinates onboarding fully

> **Answer:** C

### Q16. Your team page shows Remove buttons with no confirmation step. An admin accidentally clicks Remove on the wrong person and the member is instantly deleted. What UX pattern is missing?

- **A.** A confirmation dialog naming the member being removed and explaining consequences before executing  ✅
- **B.** Speed is more important than confirmation dialogs in team management — admins know what they're doing
- **C.** The Remove button should require double-clicking as a safeguard against accidental member removal
- **D.** Removed members should be able to rejoin the organization at any time without needing a new invitation

> **Answer:** A

### Q17. Your free plan has a 3-user limit. An admin invites a 4th member. The system sends the email but the new member cannot activate because the seat limit is reached. What should happen?

- **A.** The error message at signup is appropriate — it tells the invitee to contact the admin about seats
- **B.** Allow the fourth member to join but restrict their access to read-only until the plan is upgraded
- **C.** Seat limits should only apply to paid plans — free plans should allow unlimited members for early growth
- **D.** The seat limit should be checked at invitation time — block the invite and prompt admin to upgrade  ✅

> **Answer:** D

### Q18. Your team settings page lists all members and their roles. But there is no audit log — when a member's role changes you cannot tell who changed it or when it was changed. What is needed?

- **A.** Role changes are infrequent enough that tracking who made them isn't worth the extra effort
- **B.** A weekly email to the Owner summarizing the current member list and each assigned role
- **C.** Only the Owner should be allowed to change roles so there is never a question of who did it
- **D.** An audit log recording each role change — who made it, who was affected, and exactly when  ✅

> **Answer:** D

### Q19. Your API middleware checks if the request has a valid JWT but does not check what role or permissions the user has. Any authenticated user can call any endpoint. What is this called?

- **A.** Broken session management — the JWT itself should carry every permission the user holds
- **B.** Missing authorization — the API authenticates who you are but never checks what you may do  ✅
- **C.** A rate limiting gap — the API accepts too many requests from a single authenticated user
- **D.** An encryption weakness — the JWT payload should be encrypted so users cannot read the claims

> **Answer:** B

### Q20. Users can be in multiple orgs. On login they always land in the first org they joined even if they primarily use a different one. There is no way to set a default. What should be added?

- **A.** A user preference for default org, plus a persistent switcher that remembers the last-used org  ✅
- **B.** The first-joined org is a reasonable default regardless of the user's current activity
- **C.** The login page should ask which org to enter on every login to avoid making incorrect assumptions
- **D.** Users should only be allowed in one organization to avoid this multi-tenancy complexity entirely

> **Answer:** A

### Q21. Your RBAC has four fixed roles. A customer wants a Finance role for billing only. Adding a new role requires a code change and deployment. What is the architectural limitation?

- **A.** Four fixed roles is sufficient for any organization — adding more creates confusion for admins
- **B.** Create the Finance role as a one-time update in the codebase and deploy it alongside the next release
- **C.** Roles should be data-driven and stored in the database — so admins can create roles without a deploy  ✅
- **D.** The existing Viewer role can be repurposed for Finance users by adjusting its current permissions

> **Answer:** C

### Q22. Your invitation link works in Chrome but fails in Safari because the signup page uses an unsupported JavaScript feature. The invitee sees a blank page. What testing gap is this?

- **A.** Safari users should switch to Chrome — the platform doesn't need to support every browser available
- **B.** Add a notification banner telling Safari users to switch to Chrome before completing signup
- **C.** The invitation link should open a native mobile app instead of the web-based signup page for users
- **D.** Invitation flows must be tested across major browsers and devices — a Safari failure loses invitees  ✅

> **Answer:** D

### Q23. An admin CSV export of all team members does not check if the requester is an admin. Any authenticated member can export the full team directory. What is the risk?

- **A.** Any member can extract employee lists, emails, and access levels — exports need the same role checks  ✅
- **B.** Team directories aren't sensitive data — any member should be able to export the employee list freely
- **C.** CSV exports are inherently secure because they're local files that stay on the user's own machine safely
- **D.** The endpoint is safe because it's not documented in the public API docs and users won't discover it

> **Answer:** A

### Q24. Your magic link login URL is logged in application logs with the full token visible. What is the exposure?

- **A.** Application logs are internal infrastructure and inherently secure — no extra precautions are needed
- **B.** Anyone with log access can use magic link tokens to impersonate users — auth tokens must be excluded  ✅
- **C.** Magic link tokens expire quickly so logging them in plaintext is safe and doesn't create a real risk
- **D.** Logs should contain all request data including tokens for comprehensive debugging and analysis

> **Answer:** B

### Q25. Your Last Active column uses login time not actual usage. A member who logged in 3 months ago via persistent session might use the app daily but appears inactive. What metric is better?

- **A.** Last login timestamp is the standard metric for tracking user activity across SaaS applications today
- **B.** Session duration measured in minutes is a more accurate indicator of engagement than activity data
- **C.** Track last activity — the most recent API request or page view — reflecting actual usage not logins  ✅
- **D.** Ask members to self-report their usage levels through a periodic survey sent out by the admin team

> **Answer:** C


---
_Take it in the browser: https://the-faction.mn.co/posts/103821123_
