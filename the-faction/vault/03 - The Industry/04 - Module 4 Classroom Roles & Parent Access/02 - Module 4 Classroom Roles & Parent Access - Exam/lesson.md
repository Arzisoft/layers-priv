---
course: "The Industry"
module: "Module 4: Classroom Roles & Parent Access"
lesson: "Module 4: Classroom Roles & Parent Access — Exam"
type: "course_quiz"
post_id: 104111996
space_id: 24251863
source: "https://the-faction.mn.co/posts/104111996"
updated: "2026-08-21T03:09:34Z"
---

# Module 4: Classroom Roles & Parent Access — Exam

> Exam for **Module 4: Classroom Roles & Parent Access** (The Industry) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. A teacher has access to all 600 students in their school but only teaches 2 sections with 35 students each. They can view grades for students they have never taught. What permission boundary is wrong?

- **A.** The teacher's data access should be restricted to students in their assigned grade level rather than scoped to specific class sections
- **B.** Teacher access should be scoped to their assigned sections only — a teacher sees their 70 students, not the entire school building  ✅
- **C.** A data access agreement should be signed by each teacher acknowledging they will view records for students in their own classes
- **D.** The school administrator should configure custom access lists for each teacher specifying which individual students they can view data on

> **Answer:** B

### Q2. A parent creates an account and links to a student by entering only the child's name and date of birth. No school verification is required. A restricted non-custodial parent gains access. What should change?

- **A.** Require government-issued photo identification upload during parent account creation to verify the adult's identity before linking
- **B.** Add a secondary verification step where the parent must also provide the student's school-assigned identification number to complete
- **C.** Guardian linking must be verified through the school — SIS records provide parent data or school administrators approve link requests  ✅
- **D.** Implement a waiting period of 48 hours between parent account creation and student linking so schools can review pending connections

> **Answer:** C

### Q3. Your platform collects student names, emails, and learning activity data during account creation. The student is 11 years old and no parental consent was obtained. What federal law is being violated?

- **A.** FERPA requires parental notification before any educational technology vendor can create student accounts within their platform system
- **B.** The Children's Internet Protection Act requires parental approval for students under 13 to access online educational platform content
- **C.** State-level student data privacy laws require school board approval before deploying new educational technology to minor students
- **D.** COPPA requires verified parental consent before collecting personal information from children under 13 years of age for any purpose  ✅

> **Answer:** D

### Q4. A district admin manages all schools in their district. A new school joins the district. The admin cannot see it because the system requires manual per-school assignment. What model scales better?

- **A.** District admin scope should derive from district membership automatically — new schools inherit the admin hierarchy without manual setup  ✅
- **B.** A bulk assignment tool that lets IT staff add multiple schools to an administrator's access list in a single batch operation
- **C.** Self-service school onboarding where new schools register themselves and automatically appear in the existing district admin's dashboard
- **D.** A scheduled sync job that checks for new schools nightly and updates all district administrator access lists during the overnight window

> **Answer:** A

### Q5. A teacher leaves the school mid-year. Their session token remains valid for seven more days. During that time they can still access student grades and rosters. What security gap exists?

- **A.** Reduce the default session token expiration from seven days to 24 hours so former employees lose access more quickly after departure
- **B.** Add an exit interview step where departing teachers must explicitly log out of all active sessions before their employment officially ends
- **C.** Deprovisioning should revoke active sessions immediately — when a teacher is removed, their access ends at that moment, not days later  ✅
- **D.** Implement device-bound tokens that only work on the teacher's registered school device which would be collected upon their departure

> **Answer:** C

### Q6. A parent account is linked to their child and can see grades and attendance. But the parent also sees other students' names and grades through the class discussion forum. What is the data leak?

- **A.** Disable the discussion forum entirely for parent accounts since forums inherently expose peer student information to non-student users
- **B.** Discussion visibility for parents must be scoped to their child only — parents should never see other students' identities or content  ✅
- **C.** Make all discussion posts anonymous for all users so that neither students nor parents can identify individual classmate contributions
- **D.** Restrict parent portal access to grades and attendance and remove all interactive community features from the parent-facing view

> **Answer:** B

### Q7. Your role enforcement lives in the frontend JavaScript only. A user opens browser DevTools, changes their stored role from member to admin, and accesses the admin settings panel. What is broken?

- **A.** Obfuscate the role value in browser storage using encryption so casual users cannot identify or modify the stored value
- **B.** Implement a content security policy header that prevents browser developer tools from modifying application state during active sessions
- **C.** Add a secondary role verification check on the frontend that compares the stored role against a signed token before rendering admin views
- **D.** Role enforcement must happen on the backend API — frontend checks are display logic only and can be bypassed by any technical user  ✅

> **Answer:** D

### Q8. A school administrator tries to invite a new teacher. The system requires district admin approval for every teacher invitation. The district admin is unavailable for two days. What delegation is missing?

- **A.** School admins should invite and manage teachers within their building without requiring district-level approval for routine operations  ✅
- **B.** An auto-approval rule that automatically grants teacher invitations if the district admin does not respond within a 24-hour window period
- **C.** A backup district admin account that school administrators can use to approve their own teacher invitations during admin unavailability
- **D.** Pre-approved invitation quotas letting school admins send up to ten teacher invitations per month without district intervention

> **Answer:** A

### Q9. Your system has role-based access but no audit log tracking who viewed which student records and when. A district requests an access report for their annual FERPA review. You cannot produce one. What should exist?

- **A.** Database query logs that capture every SQL statement executed against student tables which can be parsed for access pattern analysis
- **B.** A weekly access summary report generated automatically and emailed to district administrators showing aggregate usage statistics only
- **C.** Signed user acknowledgment forms confirming that each staff member only accessed student records within their authorized role scope
- **D.** An audit log recording every student data access event — who viewed what record, when, and in what role context for FERPA compliance  ✅

> **Answer:** D

### Q10. A student belongs to two course sections taught by different teachers. Teacher A can see the student's grades in Teacher B's section. Each teacher should only see their own grades. What boundary is wrong?

- **A.** Display all of the student's grades to both teachers since they share responsibility for the same student's overall academic performance
- **B.** Add a visibility toggle letting each teacher choose whether they want to see grades from other sections for shared students
- **C.** Permission scoping should be per-section — Teacher A sees only their section's grades, not grades from any other teacher's sections  ✅
- **D.** Create separate student profiles for each section so Teacher A's instance of the student is completely independent from Teacher B's view

> **Answer:** C

### Q11. A parent's custody arrangement changes after a divorce. A court order restricts one parent's access. Your system has no mechanism to restrict individual guardian access to student records. What capability is needed?

- **A.** Remove the restricted parent's account entirely from the platform and instruct the school to deny any future account creation requests
- **B.** Configurable guardian access levels — school admins must be able to restrict specific guardians' data access based on legal custody orders  ✅
- **C.** Require both parents to share a single account with one set of credentials so the custodial parent controls all platform access decisions
- **D.** Direct the school to handle custody-related access restrictions outside the platform through manual administrative oversight processes only

> **Answer:** B

### Q12. Student accounts use auto-generated passwords like Student123 with predictable patterns. Students share these with each other and access classmates' accounts. What authentication approach eliminates this risk?

- **A.** SSO through the school's existing identity provider so students authenticate with credentials they already use daily without sharing  ✅
- **B.** Randomized complex passwords generated for each student that are distributed securely through sealed envelopes to their parents
- **C.** Multi-factor authentication requiring both a password and a one-time code sent to the student's registered phone number on each login
- **D.** Biometric authentication using fingerprint or facial recognition on school-issued devices to eliminate password-based credentials entirely

> **Answer:** A

### Q13. A school has elementary, middle, and high school divisions. An elementary teacher can see high school student records because all teachers share the same school-wide access scope. What additional scoping is needed?

- **A.** Train elementary teachers to only access records for students in their own grade levels through policy guidelines and annual reminders
- **B.** Grade-level or building-level scoping — teachers should only see students in their grade band or division within a multi-level school  ✅
- **C.** Split the multi-level school into three separate school instances in the platform, each with its own independent user management system
- **D.** Add a data access agreement that elementary teachers sign acknowledging they will not view high school student records inappropriately

> **Answer:** B

### Q14. Invitation links for new teacher accounts never expire and can be reused. A year-old link is found in a forwarded email. An unauthorized person uses it to create a teacher account. What should invitation tokens do?

- **A.** Require the invited teacher to verify their identity by uploading a government-issued photo ID before the account creation completes
- **B.** Restrict invitation links to only work from the specific email address they were originally sent to by validating the recipient domain
- **C.** Send invitation links through an encrypted messaging channel rather than email so they cannot be forwarded to unauthorized recipients
- **D.** Expire within 24-72 hours, work for a single use only, and be revocable by the school administrator who originally sent the invitation  ✅

> **Answer:** D

### Q15. A student graduates in June. In September, they can still log in and see current students' course data because their account was never deactivated. What process should trigger at graduation?

- **A.** Convert the graduated student's account to an alumni role with continued read-only access to their own historical academic records only
- **B.** Set an automatic session expiration date aligned with the graduation ceremony so the account becomes inaccessible after that calendar day
- **C.** Graduated accounts must be deactivated at end of academic year — active accounts with access to current student data violate FERPA rules  ✅
- **D.** Send a notification to graduated students requesting that they voluntarily close their accounts and confirming their data will be archived

> **Answer:** C

### Q16. Teachers create student groups for differentiated instruction. A group called Struggling Readers is visible to all students in the class. Students in the group feel stigmatized. What labeling control should exist?

- **A.** Student group names should be visible only to teachers — students see neutral identifiers or no group labels at all to prevent stigma  ✅
- **B.** Require teachers to use only positive or growth-oriented labels for student groups such as Emerging Readers instead of negative framing
- **C.** Allow students to choose which instructional groups they join voluntarily rather than being assigned by the teacher based on performance
- **D.** Display group membership only on the teacher dashboard and remove all group-related indicators from the student-facing course interface

> **Answer:** A

### Q17. Your permission system caches the user's role at login for the entire session. An admin demotes a teacher to viewer mid-day. The teacher retains full access until their session expires hours later. What should change?

- **A.** Reduce session duration from 8 hours to 30 minutes so cached roles are refreshed more frequently throughout the day's active usage period
- **B.** Send a push notification to the affected user requesting they log out and log back in so their new role assignment takes immediate effect
- **C.** Implement a heartbeat check every 5 minutes that refreshes the user's cached role from the database without requiring a full re-login flow
- **D.** Role changes should invalidate active sessions immediately or critical operations should verify current roles against the live database  ✅

> **Answer:** D

### Q18. A substitute teacher needs temporary access to a classroom for one week. Your system only supports permanent role assignments. The admin adds them and forgets to remove access three months later. What's needed?

- **A.** Time-limited role assignments with automatic expiration — set an end date on the substitute's access so it revokes without manual action  ✅
- **B.** A daily access review dashboard that alerts administrators to all temporary staff accounts that have been active beyond their expected period
- **C.** A separate substitute teacher role with reduced permissions that does not require manual removal since it cannot access sensitive student data
- **D.** Calendar-based access tied to the school's substitute scheduling system that provisions and deprovisions based on daily assignment rosters

> **Answer:** A

### Q19. Your API endpoint /api/students returns the full school roster with email addresses when called by any authenticated user, including students. A student's API call returns every classmate's contact information. What's the vulnerability?

- **A.** Rate limit the students API endpoint to prevent bulk data extraction by restricting the number of records returned per authenticated request
- **B.** Remove email addresses from the API response entirely since student contact information should not be accessible through any API endpoint
- **C.** The endpoint must check the caller's role — student-role API calls should return only that individual student's own data, not the roster  ✅
- **D.** Require API consumers to authenticate with a separate API key in addition to their user session before accessing the students endpoint

> **Answer:** C

### Q20. A parent can see their child's grades but cannot see teacher comments on assignments. The parent misses important qualitative feedback about their child's learning progress. What is the portal gap?

- **A.** Teacher comments should remain visible only to students since some feedback may contain instructional language inappropriate for parents
- **B.** Parent views should include teacher feedback and comments — the qualitative context parents need to support their child's academic growth  ✅
- **C.** Create a separate parent communication channel where teachers can share feedback summaries without exposing individual assignment comments
- **D.** Generate automated progress narratives from grade data that provide parents with AI-written summaries of their child's overall performance

> **Answer:** B

### Q21. A district has 15 schools. Each school admin sees only their building. But the district admin has no unified view across all 15 schools and must log into each school's admin panel separately. What's missing?

- **A.** An automated report that compiles data from all 15 schools into a single document delivered to the district admin's email inbox weekly
- **B.** A shared database view that removes school-level isolation so all administrators see all data regardless of their assigned school building
- **C.** A data warehouse that aggregates school-level data nightly into summary tables that the district admin queries through a separate interface
- **D.** A district-level dashboard with unified cross-school analytics and drill-down capability into individual school buildings when needed  ✅

> **Answer:** D

### Q22. A teacher accidentally shares their screen during a virtual class, revealing an admin panel with other teachers' salary data from a linked HR module. What access control failure occurred?

- **A.** Teachers should never see HR or salary data — module-level access controls must prevent exposure of data outside the educational scope  ✅
- **B.** The HR module should be hosted on a completely separate platform with no integration points to the educational technology environment
- **C.** Screen sharing software should automatically detect and blur sensitive information when administrative panels are visible on the display
- **D.** The teacher's account was likely provisioned with an incorrect admin role that granted unintended access to the human resources module

> **Answer:** A

### Q23. A technology director needs to manage user accounts, configure integrations, and view system logs. They are not an educator and should not see student academic records. Your roles do not support this separation. What's needed?

- **A.** Grant the technology director full administrative access and establish a written policy that they will not view student academic records
- **B.** Create a read-only observer role that can see all platform content including academic records but cannot modify any student data values
- **C.** A technology administrator role with system management permissions — accounts, integrations, logs — but no access to academic records  ✅
- **D.** Split the platform into two separate applications where one handles administrative functions and the other manages educational content

> **Answer:** C

### Q24. A founding teacher completes a 12-step onboarding including school setup. A new teacher invited later must also complete all 12 steps including school configuration they do not need. What should invited teachers see?

- **A.** A skip button on each onboarding step that lets invited teachers bypass school configuration pages they recognize as already completed
- **B.** Streamlined onboarding that skips school setup entirely — invited teachers go straight to profile creation and immediate classroom access  ✅
- **C.** A video tutorial showing the complete onboarding process so invited teachers understand the full platform even if they skip certain steps
- **D.** The same 12-step onboarding with pre-filled school configuration fields so invited teachers simply confirm each setting without changes

> **Answer:** B

### Q25. Your EdTech platform has two roles: Admin and User. A teacher needs admin-level data access for their 35 students but not the other 565 students in the school. What role architecture is needed?

- **A.** Granular education roles — student, teacher, parent, school admin, district admin — each with scoped data access boundaries per role  ✅
- **B.** A role cloning feature that lets administrators create custom permission sets by duplicating and modifying the existing admin template
- **C.** Attribute-based access control that evaluates user properties like department and grade level dynamically on every data request made
- **D.** A teacher-admin hybrid role that grants full administrative access but filters the student list to show only assigned class rosters

> **Answer:** A


---
_Take it in the browser: https://the-faction.mn.co/posts/104111996_
