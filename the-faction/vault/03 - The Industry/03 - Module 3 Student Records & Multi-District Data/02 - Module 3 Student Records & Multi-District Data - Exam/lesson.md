---
course: "The Industry"
module: "Module 3: Student Records & Multi-District Data"
lesson: "Module 3: Student Records & Multi-District Data — Exam"
type: "course_quiz"
post_id: 104111712
space_id: 24251863
source: "https://the-faction.mn.co/posts/104111712"
updated: "2026-08-10T18:15:42Z"
---

# Module 3: Student Records & Multi-District Data — Exam

> Exam for **Module 3: Student Records & Multi-District Data** (The Industry) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. Your AI tool created a student data table with name, email, and grade columns. The school requires enrollment status, demographics, IEP flags, and guardian contacts. What's the schema gap?

- **A.** Student records need enrollment status, demographics, IEP/504 flags, guardian contacts, and grade level beyond basic user fields  ✅
- **B.** The existing table should be extended with a flexible JSON column where schools can store any additional fields they require
- **C.** A separate supplemental profile table linked by student ID should hold the extended fields while keeping the core table simple
- **D.** The school should maintain demographic and accommodation data in their own SIS system rather than duplicating it in your platform

> **Answer:** A

### Q2. Your platform serves three school districts. A District A administrator runs a report and sees students from District B in the results. What is the root cause of this data exposure?

- **A.** The report query is missing a district filter parameter that the administrator should have selected before generating the output
- **B.** Missing district-level Row-Level Security — database policies must prevent any query from returning cross-district student records  ✅
- **C.** The administrator's account was provisioned with a super-admin role that intentionally grants visibility across all district data
- **D.** The report template was designed for single-district use and needs to be reconfigured for the multi-district deployment scenario

> **Answer:** B

### Q3. Your grade book stores a single number per student per course. A teacher needs weighted categories — 40% exams, 30% homework, 30% projects — with dropped lowest scores. What schema change supports this?

- **A.** Add a formula field to the existing grade column that lets teachers define custom weighting calculations per student per course
- **B.** Create a spreadsheet export feature so teachers can perform weighted calculations externally and import the final grades back
- **C.** A relational grade book schema with assignment categories, per-category weights, individual scores, and configurable drop rules  ✅
- **D.** Provide a grading calculator widget on the teacher dashboard that computes weighted averages from the single stored grade values

> **Answer:** C

### Q4. A student transfers from School A to School B within the same district. Your database creates a duplicate student record at School B. Their School A grades don't appear in the School B view. What caused this?

- **A.** The roster sync correctly created a new enrollment record but the grade migration job has not yet been triggered by the system
- **B.** School B's administrator needs to manually initiate a data transfer request to pull the student's historical records from School A
- **C.** The two schools use different student ID formats which prevents the system from recognizing that both records are the same person
- **D.** Students should have one record with enrollment history — transfers update the enrollment association, not create new student records  ✅

> **Answer:** D

### Q5. Your database backup runs nightly at midnight. At 3pm, a bug corrupts the grade table. You restore the midnight backup and lose 15 hours of teacher grading work. What backup strategy prevents this?

- **A.** Point-in-time recovery that lets you restore the database to any specific minute — losing seconds of data instead of full hours  ✅
- **B.** Hourly incremental backups that capture only the changes since the previous backup reducing the maximum data loss to 60 minutes
- **C.** Real-time database replication to a secondary server that maintains an identical copy for immediate failover during corruption events
- **D.** Transaction logging that records every database write operation so individual corrupted records can be manually reversed one by one

> **Answer:** A

### Q6. Your schema has no concept of academic terms. Fall 2026 Biology and Spring 2027 Biology share the same course record. When Spring grades post, Fall grades are overwritten. What's missing?

- **A.** A manual archive process where teachers export their grade data at the end of each term before the next term's data begins entry
- **B.** A versioning system on the course record which specifically creates a snapshot each time a new term begins preserving the previous term's state
- **C.** Term-aware course sections — each term creates a new section with its own students, grades, and dates while preserving prior terms  ✅
- **D.** A separate historical grades database that receives completed term data through an automated end-of-semester transfer job nightly

> **Answer:** C

### Q7. A graduated student's records need to appear on their official transcript five years later. Your system deleted their data during a routine inactive account purge. What retention policy was needed?

- **A.** Extend the inactive account purge threshold from one year to ten years so graduated student data survives longer before deletion
- **B.** Transcript data must be archived permanently per retention policy — graduated records should be moved to archives, never deleted  ✅
- **C.** Generate PDF transcript snapshots at graduation and store them as static files since the underlying data is no longer needed live
- **D.** Transfer all graduated student records to the school district's own archival system and remove them from your platform entirely

> **Answer:** B

### Q8. Your multi-district database has no index on the district_id column. As the platform grows to 50 districts with 200,000 students, every per-district query runs slowly. What's the database optimization?

- **A.** Partition the database into separate physical schemas — one schema per district — so each district queries only their own partition
- **B.** Implement query caching that stores frequently accessed district report results and serves them from memory instead of the database
- **C.** Upgrade the database server hardware with more memory and faster processors to handle the increased query volume across all districts
- **D.** Add composite indexes on district_id and commonly filtered columns so per-district queries avoid scanning the entire student table  ✅

> **Answer:** D

### Q9. Your student table stores IEP status, disability type, and accommodation details in columns visible to every teacher in the school. A gym teacher can see learning disability details. What access control is missing?

- **A.** Field-level access controls on sensitive student data — only authorized staff like special education coordinators should see IEP details  ✅
- **B.** A training requirement that ensures all teachers understand they should not access or use IEP information outside their direct duties
- **C.** Moving all IEP and disability data to a separate standalone system that only special education staff can access through a different login
- **D.** Data masking that replaces sensitive field values with asterisks when displayed to users who do not have an explicit authorization flag

> **Answer:** A

### Q10. Guardian contacts are stored as a single parent_name and parent_email field on the student table. A student has divorced parents who both need access plus a grandparent with legal guardianship. What's the limitation?

- **A.** Add parent2_name and parent2_email fields to the student table to accommodate the second parent and use notes for the grandparent
- **B.** Store all guardian contact information in a comma-separated text field that can hold an unlimited number of names and email addresses
- **C.** Create a family_contacts JSON column on the student record that stores an array of guardian objects with flexible field structures
- **D.** A separate guardians table linked to students — supporting multiple guardians with different relationships, access rights, and contacts  ✅

> **Answer:** D

### Q11. A teacher creates a custom assignment category called Participation worth 10% of the grade. Your system only supports default categories — Homework, Exams, Projects. The grade book is too rigid. What's needed?

- **A.** Add Participation to the default category list as a permanent option available to all teachers across every course in the platform
- **B.** Allow teachers to rename the existing default categories ensuring that they can relabel Projects as Participation for their specific course usage
- **C.** Teacher-configurable assignment categories — let teachers create, name, and weight their own categories instead of forcing a fixed set  ✅
- **D.** Provide a supplemental grading spreadsheet that teachers can attach to their course for any calculations beyond the default categories

> **Answer:** C

### Q12. A database migration renames the grade_level column to year_group for international schools. The deployment runs during school hours and breaks every query referencing the old column name. What should have happened?

- **A.** Schedule all destructive migrations during a weekend maintenance window and notify all users of expected downtime before the change
- **B.** Use the expand-migrate-contract pattern — add the new column, update queries to use both, migrate data, then remove the old column  ✅
- **C.** Create a database view that aliases the old column name to the new one so existing queries continue working without any code changes
- **D.** Run the migration in a single transaction with an automatic rollback trigger if any application errors are detected within 60 seconds

> **Answer:** B

### Q13. Your state reporting module counts Hispanic students. The query returns zero because the SIS sync mapped ethnicity codes differently than your schema expects. What caused the reporting error?

- **A.** Mismatched data mapping between SIS ethnicity codes and your schema — import mappings must be validated against expected enumerations  ✅
- **B.** The SIS vendor changed their ethnicity code format in a recent update without notifying your platform about the new field structure
- **C.** State reporting queries should pull demographic data directly from the SIS rather than from your platform's local copy of the records
- **D.** The enrollment import excluded demographic fields due to a data minimization filter that was incorrectly applied during roster sync

> **Answer:** A

### Q14. Your data export for state reporting includes every field in the student table — internal system IDs, hash values, metadata — alongside the 12 fields the state actually requires. What's the data handling problem?

- **A.** The state reporting office can filter the exported columns on their end so including extra fields provides flexibility without harm
- **B.** Exports should include only the required fields — sending internal system data violates data minimization and may expose sensitive values  ✅
- **C.** Adding a column selection interface to the export tool would let administrators choose which fields to include in each export manually
- **D.** Internal system IDs in exports actually help the state match records across submissions so they should be included for interoperability

> **Answer:** B

### Q15. Two teachers teach the same course with different grading scales. Teacher A uses 90/80/70/60 letter boundaries. Teacher B uses 93/85/77/70. Your system has one global scale. What configuration is needed?

- **A.** Standardize on one grading scale across the entire school district to eliminate confusion between different teachers' letter grades
- **B.** Let teachers manually override calculated letter grades on individual student records when the global scale produces incorrect results
- **C.** Create named grading scale presets at the school level that teachers select from a dropdown when setting up each course section
- **D.** Per-teacher or per-section grading scale configuration so each teacher defines their own letter grade boundaries for their classes  ✅

> **Answer:** D

### Q16. Your schema tracks attendance at the student-per-day level only. A student attends Period 1 but is absent for Period 4. Your record shows them as present for the entire day. What granularity is missing?

- **A.** Add a notes field to the daily attendance record where teachers can document partial absences and the specific periods affected
- **B.** Track only full-day absences since period-level tracking creates excessive data volume and adds complexity to the attendance workflow
- **C.** Period-level attendance tracking — record student presence per class period, not just per day, to support secondary school schedules  ✅
- **D.** Let teachers submit separate attendance records for each of their classes which are then aggregated into a daily summary for parents

> **Answer:** C

### Q17. Your test database has 1 district, 1 school, and 20 students. Everything works. In production with 50 districts and 200K students, reports take 30 seconds. What testing gap caused this?

- **A.** Seed test databases with production-scale data across multiple districts — realistic data volumes reveal performance issues that toy data hides  ✅
- **B.** Run automated performance benchmarks on the test database after every code change to detect query regressions before they reach production
- **C.** Use database query profiling tools in production to identify the specific slow queries and optimize them after the performance issue surfaces
- **D.** Implement query result caching for report data so that repeated queries return cached results instead of executing against the full dataset

> **Answer:** A

### Q18. A counselor needs a student's complete academic history — every course, every grade, every year. Your database only stores current-year data because previous years were deleted during cleanup. What should year-end processing do?

- **A.** Export completed year data as PDF transcript documents before deletion so counselors can reference the static files when history is needed by staff
- **B.** Maintain a rolling three-year retention window that keeps the most recent academic history while deleting records older than 36 months
- **C.** Transfer historical data to a separate long-term storage database that counselors can query through a different administrative interface
- **D.** Archive previous years to a historical data store without deleting them — counselors, transcripts, and reporting require multi-year access  ✅

> **Answer:** D

### Q19. Your schema uses a boolean has_iep field. The school needs IEP type, specific accommodations, review dates, and case manager assignments. A single boolean cannot hold this data. What structure is needed?

- **A.** A dedicated accommodations table linked to students — storing IEP type, specific accommodations, review schedules, and case managers  ✅
- **B.** Expand the boolean into an enumerated field with predefined IEP categories that cover the most common accommodation type classifications
- **C.** Store detailed IEP information as a document attachment on the student record that authorized staff can download and review when needed
- **D.** Link to the district's existing special education management system via API so IEP details are queried on demand from the source system

> **Answer:** A

### Q20. Student home addresses are stored in plain text with no encryption in the database. A breach exposes addresses for 15,000 students and their families. What protection should have been implemented?

- **A.** Address data should be collected only when absolutely necessary and removed from the database within 30 days of the educational purpose
- **B.** Tokenize address fields by replacing real values with randomly generated tokens that map to the actual addresses in a separate vault
- **C.** Encrypt all PII including student addresses at rest in the database with access controls limiting who can decrypt and view the values  ✅
- **D.** Store student addresses only in the district's SIS system and query them on demand via API rather than maintaining a local database copy

> **Answer:** C

### Q21. Teachers can permanently delete student records with no recovery option. A teacher accidentally deletes a student's entire grade history. The data is gone. What safety mechanism was missing?

- **A.** Remove the delete capability from teacher accounts entirely and require all record deletions to go through a district administrator
- **B.** Soft deletes with a recovery period — mark records as deleted but retain them for 30-90 days before permanent purge with admin restore  ✅
- **C.** A mandatory confirmation dialog requiring the teacher to type the student's name to confirm they intend to permanently delete the record
- **D.** Automatic nightly backups that retain deleted records so the database administrator can restore individual records from backup files

> **Answer:** B

### Q22. Biology 101 exists as a single course record. Three teachers each teach their own section with different students, schedules, and grades. Your system treats them as one course. What data model is needed?

- **A.** Clone the course record three times and maintain separate copies for each teacher with manual synchronization of curriculum updates
- **B.** Add a teacher_id filter to all grade and roster queries so that each teacher's view is dynamically scoped within the shared course record
- **C.** Create a scheduling overlay that maps each teacher's time slots to the single course record without changing the underlying data model
- **D.** Course sections — each teacher's instance is a separate section linked to the master course with its own roster, schedule, and grades  ✅

> **Answer:** D

### Q23. A state audit requires proof that no District A student data was ever accessed by District B users. Your system has no access logging. You cannot prove compliance. What should be in place?

- **A.** Access audit logging — record who accessed which student records, when, and from which district context to prove compliance in audits  ✅
- **B.** Database query logs that capture every SQL statement executed against the student tables with the requesting user's session information
- **C.** A signed attestation from each district administrator confirming that their staff only accessed student data within their own district
- **D.** Network access controls that restrict database connections to IP addresses associated with each district's authenticated VPN endpoints

> **Answer:** A

### Q24. Report cards are generated from live grade data. A teacher changes a grade after report cards were sent. The next viewer sees the updated grade, not what was originally distributed. What should report cards reference?

- **A.** Lock all grades when report cards generate so no changes can be made until the next reporting period opens for teacher grade entry
- **B.** Add a disclaimer to report cards stating that grades are subject to change and the document reflects the most current values available
- **C.** A snapshot of grades at generation time — report cards are point-in-time documents and should not change after distribution to families  ✅
- **D.** A version history that shows both the original and updated grades on the report card ensuring that parents can see what changed after distribution

> **Answer:** C

### Q25. Your platform stores three years of student data across 50 districts. The backup service reports success every night but you have never tested a full database restore. How do you verify backup reliability?

- **A.** Review the backup service logs monthly to confirm that file sizes and completion times are consistent with expectations for the data volume
- **B.** Test restores regularly — verify that backed-up data is complete, correct, and recoverable within your target recovery time objectives  ✅
- **C.** The backup service provider guarantees data integrity through their SLA so testing restores would be redundant and waste engineering time
- **D.** Implement a secondary backup system from a different vendor that runs in parallel providing redundancy without requiring restore testing

> **Answer:** B


---
_Take it in the browser: https://the-faction.mn.co/posts/104111712_
