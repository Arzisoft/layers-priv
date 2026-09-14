---
course: "The Industry"
module: "Module 4: Crew Roles & Subcontractor Access"
lesson: "Module 4: Crew Roles & Subcontractor Access — Exam"
type: "course_quiz"
post_id: 104453743
space_id: 24251863
source: "https://the-faction.mn.co/posts/104453743"
updated: "2026-08-10T18:15:43Z"
---

# Module 4: Crew Roles & Subcontractor Access — Exam

> Exam for **Module 4: Crew Roles & Subcontractor Access** (The Industry) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. Your AI builds a construction platform where every user sees every project in the company portfolio. A subcontractor sees all 15 project budgets. What is wrong?

- **A.** The platform is loading too much data and the subcontractor device will experience significant performance slowdowns
- **B.** Users should be scoped to assigned projects only so subcontractors see just the projects they are working on  ✅
- **C.** The sub should get a filtered view that hides financial data but still shows other project details
- **D.** The platform needs a separate login portal for subcontractors that connects to an isolated database instance

> **Answer:** B

### Q2. An electrical subcontractor can see the plumbing sub contract price on a shared project. Why is this a problem?

- **A.** The electrical sub may file a formal complaint with the project owner about unfair access to confidential data
- **B.** The plumbing sub contract price is inaccurate in the system and showing it to others spreads incorrect information
- **C.** Viewing another trade contract requires a paid subscription tier that the electrical subcontractor has not purchased
- **D.** Competitive pricing between subcontractors must be isolated so one trade cannot see another trade cost information  ✅

> **Answer:** D

### Q3. A project owner logs into your platform and edits the construction schedule directly. The PM discovers the changes a day later. What access control is missing?

- **A.** Owners should have read-only access to project data with no ability to modify schedules, costs, or scope documents  ✅
- **B.** Owners should have edit access but all changes should require PM approval before they are applied to the project
- **C.** The platform should send a notification to the PM immediately whenever any user modifies the project schedule data
- **D.** The owner account should be restricted to viewing only the budget summary without access to the full project schedule

> **Answer:** A

### Q4. Field workers share a tablet at the job site trailer. Logging in requires email and a complex password. Workers start sharing one account. What should you change?

- **A.** Issue individual phones to every field worker so they each have their own device and no longer need to share logins
- **B.** Remove the authentication requirement for the shared tablet since it is only accessible inside the job site trailer
- **C.** Implement quick-switch authentication using PINs or badge scans so workers can change users in a few seconds  ✅
- **D.** Create a shared field worker account with limited permissions that all workers on the project use simultaneously

> **Answer:** C

### Q5. A building inspector needs access to approved plans, submittals, and previous inspection results. Your platform gives them full edit access. What is the risk?

- **A.** The inspector may accidentally delete critical documents while navigating the interface looking for the needed files
- **B.** An inspector who can edit records such as inspection results or approved plans compromises the integrity of data  ✅
- **C.** The inspector will see cost and pricing data that is irrelevant to their role and creates a confusing user interface
- **D.** The hosting platform charges additional licensing fees for users with full edit access on projects

> **Answer:** B

### Q6. A subcontractor finished their scope three months ago but still has active access to the project portal. Why should access be revoked?

- **A.** The platform license count includes the subcontractor and removing their access frees up a seat for another user
- **B.** The subcontractor may submit fraudulent invoices through the platform portal using their still-active project access
- **C.** Active access for a completed subcontractor triggers a compliance flag in the project auditing system automatically
- **D.** The sub can still view current schedule, costs, and documents for a project they are no longer contractually part of  ✅

> **Answer:** D

### Q7. Your platform assigns roles at the company level, not the project level. A superintendent on Project A can see all data on Project B. What needs to change?

- **A.** Roles and permissions should be scoped to specific project assignments so each user sees only their assigned work  ✅
- **B.** The superintendent should be trained to only access their own project data and ignore information from other jobs
- **C.** A confirmation dialog should appear each time a user navigates to a project asking if they are authorized to view it
- **D.** The platform should log all cross-project access so administrators can review unauthorized data views after the fact

> **Answer:** A

### Q8. Your AI builds a subcontractor portal that shows the sub their scope and payment status. It also displays the GC markup percentage. What must be hidden?

- **A.** The payment status should be hidden because subcontractors should track their own payments through their accounting
- **B.** The scope details should be summarized at a high level because full scope visibility gives the sub negotiating leverage
- **C.** The GC markup percentage is competitive information that subcontractors must never see on the project portal view  ✅
- **D.** The project timeline should be removed from the sub portal because subcontractors manage their own crew schedules

> **Answer:** C

### Q9. A new subcontractor is hired mid-project. The PM wants them to have immediate portal access scoped to their trade only. What is the best onboarding flow?

- **A.** Create a platform-wide account for the subcontractor company and let them see all projects until the PM restricts it
- **B.** Send a project invitation with pre-configured role permissions so the sub gets scoped access as soon as they accept  ✅
- **C.** Ask the subcontractor to create their own account and then email the PM to request access to the correct project
- **D.** Add the subcontractor to a shared credentials list that gives them access through a generic team login on the site

> **Answer:** B

### Q10. Your role hierarchy includes Company Admin, Project Manager, and Field Worker. A superintendent needs daily scheduling control but not financial access. What is missing?

- **A.** A custom permission builder that lets the PM configure individual feature access for every user on every project
- **B.** A read-only financial view for the superintendent so they can see budget status without the ability to make changes
- **C.** A delegation feature where the PM temporarily grants their own financial permissions to the superintendent daily
- **D.** A superintendent role between PM and field worker that has crew and schedule permissions but not financial access  ✅

> **Answer:** D

### Q11. Your platform enforces role permissions on the frontend but not on the API. A subcontractor uses developer tools to call restricted API endpoints directly. What happens?

- **A.** The sub accesses restricted data because the API has no permission checks and returns any data the endpoint serves  ✅
- **B.** The developer tools are blocked by the platform security layer which prevents direct API calls from browser consoles
- **C.** The API returns an encrypted response that only the correct frontend role can decrypt and display to the user view
- **D.** The hosting platform firewall detects the unauthorized API call pattern and blocks the subcontractor IP address

> **Answer:** A

### Q12. A foreman switches to another user account on the shared tablet but can still see the previous user daily report draft. What failed in the user switch?

- **A.** The daily report draft is stored on the tablet hardware and not associated with any specific user account in system
- **B.** The tablet operating system is caching the previous session data and needs a full device restart to clear the state
- **C.** The quick-switch authentication did not fully clear the previous user session and their unsaved data persists locally  ✅
- **D.** The daily report form auto-saves to the project level instead of the user level so any worker on the project sees it

> **Answer:** C

### Q13. An architect on the project needs to respond to RFIs and review submittals but should not access cost data or the construction schedule. How do you configure their role?

- **A.** Give the architect full project access and train them to only use the RFI and submittal sections of the platform
- **B.** Create a separate project instance for the architect that contains only the documents relevant to their work scope
- **C.** Share RFI and submittal documents via email instead of giving the architect any direct access to the platform
- **D.** Define an architect role with permissions limited to RFI responses and submittal reviews with no cost or schedule view  ✅

> **Answer:** D

### Q14. Your platform has no audit log for permission changes. A PM removes a sub access and the sub claims they were locked out unfairly. What evidence is available?

- **A.** None, because without an audit log there is no record of when the permission was changed or who made the change  ✅
- **B.** The platform database transaction log shows all data changes including permission updates with full user attribution
- **C.** The PM email records should contain a notification that was sent when the permission change was processed by system
- **D.** The subcontractor login history shows the exact timestamp when their access stopped working on the project portal

> **Answer:** A

### Q15. A company admin accidentally gives a field worker company-wide admin permissions. What safeguard should prevent this?

- **A.** A training requirement that ensures all company admins understand the permission hierarchy before they can assign roles
- **B.** A confirmation step and role escalation warning that flags when a user is being elevated beyond their standard level  ✅
- **C.** An automatic rollback that detects unusual permission assignments and reverts them after a twenty-four hour window
- **D.** A policy that restricts role assignment to a single designated administrator rather than allowing multiple admin users

> **Answer:** B

### Q16. Your platform allows subcontractors to see which other subs are working on the same project. Is this acceptable?

- **A.** No, subcontractors should not know which other companies are on the project because it reveals the GC bid strategy
- **B.** Yes, seeing other trade names helps subcontractors coordinate their work sequence and avoid scheduling conflicts
- **C.** Trade names and contacts may be visible for coordination but contract values and scope details must remain hidden  ✅
- **D.** Only the GC should control what subcontractor information is shared and the platform should hide everything by default

> **Answer:** C

### Q17. Your invitation system sends a link that grants project access without requiring any identity verification. What is the risk?

- **A.** The email server may flag the invitation as spam and the intended recipient never receives their access credentials
- **B.** The link expires after a fixed period so if the recipient does not act quickly they will need a new invitation sent
- **C.** The invitation link consumes a platform license seat immediately even if the intended recipient never actually logs in
- **D.** Anyone who obtains the link can access the project data without proving they are the intended authorized recipient  ✅

> **Answer:** D

### Q18. Your role testing shows that a PM can view data from projects they are not assigned to by changing the project ID in the URL. What type of vulnerability is this?

- **A.** An insecure direct object reference where the server does not verify the user has permission for the requested project  ✅
- **B.** A cross-site scripting vulnerability where the URL parameter injects unauthorized JavaScript into the page response
- **C.** A session fixation attack where the modified URL forces the server to associate the PM with a different project session
- **D.** A privilege escalation exploit where changing the URL parameter temporarily elevates the PM to a company admin role

> **Answer:** A

### Q19. A GC wants their project managers to see all project data but not be able to delete records. How should the role be configured?

- **A.** Give the PM full admin access and add a confirmation dialog before any delete operation to prevent accidental removal
- **B.** Grant the PM read and write permissions on all project data but restrict delete permissions to company admin only  ✅
- **C.** Create a separate backup of all data nightly so that any records a PM deletes can be restored from the backup copy
- **D.** Disable the delete function entirely for all users since construction records should never be removed from the system

> **Answer:** B

### Q20. Field workers on your platform cannot see any project data until a PM manually approves each access request. Onboarding takes days. What should change?

- **A.** Remove the approval requirement entirely so any authenticated user can access any project they search for on site
- **B.** Pre-approve all field workers at the company level so they automatically have access to every active project running
- **C.** Use role-based templates so when a worker is assigned to a project they receive standard field permissions instantly  ✅
- **D.** Allow the superintendent to grant temporary access that expires at the end of each shift and must be renewed daily

> **Answer:** C

### Q21. You audit your platform permissions and discover that a test account with admin access is still active from the development phase. What should you do?

- **A.** Immediately deactivate the test account and review all other accounts for stale or unnecessary elevated permissions  ✅
- **B.** Change the test account password to something stronger since the elevated access may be needed for future testing
- **C.** Downgrade the test account to field worker level so it still functions for testing but cannot access sensitive data
- **D.** Leave the account active but add monitoring so that any login from the test account triggers an alert notification

> **Answer:** A

### Q22. Your platform sends an email with the project name and a direct login link every time a user is invited. An unauthorized person intercepts the email. What is exposed?

- **A.** Only the project name is exposed and the login link requires additional authentication that the interceptor lacks
- **B.** The email contains no sensitive data because the login link redirects to a generic authentication page for all users
- **C.** The interceptor can see the email but cannot use the link because it is tied to the specific recipient email address
- **D.** The project name reveals confidential information and if the link lacks identity verification access may be granted  ✅

> **Answer:** D

### Q23. A subcontractor requests access to the full project schedule to better plan their crew deployment. Should you grant it?

- **A.** Yes, full schedule access helps all subcontractors coordinate and reduces the chance of scheduling conflicts on site
- **B.** Grant access to only the schedule items relevant to their trade and the predecessor tasks that directly affect them  ✅
- **C.** Deny all schedule access because the project schedule contains sequencing information that is proprietary to the GC
- **D.** Share the schedule as a static PDF export so the subcontractor can view it without having live platform access

> **Answer:** B

### Q24. Your platform has four external roles: subcontractor, owner, architect, and inspector. All four share the same permission template. What is the problem?

- **A.** The shared template means all four roles receive email notifications for every project event creating message overload
- **B.** The platform cannot distinguish between the four roles in the audit log because they share the same permission set
- **C.** Each external role needs different data visibility and a shared template either over-exposes or under-serves each one  ✅
- **D.** The shared permission template uses more database storage than four individual templates would for the same users

> **Answer:** C

### Q25. You complete a full permissions audit and everything is configured correctly. How often should role assignments and access controls be re-verified?

- **A.** After every project phase change and when team members join or leave because access needs shift during the project  ✅
- **B.** Only at the start and end of each project because role assignments do not change during active construction work
- **C.** Once per quarter during a scheduled security review that covers all platform settings including permission controls
- **D.** Permissions do not need re-verification once set because the system enforces them automatically going forward

> **Answer:** A


---
_Take it in the browser: https://the-faction.mn.co/posts/104453743_
