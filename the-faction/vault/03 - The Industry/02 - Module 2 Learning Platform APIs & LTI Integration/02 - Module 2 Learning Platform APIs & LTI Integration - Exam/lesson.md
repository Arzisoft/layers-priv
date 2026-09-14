---
course: "The Industry"
module: "Module 2: Learning Platform APIs & LTI Integration"
lesson: "Module 2: Learning Platform APIs & LTI Integration — Exam"
type: "course_quiz"
post_id: 104111500
space_id: 24251863
source: "https://the-faction.mn.co/posts/104111500"
updated: "2026-08-21T03:07:02Z"
---

# Module 2: Learning Platform APIs & LTI Integration — Exam

> Exam for **Module 2: Learning Platform APIs & LTI Integration** (The Industry) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. A student completes a quiz in your LTI-connected tool scoring 85%. The teacher checks the Canvas grade book and the score is missing. What integration feature was not implemented?

- **A.** Roster synchronization that maps student identities between your tool and the Canvas LMS so scores attach to correct learner profiles
- **B.** Grade passback via LTI Assignment and Grade Services so your tool sends assessment scores to the LMS grade book automatically  ✅
- **C.** Webhook notifications that alert the teacher when students complete assessments so they can manually record each score received
- **D.** A grade export feature that generates downloadable CSV files for teachers to import into Canvas through the bulk upload tool

> **Answer:** B

### Q2. Your roster sync runs once per semester. A student transfers into a class in October but cannot access the platform because the roster has not been updated since August. What sync frequency is needed?

- **A.** Weekly batch sync jobs that pull updated enrollment data from the SIS every Sunday evening to capture the prior week's changes
- **B.** Teacher-initiated manual sync where educators click a refresh button to pull updated roster data when they notice missing students
- **C.** Daily or real-time sync via SIS webhooks so enrollment changes like transfers and drops are reflected within hours, not months  ✅
- **D.** Semester sync with a secondary self-registration option where transfer students can create their own accounts independently

> **Answer:** C

### Q3. Your LTI integration works perfectly in Canvas. A new district uses Blackboard. Teachers launch your tool from Blackboard and see a blank iframe with no error message. What caused the failure?

- **A.** Blackboard requires a paid enterprise license agreement for third-party LTI tool integration that the district has not yet purchased
- **B.** The district's firewall security rules are blocking the iframe connection between Blackboard and your external tool's servers
- **C.** Blackboard uses an older LTI version that is fundamentally incompatible with the modern launch protocol your tool requires
- **D.** Your LTI implementation has Canvas-specific assumptions — different LMS platforms have quirks that require cross-platform testing  ✅

> **Answer:** D

### Q4. Your LTI handler extracts user identity from the JWT payload but does not verify the JWT signature against the LMS public key. What security vulnerability does this create?

- **A.** Fabricated tokens — anyone who knows your launch URL could send a fake JWT claiming any user identity or elevated role privileges  ✅
- **B.** Session hijacking — existing valid user tokens could be intercepted and replayed by third parties to access unauthorized student data
- **C.** Token expiration bypass — JWTs without signature checks would continue working indefinitely even after the session period ends
- **D.** Cross-site request forgery — malicious sites could trigger LTI launches on behalf of users without their knowledge or consent

> **Answer:** A

### Q5. Your tool sends a grade of 85 via passback. Canvas displays 0.85 out of 1.0 instead of 85 out of 100. The teacher expects a points-based score. What mapping issue caused the discrepancy?

- **A.** Canvas automatically converts all incoming scores to a weighted percentage scale regardless of the original format submitted
- **B.** The LTI passback API rounds all submitted scores to two decimal places which caused the system to interpret 85 as a decimal value
- **C.** Score format mismatch — LTI passback sent a normalized 0-1 scale value but the Canvas assignment expected a 0-100 point scale  ✅
- **D.** The Canvas assignment was configured with a maximum score of 1 point instead of 100 points causing the fractional display

> **Answer:** C

### Q6. A district has years of interactive curriculum packaged in SCORM format. Your platform only supports its own native content format and cannot import SCORM packages. What is the adoption blocker?

- **A.** The district should convert all of their existing SCORM content to your native format using an automated migration tool before onboarding
- **B.** Missing SCORM runtime support — districts with existing curriculum investments will reject platforms that cannot import their content  ✅
- **C.** SCORM is an outdated standard that the district should plan to phase out in favor of modern xAPI-based learning content packages
- **D.** Your platform should offer a content authoring tool so the district can recreate their curriculum natively inside your system

> **Answer:** B

### Q7. Grade passback fails silently — scores do not appear in the LMS but your tool shows a success message to students. Teachers discover missing grades at the end of the grading period. What should happen on failure?

- **A.** Require students to verify their grade appeared in the LMS after each assessment and report discrepancies to the teacher directly
- **B.** Schedule a nightly reconciliation job that compares all scores between your tool and the LMS and generates a discrepancy report
- **C.** Send an automated email to the LMS administrator listing all failed grade passback attempts for manual intervention and repair
- **D.** Alert the teacher immediately, queue the failed score for automatic retry, and log the error for troubleshooting and recovery  ✅

> **Answer:** D

### Q8. Your platform stores every student's LTI launch data — full name, email, and role — indefinitely for product analytics. A district asks about FERPA data minimization. What is the compliance concern?

- **A.** Retaining student PII indefinitely for analytics may exceed the contracted educational purpose, violating FERPA minimization rules  ✅
- **B.** LTI launch data becomes your platform's property once received and can be retained for any business purpose without restriction
- **C.** FERPA data minimization requirements only apply to the school district's own systems, not to third-party vendor platforms receiving data
- **D.** Analytics data must be stored for a minimum of seven years per federal education record retention requirements before deletion

> **Answer:** A

### Q9. A student launches your LTI tool twice and receives two different quiz scores. Canvas shows the first score, not the higher one. The teacher wants the best attempt recorded. What logic is missing?

- **A.** A single-attempt enforcement that locks the assessment after the first submission and prevents any subsequent retake attempt at all
- **B.** A timestamp-based override that always keeps the most recent score regardless of whether it is higher or lower than the prior
- **C.** An averaging function that calculates the mean of all attempts and submits that composite score to the LMS grade book instead
- **D.** Configurable attempt policy — send the highest, most recent, or teacher-defined score instead of relying on submission timing  ✅

> **Answer:** D

### Q10. A third-party analytics vendor calls your /students API endpoint and stores the returned data in their own database. The school district never authorized this access. What regulation is violated?

- **A.** The analytics vendor violated your platform's terms of service by accessing the API without a valid commercial partnership agreement
- **B.** Your API rate limiting should prevent unauthorized bulk data extraction by throttling requests from unrecognized client applications
- **C.** FERPA prohibits sharing student data with unauthorized third parties — API endpoints with student data must require authorization  ✅
- **D.** The analytics vendor's data storage practices may not meet your platform's security standards for encrypted data at rest compliance

> **Answer:** C

### Q11. A district wants to deploy your tool across 200 courses. Setting up LTI credentials individually for each course would take weeks of manual configuration. What deployment model scales?

- **A.** A scripted batch process that automates the per-course credential creation by iterating through the district's course catalog list
- **B.** Institution-level LTI deployment — configure credentials once at the district level with automatic provisioning across all courses  ✅
- **C.** A phased rollout deploying to ten courses per week over twenty weeks so the manual setup burden is spread across the semester
- **D.** A self-service portal where individual teachers configure their own LTI connections using a simplified setup wizard interface

> **Answer:** B

### Q12. Your xAPI learning statements include students' full names in the actor field. A privacy review flags personally identifiable information in the learning record store. What should the actor field contain?

- **A.** Pseudonymous identifiers that enable learning analytics while keeping personally identifiable student information in your secure system only  ✅
- **B.** Hashed email addresses that provide unique student identification without exposing their actual contact information in analytics records
- **C.** The student's school-assigned ID number which is considered directory information and may be shared more freely under FERPA rules
- **D.** An empty actor field with the student mapping maintained in a separate lookup table that only district administrators can access

> **Answer:** A

### Q13. Your OneRoster roster sync runs nightly at 2am. A teacher adds a new student to their class at 9am. The student cannot access the platform until the next morning. What would close the access gap?

- **A.** A manual override button that lets teachers grant immediate temporary platform access to newly enrolled students while awaiting sync
- **B.** Real-time or hourly roster updates via SIS webhooks so newly enrolled students receive platform access within minutes, not 24 hours  ✅
- **C.** A student self-registration flow where new enrollees create their own accounts using a class code provided by the assigning teacher
- **D.** A scheduled sync running every four hours instead of nightly which would reduce the maximum access gap from 24 hours to 4 hours

> **Answer:** B

### Q14. Links inside your LTI tool open within the constrained iframe, making external content too small to read. Course resources and reference materials are unusable. What should link behavior be?

- **A.** Expand the iframe to full browser width when external content is detected so the user views everything within the same window frame
- **B.** Disable all external links inside the LTI tool and convert referenced resources into embedded content within your platform instead
- **C.** Add a zoom control inside the iframe so students can manually enlarge external content to a readable size when links are clicked
- **D.** Open external links in a new browser tab while your tool stays in the LMS iframe — external resources need full window display  ✅

> **Answer:** D

### Q15. Your OneRoster sync imports demographic fields including race, disability status, and lunch eligibility. Your platform uses none of this data for any educational purpose. What is the privacy concern?

- **A.** Demographic data should be imported for potential future feature development even if not currently used by the platform's live tools
- **B.** Importing demographic data is required by federal reporting mandates regardless of whether the vendor platform directly uses the fields
- **C.** Only sync fields you actually use — importing sensitive data without educational purpose increases compliance burden and breach exposure  ✅
- **D.** Store the imported demographic data in an encrypted secondary database partition with restricted access limited to district admins only

> **Answer:** C

### Q16. Grade passback for 500 students after a district assessment takes 45 minutes processing sequentially. Teachers checking grades during this window see incomplete data. How should throughput improve?

- **A.** Batch or parallel grade submission with a visible sync status indicator so teachers know grades are processing, not permanently missing  ✅
- **B.** Process all grade submissions during an overnight maintenance window so teachers see complete results when they log in the next morning
- **C.** Reduce the assessment to smaller groups of 50 students each so the grade passback processing completes faster per student cohort batch
- **D.** Queue all scores locally and submit them only after the teacher manually confirms the final grades through a review dashboard screen

> **Answer:** A

### Q17. Your LTI integration stores the LMS platform's client secret in a configuration file committed to your Git repository. A developer shares the repo with a contractor. What credential exposure occurred?

- **A.** The contractor's access is covered under their NDA agreement which legally prohibits them from extracting or using discovered secrets
- **B.** Private repositories provide sufficient access control since only authorized team members can view the committed configuration files
- **C.** Rotating the client secret after the contractor's access period ends will neutralize any risk from their temporary repository access
- **D.** The LMS client secret is exposed in version history — credentials must be stored in environment variables or a secrets manager only  ✅

> **Answer:** D

### Q18. A teacher wants to embed a specific quiz from your tool as an individual Canvas assignment, not just launch the tool generically. Your integration only supports basic tool launches. What LTI capability is needed?

- **A.** LTI Deep Linking — lets teachers browse your content catalog and select specific activities to embed as individual LMS assignments  ✅
- **B.** LTI Advantage Names and Roles Provisioning that provides your tool with full course membership data for personalized content selection
- **C.** A custom API endpoint that generates unique embeddable URLs for each content item which teachers then paste into Canvas manually
- **D.** LTI Resource Links that create permanent bookmarks to specific tool pages accessible from the LMS course navigation sidebar menu

> **Answer:** A

### Q19. A school uses Google Classroom which has limited LTI support compared to Canvas. Your tool relies on LTI 1.3 features Google does not fully implement. What is the strategic integration decision?

- **A.** Limit your platform to LMS vendors with full LTI 1.3 compliance and exclude schools using Google Classroom from your target market
- **B.** Wait for Google to improve their LTI implementation and advise interested schools to migrate to Canvas in the interim for full access
- **C.** Build a dedicated Google Classroom integration using their Classroom API alongside your LTI path for maximum market reach coverage  ✅
- **D.** Downgrade your integration to LTI 1.1 which Google Classroom supports more fully even though it lacks modern security features

> **Answer:** C

### Q20. Your roster sync creates user accounts when students enroll but never removes them when students withdraw. A transferred student retains full access six months later. What lifecycle stage is missing?

- **A.** An inactivity timeout that automatically suspends student accounts after 90 days without a login event regardless of enrollment status
- **B.** Deprovisioning — when a student leaves in the SIS, their account must be deactivated and access revoked within the next sync cycle  ✅
- **C.** A teacher-managed removal workflow where educators manually deactivate former students from their class rosters each marking period
- **D.** An annual purge process that deletes all inactive accounts at the end of each school year during the summer maintenance window period

> **Answer:** B

### Q21. Your API returns a 500 error when grade passback encounters a transferred student's invalid ID. The entire batch of 30 remaining grades fails because of one missing student. What error handling is needed?

- **A.** Validate all student IDs against the current roster before initiating the grade passback batch to filter out invalid entries in advance
- **B.** Retry the entire batch submission three times with exponential backoff delays before reporting the failure to the requesting teacher
- **C.** Return the 500 error with detailed diagnostic information so the teacher can identify and manually remove the invalid student entry
- **D.** Skip the invalid student, log the error for review, and continue processing the remaining 29 grades — one failure should not block all  ✅

> **Answer:** D

### Q22. Your platform tracks learning time by counting minutes the browser tab is open. A student walks away for two hours with the tab open. The analytics report shows two hours of active study. What metric is more accurate?

- **A.** Activity-based time tracking that counts only periods with mouse movement, scrolling, clicks, or video playback as genuine engagement  ✅
- **B.** Video watch time tracking that measures only the duration of media playback events and ignores all other types of platform activity
- **C.** Session-based tracking that counts the time between login and logout events with automatic timeout after thirty minutes of inactivity
- **D.** Self-reported study logs where students manually record their actual study time after each learning session for honest accountability

> **Answer:** A

### Q23. A district wants to pilot your tool in five classrooms before district-wide deployment. Your LTI setup makes the tool available to all 500 teachers simultaneously with no scoping controls. What deployment flexibility is missing?

- **A.** A staged rollout plan that communicates to non-pilot teachers that they should not use the tool until the formal evaluation period ends
- **B.** A separate isolated instance of your platform provisioned exclusively for the five pilot classrooms with independent infrastructure
- **C.** Scoped deployment controls — enable the tool for specific courses or teachers during pilot phases before expanding to the full district  ✅
- **D.** An access request workflow where non-pilot teachers can apply for early access which the district administrator approves individually

> **Answer:** C

### Q24. Teachers create interactive lessons in your authoring tool. Content is stored in a proprietary format with no export capability. A district asks about data portability before procurement. What is the adoption risk?

- **A.** Proprietary formats protect your platform's competitive advantage by preventing competitors from replicating your content features
- **B.** Content lock-in — districts require exportable formats so they retain their curriculum investment if they ever change platform vendors  ✅
- **C.** Teachers can manually recreate their lessons on another platform if the district decides to switch so formal export is unnecessary
- **D.** Offering a content migration service at contract end satisfies portability requirements without building permanent export functionality

> **Answer:** B

### Q25. A school district uses Canvas as their LMS. They want your AI-built EdTech tool to launch inside Canvas so teachers and students avoid separate logins. What integration standard enables this?

- **A.** LTI (Learning Tools Interoperability) — the protocol for launching external tools inside an LMS with SSO and course context  ✅
- **B.** OAuth 2.0 authentication flow connecting your platform credentials directly to the Canvas user directory for seamless shared sessions
- **C.** A custom Canvas plugin built specifically for your platform that handles authentication through the Canvas extension API
- **D.** SAML-based federation that synchronizes user identities between your platform and the Canvas authentication provider

> **Answer:** A


---
_Take it in the browser: https://the-faction.mn.co/posts/104111500_
