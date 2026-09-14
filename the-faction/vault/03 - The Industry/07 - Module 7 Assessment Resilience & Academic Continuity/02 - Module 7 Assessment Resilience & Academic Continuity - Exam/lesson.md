---
course: "The Industry"
module: "Module 7: Assessment Resilience & Academic Continuity"
lesson: "Module 7: Assessment Resilience & Academic Continuity — Exam"
type: "course_quiz"
post_id: 104112558
space_id: 24251863
source: "https://the-faction.mn.co/posts/104112558"
updated: "2026-08-10T18:15:42Z"
---

# Module 7: Assessment Resilience & Academic Continuity — Exam

> Exam for **Module 7: Assessment Resilience & Academic Continuity** (The Industry) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. Your engineering team plans to deploy a major platform update on Monday at 2pm. The district is in the middle of state-mandated standardized testing that entire week. What should change about the deployment schedule?

- **A.** Freeze all deployments during testing windows — state assessment periods carry the highest uptime requirement in educational technology  ✅
- **B.** Deploy the update after school hours at 6pm instead of 2pm so students have finished their testing sessions before any changes take effect
- **C.** Proceed with the deployment but have a rollback plan ready in case the update causes issues during the standardized testing sessions
- **D.** Deploy only frontend cosmetic changes and defer backend updates until after the testing window closes to minimize the risk of disruption

> **Answer:** A

### Q2. A teacher needs to submit final grades by 5pm Friday. Your platform shows a loading spinner starting at 3pm due to a server issue. The teacher cannot finalize grades before the deadline. What infrastructure should have prevented this?

- **A.** A manual grade submission fallback that lets teachers email their final grades to an administrator who enters them into the system later
- **B.** High-availability architecture during grade deadlines — the platform must know critical academic dates and ensure maximum uptime for them  ✅
- **C.** Extended deadline flexibility that automatically pushes the submission window back by the duration of any platform outage that occurred
- **D.** A local grade book application that teachers install on their computers so they can work offline and sync grades when the platform recovers

> **Answer:** B

### Q3. Your database backup runs nightly. At 2pm a bug corrupts the entire grade table. You restore last night's backup and lose six hours of teacher grading across 50 classrooms. What backup strategy was needed?

- **A.** Increase backup frequency from nightly to every two hours which would reduce the maximum potential data loss window from 24 to 2 hours
- **B.** Real-time database replication to a standby server that maintains an identical live copy and can take over instantly during corruption events
- **C.** Point-in-time recovery — restore the database to any specific minute before the corruption so at most seconds of grade data are ever lost  ✅
- **D.** Transaction-level logging that records every individual database write so corrupted records can be identified and reversed one at a time

> **Answer:** C

### Q4. Your team accidentally runs a practice year-end rollover on production in January instead of staging. All courses reset, current grades are archived, and 200 teachers lose access to their mid-year grade books. What process was violated?

- **A.** A confirmation dialog requiring administrators to type a verification phrase before executing the year-end rollover process on any system
- **B.** Role-based access controls that restrict the year-end rollover function to a single designated super-administrator account in the platform
- **C.** Calendar-based lockout that prevents the rollover function from executing outside of the designated June-August year-end processing window
- **D.** Year-end processes must be tested on staging first with production-like data — never run destructive lifecycle operations on production directly  ✅

> **Answer:** D

### Q5. A snowstorm forces an entire district to go remote overnight. Your platform normally handles 2,000 concurrent users. By 8am the next morning, 15,000 students and teachers try to log in and the platform crashes. What was missing?

- **A.** Emergency scaling capacity — the platform must handle sudden 5-10x traffic spikes when districts shift to remote learning with zero notice  ✅
- **B.** A pre-configured remote learning mode reduces platform features to essential-only functionality to lower the per-user resource demand
- **C.** A district-level staggered login schedule that spreads student access across 30-minute windows to prevent simultaneous login surge overload
- **D.** Advance weather monitoring integration that detects incoming storms and automatically pre-provisions additional server capacity in response

> **Answer:** A

### Q6. Your uptime monitoring checks whether the homepage loads. The homepage shows 100% uptime but the assessment engine is completely down. Students cannot take exams while monitoring reports everything is fine. What is the monitoring gap?

- **A.** Add a separate uptime monitoring check for every individual page and feature endpoint across the entire platform to ensure full visibility
- **B.** Rely on user-reported issues as the primary indicator of feature-level outages since automated monitoring cannot test every possible workflow
- **C.** Monitor critical user flows — assessment submission, grade saving, and login must each have their own health checks beyond just the homepage  ✅
- **D.** Deploy an internal testing bot that continuously takes practice assessments and submits grades to verify end-to-end platform functionality

> **Answer:** C

### Q7. Your load test simulates 1,000 concurrent users and passes. During state testing, 5,000 students hit the assessment engine simultaneously. The database connection pool exhausts and assessments fail. What was the testing gap?

- **A.** Load testing with 1,000 users is sufficient for most platforms and the state testing surge was an unpredictable anomaly
- **B.** Load test at expected peak capacity of 5-10x normal traffic — state testing creates concentrated bursts far exceeding daily average usage  ✅
- **C.** Database connection pool size should be set to unlimited so any number of concurrent users can establish database connections simultaneously
- **D.** Implement a request queue that holds excess assessment submissions in memory until database connections become available during peak periods

> **Answer:** B

### Q8. A database migration runs during a Saturday maintenance window. It takes 6 hours instead of the estimated 2. The platform is still down when a Sunday study group tries to access course materials. What should the process include?

- **A.** Schedule all maintenance windows for a minimum of 12 hours to ensure adequate time for any migration regardless of unexpected complications
- **B.** Communicate to all users that the platform may be unavailable for the entire weekend during any scheduled Saturday maintenance window event
- **C.** Run all database migrations during winter or summer break periods when no students or teachers need access to the platform for any purpose
- **D.** Time buffers, tested rollback plans, and user communication about extended windows — plus zero-downtime migration techniques when possible  ✅

> **Answer:** D

### Q9. Your incident communication plan says to post updates on the status page. The status page is hosted on the same infrastructure as the application. When the platform goes down, the status page goes down too. What is wrong?

- **A.** Host the status page on independent infrastructure — if your platform is down, schools must still be able to access outage information online  ✅
- **B.** Use social media accounts as the primary incident communication channel since those platforms have independent uptime and broad audience reach
- **C.** Send mass email notifications to all registered users when an outage occurs so they receive updates regardless of platform availability status
- **D.** Establish a dedicated phone hotline that school IT administrators can call during outages to receive live status updates from your support team

> **Answer:** A

### Q10. Your platform stores all data in a single AWS region. A regional outage takes the entire region offline for four hours during a school day. All student data and assessments are unavailable. What architecture prevents this?

- **A.** Maintain a cold backup in a second AWS region that can be manually activated within four hours if the primary region experiences an outage
- **B.** Switch to a multi-cloud strategy distributing infrastructure across AWS, Azure, and Google Cloud to eliminate single-provider dependency risk
- **C.** Accept single-region risk as an industry standard tradeoff and purchase the highest-tier AWS support plan for fastest incident resolution times
- **D.** Multi-region data replication with automatic failover — if one region goes down, another region serves traffic with no visible interruption  ✅

> **Answer:** D

### Q11. A student is halfway through a 60-question standardized assessment when their browser crashes. They reopen the browser and all progress is gone. They must restart the entire assessment from question one. What should the assessment engine support?

- **A.** A browser stability check before the assessment begins that verifies the student's device meets minimum requirements for uninterrupted testing
- **B.** Offline assessment mode that downloads all questions to the device before starting so browser crashes do not lose any submitted answer data
- **C.** Auto-save and session recovery — assessment progress saved continuously so students resume from their last answered question after any crash  ✅
- **D.** A proctor override that lets the teacher manually restore the student's progress to the approximate question they reached before the crash

> **Answer:** C

### Q12. Your SLA promises 99.9% uptime. Your actual downtime last year was 12 hours, mostly during assessment windows and grade deadlines. The district says the timing matters more than the total. What is the real issue?

- **A.** Negotiate a lower SLA target of 99.5% for the next contract period to create a more achievable uptime commitment for your infrastructure team
- **B.** Aggregate uptime is not enough — downtime during assessments and grade deadlines has outsized impact and needs weighted SLA commitments  ✅
- **C.** Offer service credits for each hour of downtime to financially compensate the district for the operational impact of unplanned outages
- **D.** Invest in infrastructure improvements to achieve 99.99% uptime across all periods which would reduce total downtime to under one hour annually

> **Answer:** B

### Q13. Your on-call rotation has one engineer covering nights and weekends. During a Sunday evening assessment period, that engineer is unreachable. A database issue goes unresolved for three hours. What should be different?

- **A.** Primary and secondary on-call responders with guaranteed response times during known testing windows to ensure incident coverage redundancy  ✅
- **B.** An automated incident response system that can diagnose and resolve common database issues without requiring human engineer intervention
- **C.** Restrict all assessment scheduling to weekday business hours when the full engineering team is available and reachable for support coverage
- **D.** A managed database service with vendor-provided 24/7 monitoring that handles incident response so your team does not need weekend on-call

> **Answer:** A

### Q14. The school year ends in June. Your team runs 15 manual SQL scripts to advance students, archive courses, and create fall sections. Script 8 fails and corrupts student advancement data. What should the process be?

- **A.** Add error handling and rollback logic to each individual SQL script so failures in any single step are contained and reversed automatically
- **B.** An automated year-end pipeline — scripted, tested on staging, with rollback capability and verification checks between each processing stage  ✅
- **C.** Assign three engineers to run the scripts simultaneously in parallel sessions to complete the year-end process faster and reduce the error window
- **D.** Convert the SQL scripts to stored procedures executed within the database server which provides better transaction management and error handling

> **Answer:** B

### Q15. Your disaster recovery plan was written two years ago. It references infrastructure components that no longer exist and team members who have left. Nobody has tested the plan. A disaster occurs and the team cannot follow it. What should have happened?

- **A.** Maintain the existing plan as a general framework and improvise the specific technical steps during an actual disaster based on current systems
- **B.** Assign a single engineer to update the plan quarterly by reviewing the document and correcting any outdated references they identify on paper
- **C.** Replace the written plan with an automated disaster recovery system that executes predefined recovery procedures without human decision-making
- **D.** Review and test DR plans regularly — at least annually with updated infrastructure references, current contacts, and simulated recovery drills  ✅

> **Answer:** D

### Q16. Your platform runs on a single database server with no replicas. The server's disk fails. Recovery requires restoring from backup to a new server which takes an estimated six hours. What architecture prevents this downtime?

- **A.** Use RAID disk arrays on the database server to provide hardware-level redundancy so a single disk failure does not take the server offline
- **B.** Maintain a hot spare server with matching hardware configuration that can be manually provisioned and loaded with the latest backup in 2 hours
- **C.** Database replication with automatic failover — a standby replica takes over in seconds when the primary fails with no multi-hour recovery gap  ✅
- **D.** Store the database on network-attached storage with built-in redundancy so disk failures are handled transparently by the storage infrastructure

> **Answer:** C

### Q17. A student submits their assessment at 2:59pm. The deadline is 3:00pm. Your server clock is two minutes fast and the system rejects the submission as late, affecting the student's grade. What should be in place?

- **A.** NTP-synchronized server time and a brief grace period on assessment deadlines to account for network latency and minor clock variations  ✅
- **B.** Use the student's device clock as the authoritative timestamp for submission rather than the server clock to avoid server-side discrepancies
- **C.** Display a countdown timer synchronized with the server clock so students can see exactly how much time remains before the deadline closes
- **D.** Allow teachers to manually override late submission flags when students report that their submission was rejected due to clock discrepancies

> **Answer:** A

### Q18. Monitoring alerts fire 50 times per day for minor issues. The on-call engineer starts ignoring all alerts. A real database failure alert goes unnoticed for 45 minutes during an assessment window. What is the monitoring problem?

- **A.** Hire a dedicated monitoring analyst whose sole responsibility is reviewing every alert and escalating genuine incidents to the engineering team
- **B.** Reduce the total number of monitoring checks to only the five most critical system components to eliminate all non-essential alert noise
- **C.** Route all alerts through a ticketing system that requires the on-call engineer to acknowledge each one before it can be marked as resolved
- **D.** Alert fatigue — reduce noisy alerts, set proper severity thresholds, and tier alerts so critical incidents stand out from routine background noise  ✅

> **Answer:** D

### Q19. A 3-hour maintenance window is communicated only to district IT contacts via email. Teachers are not notified. During maintenance, 40 teachers cannot access the grade book on a grading deadline day. What is the communication gap?

- **A.** Maintenance communications must reach end users — teachers and administrators — not just IT contacts, especially near academic deadlines  ✅
- **B.** IT contacts are responsible for forwarding maintenance notifications to their school staff so the communication chain is the district's duty
- **C.** Post maintenance schedules on the platform's status page and expect teachers to check it regularly before planning any grade entry sessions
- **D.** Schedule all maintenance during overnight hours between 11pm and 5am when no teachers or students are expected to use the platform actively

> **Answer:** A

### Q20. Your assessment engine has no submission rate limiting. During a 500-student exam, all submissions hit the grading API simultaneously. The API backs up and students wait 10 minutes for results. What is needed?

- **A.** Increase the grading API server capacity permanently to handle the maximum possible concurrent submission volume at any given moment
- **B.** Delay all grade processing until after the exam window closes and batch-process all submissions overnight for next-morning result delivery
- **C.** A submission queue with estimated wait times shown to students — process submissions in order instead of overloading the API with all at once  ✅
- **D.** Distribute the exam start times across 30-minute windows so submissions are naturally staggered and do not arrive at the API simultaneously

> **Answer:** C

### Q21. Your platform has no academic calendar integration. The engineering team schedules a database migration for the same week as the district's state assessment window. Nobody caught the conflict until testing began. What integration is needed?

- **A.** A manual coordination process where the engineering team emails each district before scheduling any maintenance to check for calendar conflicts
- **B.** Academic calendar integration in the deployment pipeline — critical school dates should automatically block maintenance scheduling system-wide  ✅
- **C.** A shared Google Calendar between the engineering team and district administrators where both parties manually enter their important scheduled dates
- **D.** Quarterly planning meetings between engineering and district contacts to align maintenance windows with academic schedules for the upcoming period

> **Answer:** B

### Q22. A student's assessment submission is accepted by the server but the confirmation message fails to display. The student does not know their work was saved and submits again, creating a duplicate entry. What should happen?

- **A.** Disable the submit button immediately after the first click so students cannot physically click it a second time regardless of confirmation
- **B.** Send an automated email confirmation to the student for every successful submission so they have an external record of their completed work
- **C.** Display a submission history page that students can check at any time to verify whether their assessment was successfully recorded on file
- **D.** Detect and prevent duplicate submissions automatically — show persistent confirmation status and deduplicate identical submissions on arrival  ✅

> **Answer:** D

### Q23. Your team restores from a database backup after a failure. Everything appears normal until a teacher reports that 200 grade entries from the past hour are missing. The backup did not include the most recent data. What verification was skipped?

- **A.** Post-restore verification — compare restored data against recent activity logs to identify and recover any data gaps before declaring complete  ✅
- **B.** An automated integrity check that compares row counts between the restored database and the backup file to confirm all records were transferred
- **C.** Teacher notification requesting that all staff verify their most recent grade entries are present and report any missing data within 24 hours
- **D.** A parallel restore to a secondary environment where the team can query both databases and compare specific records before switching traffic

> **Answer:** A

### Q24. Your health check endpoint returns 200 OK as long as the web server is running. The web server is up but the database connection is broken. The load balancer routes traffic to this broken instance. What is wrong with the health check?

- **A.** The load balancer should use TCP connection checks instead of HTTP health checks to verify that the server is accepting network connections
- **B.** Add a separate dedicated health check endpoint for the database that the load balancer queries independently from the web server health check
- **C.** Health checks must verify end-to-end functionality — database connectivity, cache availability, and critical dependencies, not just web server status  ✅
- **D.** Configure the web server to automatically restart when it detects a broken database connection so the health check failure triggers self-healing

> **Answer:** C

### Q25. Your recovery time objective is four hours. A school district's assessment window requires platform availability within 30 minutes of any failure. The 3.5-hour gap between your RTO and their requirement is unacceptable. What needs to change?

- **A.** Negotiate with the district to accept a four-hour RTO as a reasonable standard for educational technology platforms during assessment periods
- **B.** Align your RTO with customer requirements — assessment-critical platforms need sub-hour recovery via hot standby, not backup restoration  ✅
- **C.** Purchase a premium support tier from your cloud provider that guarantees infrastructure recovery within 30 minutes of any reported failure
- **D.** Implement a read-only failover mode that provides assessment access within 30 minutes while full platform recovery continues in the background

> **Answer:** B


---
_Take it in the browser: https://the-faction.mn.co/posts/104112558_
