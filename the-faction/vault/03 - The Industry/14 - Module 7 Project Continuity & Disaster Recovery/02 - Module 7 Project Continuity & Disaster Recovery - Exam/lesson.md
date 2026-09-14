---
course: "The Industry"
module: "Module 7: Project Continuity & Disaster Recovery"
lesson: "Module 7: Project Continuity & Disaster Recovery — Exam"
type: "course_quiz"
post_id: 104452084
space_id: 24251863
source: "https://the-faction.mn.co/posts/104452084"
updated: "2026-08-10T18:15:43Z"
---

# Module 7: Project Continuity & Disaster Recovery — Exam

> Exam for **Module 7: Project Continuity & Disaster Recovery** (The Industry) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. Your construction platform goes down during a scheduled framing inspection. The inspector cannot access approved plans. The inspection is postponed. What is the cost?

- **A.** Only the hosting fee for the downtime period since the platform service level agreement covers inspection delays
- **B.** A small administrative fee charged by the building department for rescheduling the inspection to a different date
- **C.** The concrete pour scheduled for the next day is delayed, pushing framing and every downstream trade back by days  ✅
- **D.** No significant cost because the inspector can return the following day and the project continues without impact

> **Answer:** C

### Q2. A weather event shuts down your job site for three days. The superintendent documents 'rain delay' with no photos or measurements. Is this sufficient for a dispute?

- **A.** No, contract disputes require GPS-tagged photos, precipitation amounts, temperature, and the shutdown decision record  ✅
- **B.** Yes, the superintendent written note is the standard documentation format for weather delays on construction projects
- **C.** Only if the project owner also signs the weather delay report confirming they agree with the shutdown decision made
- **D.** The weather documentation is irrelevant because construction contracts do not allow time extensions for weather events

> **Answer:** A

### Q3. Your platform runs a database migration during an active 18-month project. The migration corrupts six months of cost data. What should have prevented this?

- **A.** A policy that freezes all database migrations until the project reaches substantial completion and data is archived
- **B.** A manual review of every database record before and after the migration to verify that no values were changed
- **C.** A faster migration script that completes in under one minute to reduce the window where corruption can occur
- **D.** Testing the migration on a staging environment with production-scale data and confirming rollback procedures work  ✅

> **Answer:** D

### Q4. Your backup system completes nightly backups successfully but you have never tested a restore. A server failure occurs. What is the risk?

- **A.** The backups are guaranteed to restore correctly because the backup completion status confirms data integrity fully
- **B.** The backups may be incomplete or corrupted and without tested restores you have no proof the data is recoverable  ✅
- **C.** The hosting provider handles all restores automatically so testing is unnecessary and would only waste team resources
- **D.** A failed restore only affects historical data since the current day entries are still in the application server memory

> **Answer:** B

### Q5. Your platform retains construction records for five years. A lawsuit is filed seven years after project completion. The records have been deleted. What went wrong?

- **A.** Five years is the standard retention period and the company has no legal obligation to retain records beyond that
- **B.** The lawsuit was filed too late and the court will dismiss the case because the statute of limitations has passed
- **C.** Construction records require seven to ten year retention minimum and the five year policy was insufficient for compliance  ✅
- **D.** The deleted records can be reconstructed from other available project documentation such as the original contract and all invoices

> **Answer:** C

### Q6. Your platform schedules maintenance windows on Tuesday mornings. Building inspections are also typically scheduled on Tuesday mornings. What should change?

- **A.** Move maintenance to off-peak hours when inspectors are not active so the platform is available during inspections  ✅
- **B.** Notify inspectors 24 hours before each maintenance window and ask them to reschedule their visits to another day
- **C.** Keep the Tuesday schedule but reduce the maintenance window to 15 minutes to minimize the overlap with inspections
- **D.** Build an offline mode that lets inspectors access the platform during maintenance without any server connectivity

> **Answer:** A

### Q7. A three-year highway project started on Version 1 of your platform. You are now releasing Version 5 with breaking database changes. What must you ensure?

- **A.** The highway project is migrated to Version 5 immediately because all projects must run on the current platform release
- **B.** The highway project remains permanently on Version 1 until completion because mid-project upgrades are too risky
- **C.** The breaking changes are acceptable as long as the release notes document which data fields are affected by the update
- **D.** A tested data migration path preserves all existing project data without corruption or loss when upgrading versions  ✅

> **Answer:** D

### Q8. Your platform has a single database server with no replication. The server hardware fails. How long until the project team can access their data again?

- **A.** Immediately, because modern cloud hosting platforms automatically transfer active sessions to a backup server
- **B.** Hours to days depending on backup age and restore speed since there is no replica to fail over to automatically  ✅
- **C.** The data is permanently lost because without replication there is no second copy of the database anywhere
- **D.** Within minutes because the hosting provider replaces failed hardware and restarts the original database instance

> **Answer:** B

### Q9. A weather delay pushes the foundation pour back two weeks. Your schedule does not recalculate downstream task dates. What feature is missing?

- **A.** A manual notification system that alerts the PM to update each downstream task when a predecessor date changes
- **B.** A weather integration API that automatically predicts the next available pour date based on the forecast conditions
- **C.** Schedule dependency logic that automatically recalculates all downstream dates when a predecessor task is delayed  ✅
- **D.** A buffer period built into every task that absorbs weather delays without affecting the overall project completion date

> **Answer:** C

### Q10. Your point-in-time recovery can restore the database to yesterday. Today cost entries worth $200,000 were entered. The database fails tonight. What is lost?

- **A.** All of today cost entries because the recovery point only reaches yesterday and anything entered today is not backed up  ✅
- **B.** Nothing is lost because point-in-time recovery captures every transaction up to the moment of the failure event
- **C.** Only the entries made in the last hour because the database writes a checkpoint to the backup every sixty minutes
- **D.** The cost entries are preserved in the application server cache and can be replayed into the database after restore

> **Answer:** A

### Q11. Your platform uses a single region for hosting. A regional data center outage takes the platform offline for eight hours during an active inspection period. What would have helped?

- **A.** A longer service level agreement with the hosting provider that guarantees less than one hour of downtime per month
- **B.** A mobile app that caches all the platform data locally so users can continue working during any server outage event
- **C.** A monitoring service that detects the outage within seconds and sends an SMS alert to the project team immediately
- **D.** Cross-region replication that automatically fails over to a secondary region when the primary data center goes down  ✅

> **Answer:** D

### Q12. Your disaster recovery plan exists as a document but has never been practiced. A real disaster occurs and the team cannot execute the recovery steps. What was missing?

- **A.** A more detailed written plan with step-by-step screenshots that would have been clear enough to follow under pressure
- **B.** Regular disaster recovery drills that test the plan under realistic conditions so the team knows the process works  ✅
- **C.** An automated recovery system that executes the plan without human intervention so the team skills are not needed
- **D.** A third-party disaster recovery vendor on retainer who handles all recovery operations when the team is unavailable

> **Answer:** B

### Q13. A public infrastructure project requires permanent record retention. Your platform auto-deletes records after ten years. What must change?

- **A.** The ten-year policy is sufficient for all project types and public infrastructure projects have no special requirements
- **B.** The platform should extend the retention period to twenty years which covers the longest possible requirement
- **C.** Public project records should be exported to government systems and the platform can proceed with its standard policy
- **D.** The retention policy must support project-type overrides so public projects can be set to permanent retention individually  ✅

> **Answer:** D

### Q14. Your weather documentation captures rain but not temperature, wind speed, or the superintendent decision to shut down. Why does this matter for disputes?

- **A.** Incomplete weather records weaken the contractor claim because the opposing party can argue conditions were workable  ✅
- **B.** Temperature and wind speed are only relevant for concrete work and do not affect general construction delay claims
- **C.** The superintendent shutdown decision is implicit in the delay record and does not need to be documented separately
- **D.** Weather disputes are resolved by the National Weather Service historical data and site-level records are not required

> **Answer:** A

### Q15. Your platform updates break a critical reporting feature during a month-end billing cycle. The PM cannot generate pay applications. What deployment practice should prevent this?

- **A.** Delay all platform updates until after the project reaches final completion so no active work is disrupted by changes
- **B.** Notify all project managers 48 hours before each update and let them export critical data as a precautionary measure
- **C.** Deploy updates to a staging environment first and verify that all critical workflows including billing function correctly  ✅
- **D.** Implement a feature flag system that lets PMs individually disable new features and roll back to the previous version

> **Answer:** C

### Q16. Your recovery time objective is four hours. After a failure, restoring from backup takes twelve hours. What does this gap mean?

- **A.** The four-hour objective was unrealistic and should be revised to match the actual twelve-hour recovery performance
- **B.** The backup infrastructure needs improvement such as faster storage, smaller backup sets, or a warm standby replica  ✅
- **C.** The twelve-hour restore only needs to happen once and future failures will restore faster because the system is warmed up
- **D.** The recovery time objective only applies to business-critical data and non-essential records can take twelve hours

> **Answer:** B

### Q17. Your schedule recalculation moves the completion date forward by two weeks after a delay is entered. The contract has liquidated damages for late delivery. What should the platform document?

- **A.** The original completion date only since the contract liquidated damages are calculated from the original deadline alone
- **B.** The number of calendar days lost to the delay so the contractor can calculate the liquidated damages amount owed
- **C.** A formal request to the owner for a time extension that must be approved before the completion date is officially moved
- **D.** The cause of the delay with supporting evidence because excusable delays like weather may qualify for time extensions  ✅

> **Answer:** D

### Q18. Your platform has been running for three years. The original team that built the disaster recovery plan has left. No one on the current team has been trained. What is the risk?

- **A.** When a disaster occurs the current team cannot execute the recovery plan effectively because they have never practiced it  ✅
- **B.** The disaster recovery plan automatically adjusts to organizational changes so team member turnover is not a concern
- **C.** The hosting provider handles the execution of disaster recovery plans on behalf of the customer so internal training is optional
- **D.** The original team documented the plan thoroughly enough that any technical person can follow the steps without training

> **Answer:** A

### Q19. Your platform archives completed projects to cold storage. A warranty claim requires accessing daily reports from three years ago. What performance should users expect?

- **A.** The same instant access speed as active projects because archival should not affect the query response time at all
- **B.** The records are unavailable because cold storage is write-only and archived data cannot be retrieved after the transfer
- **C.** Slower retrieval times compared to active data but the records must still be accessible and complete when returned  ✅
- **D.** The archived data must first be fully restored to active storage before any individual records can be queried or viewed

> **Answer:** C

### Q20. Your uptime monitoring only checks whether the platform homepage loads. The API that serves project data is down but the homepage still works. What should monitoring cover?

- **A.** Only the homepage because if the main page loads then all backend services are confirmed to be running correctly
- **B.** Critical API endpoints, database connectivity, document storage, and authentication services beyond just the homepage  ✅
- **C.** Every individual page and feature on the platform to ensure one hundred percent coverage of all possible failure points
- **D.** Only the login page because if users can authenticate then all services behind the authentication layer must be working

> **Answer:** B

### Q21. A tropical storm warning is issued for your job site region. How should the platform help the superintendent prepare?

- **A.** Surface the weather alert, prompt documentation of current site conditions, and enable schedule delay entry for the event  ✅
- **B.** Automatically shut down all job site access on the platform and prevent any data entry until the weather event passes
- **C.** Send a notification to the project owner that the project will be delayed and calculate the estimated cost impact now
- **D.** The platform should not respond to weather events because weather management is outside the scope of construction tech

> **Answer:** A

### Q22. Your database replication has a five-minute lag. A failure occurs and you fail over to the replica. What data is potentially missing?

- **A.** All data entered in the last 24 hours because replication lag compounds over time and the gap grows with each cycle
- **B.** No data is missing because replication lag only affects the display speed and all transactions are eventually replicated
- **C.** Only read-only query results are affected because all write operations are committed to both primary and replica instantly
- **D.** Up to five minutes of the most recent transactions because the replica had not yet received those writes before failover  ✅

> **Answer:** D

### Q23. Your platform has strong availability and recovery but no capacity planning. A large project doubles the active user count overnight. What happens?

- **A.** The platform automatically scales to handle the increased load because modern cloud hosting adjusts resources in real time
- **B.** Only the new users experience slowdowns because the platform prioritizes existing users with established session data
- **C.** The platform may experience degraded performance or outages because the infrastructure was not sized for the load  ✅
- **D.** The database handles the load fine but the application server queues requests which adds a consistent two second delay

> **Answer:** C

### Q24. You complete your project continuity and disaster recovery audit. All systems pass. What ongoing practice keeps the platform resilient as conditions change?

- **A.** Only when a failure occurs should the team review and update the disaster recovery plan based on the actual incident
- **B.** Regular backup testing, DR drills, uptime monitoring review, and capacity planning updates as the platform grows  ✅
- **C.** Annual infrastructure renewal where all servers and databases are replaced with the latest hardware and software
- **D.** No ongoing practice is needed because a passing audit confirms the disaster recovery architecture is permanently sound

> **Answer:** B

### Q25. You complete all seven T5 Construction modules. What is the ongoing practice that keeps your construction platform reliable across multi-year projects?

- **A.** Continuous monitoring, regular testing, and proactive maintenance because construction projects outlast any single configuration  ✅
- **B.** A one-time comprehensive configuration audit at project start because construction requirements do not change mid-project
- **C.** Full reliance on the hosting provider managed services because they handle all availability and recovery automatically
- **D.** Annual reviews only because construction technology platforms are stable enough to run for twelve months between audits

> **Answer:** A


---
_Take it in the browser: https://the-faction.mn.co/posts/104452084_
