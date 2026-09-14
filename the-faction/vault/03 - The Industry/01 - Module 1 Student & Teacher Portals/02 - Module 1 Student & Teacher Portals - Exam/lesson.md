---
course: "The Industry"
module: "Module 1: Student & Teacher Portals"
lesson: "Module 1: Student & Teacher Portals — Exam"
type: "course_quiz"
post_id: 104110859
space_id: 24251863
source: "https://the-faction.mn.co/posts/104110859"
updated: "2026-08-10T18:15:42Z"
---

# Module 1: Student & Teacher Portals — Exam

> Exam for **Module 1: Student & Teacher Portals** (The Industry) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. Your AI-built learning platform uses one dashboard for all users. Teachers cannot find their grade book tools among student-facing content. What architectural change resolves this?

- **A.** Role-based view architecture that renders different dashboard layouts based on user type — student, teacher, parent, or admin  ✅
- **B.** A universal search feature with filters for role-specific tools so that all users can locate platform features through keyword queries
- **C.** An onboarding tutorial sequence that walks each user type through the platform features relevant to their daily workflows
- **D.** A customizable widget system that lets individual users drag and arrange dashboard components to match their preferences

> **Answer:** A

### Q2. A student logs in for the first time and sees every platform feature at once — forums, resource libraries, analytics, study groups. They close the tab overwhelmed. What UX principle was violated?

- **A.** Information hierarchy — the platform should rank features by usage frequency and display the most popular ones at the top of the page
- **B.** Progressive disclosure — new users should see only essential features first, with advanced tools revealed as their engagement deepens  ✅
- **C.** Guided onboarding — a mandatory walkthrough should explain every feature before granting the student access to the full dashboard
- **D.** Modular navigation — features should be organized into collapsible sections that students can expand based on their current needs

> **Answer:** B

### Q3. Your platform works perfectly on MacBook development machines. A school deploys it to 300 Chromebooks on shared bandwidth and students report constant loading failures. What's the root cause?

- **A.** The school's IT department should whitelist all platform domains and open the required network ports for full application functionality
- **B.** Chromebook hardware limitations require a dedicated lightweight mobile app version built specifically for Chrome OS devices
- **C.** The platform was never tested on constrained devices and networks — heavy assets and scripts overwhelm shared school bandwidth  ✅
- **D.** Students are likely running too many browser tabs simultaneously, exhausting the Chromebook's limited memory and processing

> **Answer:** C

### Q4. Your platform uses red and green status indicators for assignments. An accessibility audit reveals that 8% of male students may have difficulty distinguishing these colors. What should change?

- **A.** Replace the red-green palette with blue and orange indicators that are more universally distinguishable across color vision types
- **B.** Add a high-contrast accessibility mode that students can enable in their profile settings when they need alternative indicators
- **C.** Display percentage values alongside colored indicators so students have a numeric reference independent of the color system
- **D.** Add icons and text labels alongside all color indicators so status is communicated through multiple channels beyond color alone  ✅

> **Answer:** D

### Q5. A teacher's grade book shows 35 students across 15 assignments. Horizontal scrolling hides student names when viewing later assignments, making grading confusing. What's the interface fix?

- **A.** Freeze the student name column so it stays visible while the teacher scrolls horizontally through the full assignment grid  ✅
- **B.** Implement a pagination system showing five assignments per page so the table never requires any horizontal scrolling at all
- **C.** Add a student search bar above the grade book so the teacher can quickly locate individual students by name when needed
- **D.** Display assignments vertically instead of horizontally so each student row shows all grades in a single scrollable column

> **Answer:** A

### Q6. Course content displays as a flat list of 30 lessons with no grouping, sequencing, or progress indicators. Students cannot tell which unit they belong to. What structure is needed?

- **A.** An alphabetical sort option that lets students organize lessons by title so they can locate specific content more efficiently
- **B.** A calendar integration that maps each lesson to a specific date so students follow a chronological schedule through the course
- **C.** Unit-based grouping with sequential numbering, section headers, and visual progress indicators showing completion by module  ✅
- **D.** A recommendation engine that suggests the next lesson based on the student's prior activity and assessment performance data

> **Answer:** C

### Q7. A parent logs into the portal and sees teacher-level controls including grade editing, roster management, and assignment creation tools. What's the access control failure?

- **A.** The parent account was incorrectly provisioned with teacher-level credentials during the school's bulk account creation import process
- **B.** The parent is seeing the teacher view — parents need a purpose-built read-only portal showing only their linked child's data  ✅
- **C.** The platform lacks separate authentication paths so all users receive the same interface regardless of their assigned role
- **D.** The school administrator forgot to configure role restrictions during initial platform setup for the parent user category

> **Answer:** B

### Q8. On mobile devices, the grade submission button overlaps with the Android system back button position. Teachers accidentally navigate away while trying to submit grades. What UX issue is this?

- **A.** A missing confirmation dialog that should appear before any grade submission to prevent accidental taps and navigation errors
- **B.** A responsive layout problem where button sizing calculations do not account for varying screen dimensions across phone models
- **C.** An insufficient touch target size that causes imprecise tap registration near the edges of interactive UI elements on phones
- **D.** Critical action buttons positioned in device navigation zones — interactive elements must be tested on actual mobile hardware  ✅

> **Answer:** D

### Q9. The dashboard shows assignments due within 24 hours only. A student checking Friday evening sees nothing, missing the assignment due Monday morning. What time window is appropriate?

- **A.** A 7-day lookahead with assignments grouped by date so students can plan their full week of upcoming academic obligations  ✅
- **B.** The complete semester assignment calendar showing every due date from enrollment through finals in chronological sequence
- **C.** A customizable time window that lets students choose their own preferred deadline visibility range in account settings
- **D.** A notification-based system that sends push alerts at 48, 24, and 2 hours before each deadline instead of a dashboard view

> **Answer:** A

### Q10. Half the support tickets are password resets from students who forget their platform credentials. The credential management burden is unsustainable. What authentication approach reduces this?

- **A.** Simpler password requirements that remove complexity rules so students can create shorter and more memorable login credentials
- **B.** A biometric login option using fingerprint or facial recognition on devices that support these hardware authentication methods
- **C.** An automated password recovery flow that sends reset links within seconds so students can regain access without contacting support
- **D.** SSO through the school's existing identity provider so students authenticate with the same credentials they already use daily  ✅

> **Answer:** D

### Q11. Your course page downloads a 45-minute video entirely before playback begins. Students on school networks stare at a 3-minute loading bar before seeing any content. What should the player do?

- **A.** Compress all video files to smaller delivery formats during the upload process so the total download size is reduced for all students
- **B.** Split each lesson into 5-minute segments that download individually so students access the first segment while others queue
- **C.** Stream video progressively so playback starts within seconds while the remaining content buffers ahead of the viewing position  ✅
- **D.** Convert video lessons to audio-only format with synchronized slide decks to dramatically reduce the bandwidth requirements

> **Answer:** C

### Q12. A school administrator needs schoolwide grade distribution analytics but your platform gives them full access to every individual student's detailed records by default. What's the exposure risk?

- **A.** Individual record access is appropriate for administrators since they are responsible for all students within their building
- **B.** Admin dashboards should show aggregate analytics by default with individual student drill-down available only when specifically needed  ✅
- **C.** The platform should restrict administrators to exported summary reports generated monthly rather than real-time data access
- **D.** A separate analytics application should be built specifically for administrators to keep reporting workflows isolated from student records

> **Answer:** B

### Q13. Students upload assignments but receive no confirmation after the upload completes. They upload again out of uncertainty, creating duplicate submissions and grading confusion. What's missing?

- **A.** A clear confirmation state showing the uploaded file name, timestamp, and success indicator so students know their work was received  ✅
- **B.** An automatic email notification sent to both the student and teacher confirming that the assignment file was successfully received
- **C.** A duplicate detection system that identifies when the same file has been uploaded twice and merges the submissions automatically
- **D.** A submission history page accessible from the student profile where all previously uploaded assignments and their statuses appear

> **Answer:** A

### Q14. Grades display as raw percentages only — 87%, 73%, 91%. A parent cannot determine if 73% means their child is struggling or performing above average. What context is missing?

- **A.** A color-coded grading scale that highlights scores in red, yellow, or green based on teacher-defined performance thresholds
- **B.** Letter grade equivalents, class trend context, and performance trajectory indicators that help parents interpret raw numbers  ✅
- **C.** A parent notification system that sends automated alerts when a student's grade drops below the teacher's minimum threshold
- **D.** A comparison chart showing the student's percentages alongside anonymized classmate averages for each graded assignment

> **Answer:** B

### Q15. The Reports section shows 12 options with labels like RPT-AGG-STD-001 and RPT-DTL-GRD-003. A teacher cannot determine which report shows student progress by assignment. What should change?

- **A.** A report search bar that lets teachers filter available reports by entering keywords related to the data they need to find
- **B.** Consolidation of the twelve reports into three simplified options covering grades, attendance, and student engagement metrics
- **C.** A guided report wizard that asks teachers what information they need and automatically selects the correct report to generate
- **D.** Descriptive teacher-friendly report names like 'Student Progress by Assignment' instead of technical codes requiring training  ✅

> **Answer:** D

### Q16. Your platform uses a dark color scheme throughout. A teacher in a brightly lit classroom with overhead fluorescent lighting finds text unreadable on low-brightness school Chromebooks. What should be available?

- **A.** Automatic brightness detection that adjusts the platform's contrast levels based on the ambient light sensor in the device
- **B.** A dedicated high-contrast accessibility mode designed specifically for users with visual impairments in challenging lighting
- **C.** Both light and dark theme options since classroom lighting varies widely and dark themes fail on low-brightness school devices  ✅
- **D.** Platform-wide font size controls that let users increase text size independently of the theme to improve readability in any mode

> **Answer:** C

### Q17. An assignment page shows only the description and due date. No rubric, no connection to learning objectives, and no supporting resources are visible. Students ask the teacher to clarify expectations. What should the page include?

- **A.** The grading rubric, associated learning objectives, and any teacher-attached resources all visible on the assignment page itself  ✅
- **B.** A link to the course syllabus where students can look up the grading criteria and learning objectives for the entire semester
- **C.** An AI-powered assistant that can answer student questions about assignment expectations based on the teacher's configuration
- **D.** A class discussion thread attached to each assignment where students can ask clarifying questions before the submission deadline

> **Answer:** A

### Q18. Students receive 15 platform notifications daily — new grades, discussion replies, course updates, badges earned. They begin ignoring all notifications, missing important deadline alerts. What principle is violated?

- **A.** Notification permissions — students should opt in to each notification category during onboarding rather than receiving all by default
- **B.** Delivery timing — notifications should be batched and sent once daily as a digest rather than individually throughout the day
- **C.** Channel separation — urgent notifications should arrive via text message while non-urgent updates stay within the platform inbox
- **D.** Signal-to-noise ratio — excessive notifications cause fatigue so students ignore everything including critical deadline reminders  ✅

> **Answer:** D

### Q19. A student needs four taps through a hamburger menu to reach their current lesson — the action they perform most frequently every day. What navigation improvement reduces this friction?

- **A.** Place the active course and current lesson directly on the dashboard so the most frequent daily action requires only one tap  ✅
- **B.** Add a persistent bottom navigation bar with quick links to courses, grades, messages, and profile across all platform screens
- **C.** Implement a recent activity section that shows the last five accessed pages so students can quickly return to prior content
- **D.** Create a voice-activated navigation option where students can say the lesson name to jump directly to that content page

> **Answer:** A

### Q20. Creating an assignment requires visiting five separate settings pages for rubric, due date, class selection, plagiarism checking, and late submission policy. Teachers find the workflow fragmented. What's the fix?

- **A.** Pre-built assignment templates with common configurations so teachers select a template instead of setting each option manually
- **B.** An AI assistant that auto-configures assignment settings based on the course type and the teacher's historical preferences
- **C.** A unified assignment creation workflow presenting all configuration options on one page or in a single guided step sequence  ✅
- **D.** A bulk assignment tool that lets teachers create multiple assignments simultaneously and apply shared settings across them all

> **Answer:** C

### Q21. A student's course list mixes current active courses with completed courses from previous semesters. They cannot quickly find their current classes among the historical entries. What's the structural fix?

- **A.** An alphabetical sort option that organizes all courses by title so students can scan the list in a predictable sequence daily
- **B.** Separate active and completed courses into distinct sections with current courses displayed prominently on the dashboard  ✅
- **C.** A semester filter dropdown that lets students select which academic term to display and hides all courses from other periods
- **D.** A pinning feature that lets students manually mark their most important courses to keep them at the top of the full list

> **Answer:** B

### Q22. Attendance tracking offers only Present, Absent, or Tardy options. The school's policy requires distinguishing excused from unexcused absences and tracking early dismissals. What's needed?

- **A.** A free-text notes field where teachers can type additional context about each attendance record to explain special circumstances
- **B.** A separate attendance management system maintained outside the platform that the school district already uses for official records
- **C.** A simplified two-option system showing only Present or Absent since more detailed tracking adds unnecessary complexity for teachers
- **D.** The full district attendance code set — excused, unexcused, tardy, early dismissal, remote — matching official policy requirements  ✅

> **Answer:** D

### Q23. A discussion forum shows all student names publicly on every post. When a teacher creates a reflection about personal challenges, some students refuse to participate because classmates can see their responses. What option should exist?

- **A.** Anonymous-to-peers posting where the teacher sees authorship for accountability but classmates see anonymous contributions only  ✅
- **B.** Private journal entries visible only to the student and teacher as a complete replacement for all class discussion activities
- **C.** Optional participation settings that let students skip sensitive discussion prompts without any grade impact or penalty applied
- **D.** Moderated posting where the teacher reviews and approves each student response before it becomes visible to the rest of the class

> **Answer:** A

### Q24. Interactive platform elements are not keyboard-focusable. A student using an assistive switch device cannot navigate course content or submit assignments. What standard is violated?

- **A.** Universal design principles suggesting that platforms should provide alternative text descriptions for every interactive element
- **B.** Mobile responsiveness standards requiring all interactive elements to support touch input on tablets and smartphone screens
- **C.** Section 508 and WCAG keyboard operability requirements mandating that all interactive elements work via keyboard navigation  ✅
- **D.** Screen reader compatibility guidelines recommending that all platform content includes properly structured heading hierarchy

> **Answer:** C

### Q25. A school requests a platform demo. Your demo environment uses entries like 'Test Student 1' with placeholder grades of 0%. Teachers cannot evaluate how the interface looks with realistic class data. What's better?

- **A.** Use the school's actual student data in the demo so teachers see exactly how their current rosters and grades would appear live
- **B.** Use realistic but fictional demo data with plausible names, varied grades, and real class sizes so teachers evaluate actual usability  ✅
- **C.** Skip the demo environment entirely and offer a free trial pilot period where teachers can populate the platform with their own student records
- **D.** Show a recorded video walkthrough of the platform with narrated screenshots highlighting each feature's functionality in detail

> **Answer:** B


---
_Take it in the browser: https://the-faction.mn.co/posts/104110859_
