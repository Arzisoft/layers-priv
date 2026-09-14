---
course: "The Industry"
module: "Module 3: Project Records & Multi-Site Data"
lesson: "Module 3: Project Records & Multi-Site Data — Exam"
type: "course_quiz"
post_id: 104450669
space_id: 24251863
source: "https://the-faction.mn.co/posts/104450669"
updated: "2026-08-10T18:15:43Z"
---

# Module 3: Project Records & Multi-Site Data — Exam

> Exam for **Module 3: Project Records & Multi-Site Data** (The Industry) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. Your AI builds a construction database that organizes all records by user rather than by project. Why is this a problem?

- **A.** User-centric schemas prevent the system from generating financial reports accurately because costs are tied to individuals
- **B.** The database engine cannot efficiently index records by user since construction platforms expect project keys
- **C.** In construction, the project is the primary entity and every record from daily reports to costs belongs to a project  ✅
- **D.** User-based organization requires each person to have only one active project which limits platform functionality

> **Answer:** C

### Q2. A GC manages 15 active projects. Their dashboard shows total costs from all projects mixed together in a single view. What is missing?

- **A.** Project-level data isolation so each project has separate financial reporting while still supporting portfolio views  ✅
- **B.** A filter dropdown that lets the GC manually select which project to display on the main dashboard at any time
- **C.** Separate database instances for each of the 15 projects to guarantee no data crosses between them accidentally
- **D.** An automated reconciliation process that verifies no cost entries were incorrectly assigned to the wrong project record

> **Answer:** A

### Q3. Your platform uses custom cost codes instead of CSI MasterFormat. A bonding company asks for cost data by standard divisions. What breaks?

- **A.** The bonding company rejects the application entirely because non-standard cost codes indicate poor financial control
- **B.** The custom codes cannot be exported to any standard external format because the database schema does not support mapping
- **C.** The project budget becomes inaccurate because custom codes calculate rollup totals differently than standard ones
- **D.** The GC must manually map every cost entry to CSI divisions which is time-consuming and introduces translation errors  ✅

> **Answer:** D

### Q4. Your AI stores 200MB blueprint PDFs directly in database rows alongside project metadata. What performance issue does this create?

- **A.** The database replication process fails because large binary objects exceed the maximum row size the engine allows
- **B.** Queries against project metadata slow dramatically because the database reads massive file data alongside it  ✅
- **C.** Blueprint files become corrupted during database transactions because the engine is not designed for binary storage
- **D.** The database backup process takes so long that it blocks all other operations and causes the platform to go offline

> **Answer:** B

### Q5. A project completed three years ago is involved in a warranty dispute. The contractor needs the daily reports from that period. Your platform deleted them after one year. What went wrong?

- **A.** The storage cost savings from deletion outweigh the legal risk because construction disputes rarely go back three years
- **B.** The platform should have converted the daily reports to summary documents before deleting the original detailed records
- **C.** Construction records require seven to ten years of retention for warranty claims and litigation and one year is insufficient  ✅
- **D.** The daily reports should have been printed and stored in physical archives rather than kept in the digital platform

> **Answer:** C

### Q6. A subcontractor working on two projects for the same GC can see data from all 15 of the GC active projects on the platform. What is the risk?

- **A.** The subcontractor has access to competitive pricing, project costs, and scope details that should be confidential  ✅
- **B.** The subcontractor may accidentally submit timecards or daily reports to the wrong project creating data integrity issues
- **C.** The platform performance degrades for the subcontractor because their view loads data from all 15 projects at once
- **D.** The GC insurance policy requires subcontractor data isolation and the lack of it creates a coverage compliance gap

> **Answer:** A

### Q7. Your project manager needs all mechanical RFIs from the first quarter. The query takes 45 seconds against a database with three years of records. What is likely missing?

- **A.** The database server needs more memory allocated to handle multi-year datasets because the records exceed the cache size
- **B.** Indexes on the document type, date, and trade columns that would let the database locate matching records without a full scan  ✅
- **C.** The query is written incorrectly and should use a different SQL syntax that the database engine can optimize more efficiently
- **D.** Older records should be deleted from the active database to reduce the total row count and speed up all query operations

> **Answer:** B

### Q8. Your platform stores field photos with no metadata — just the image file and a generic filename. Why does this reduce the documentation value?

- **A.** Photos without metadata are larger in file size and consume more storage space in the object storage bucket per image
- **B.** The platform is unable to display the photos in a gallery view because the rendering engine requires file metadata headers
- **C.** Insurance companies reject photo evidence that lacks metadata because it cannot be verified as authentic documentation
- **D.** Without timestamp, GPS coordinates, and project tags the photos cannot be searched, filtered, or tied to specific work  ✅

> **Answer:** D

### Q9. Your job costing schema tracks costs at the project level but not by cost code or division. The GC wants to know how much they spent on electrical across all projects. Can you answer?

- **A.** Yes, the platform can infer trade from the sub name and generate the report without cost code tagging data
- **B.** Yes, the accounting team can manually categorize each expense after the fact to build the report the GC requested
- **C.** No, without cost code tagging at the transaction level there is no reliable way to break spending down by trade  ✅
- **D.** No, but the GC can estimate the electrical spend by looking at the subcontractor payment total for that trade only

> **Answer:** C

### Q10. Your platform archives completed projects by moving all data to a cold storage tier. A lawyer requests records from an archived project. What must still work?

- **A.** The archived data must be queryable and retrievable even if access is slower than active project data speeds  ✅
- **B.** The platform should transfer the archived project back to active storage permanently before any records are accessed
- **C.** The lawyer must submit a formal court order before the platform is required to restore any archived project records
- **D.** Only summary reports from the archived project need to be retrievable since detailed records can be reconstructed later

> **Answer:** A

### Q11. Your schema includes a cost code field but no hierarchy for divisions, phases, and cost types. Why does a flat cost code structure fall short?

- **A.** Flat cost codes cannot be sorted or grouped logically which prevents the platform from generating organized cost reports
- **B.** The database engine requires hierarchical keys for efficient indexing and flat codes cause index fragmentation
- **C.** Subcontractors cannot map their internal cost tracking to a flat system because their own codes are hierarchical
- **D.** Rollup reporting at the division and phase level is impossible without a hierarchy that groups codes into categories  ✅

> **Answer:** D

### Q12. A project manager searches for a specific submittal document uploaded last month. The search returns nothing despite the document existing. What is likely wrong?

- **A.** The document was uploaded by a subcontractor account and the PM role does not have permission to view sub uploads
- **B.** The document metadata was not populated during upload so the search engine has no indexed fields to match against  ✅
- **C.** The search function only works on documents created within the platform and not on externally uploaded PDF files
- **D.** The platform search indexes refresh on a weekly schedule and last month upload has not been included in the index

> **Answer:** B

### Q13. Your database schema does not include a project foreign key on the daily reports table. Reports can be created without being linked to a project. What breaks?

- **A.** Orphaned reports with no project association cannot appear in project timelines, searches, or compliance records  ✅
- **B.** The database will reject all insert operations on the daily reports table because the missing key causes a constraint error
- **C.** Daily reports automatically inherit the project from the logged-in user profile so the foreign key is not required
- **D.** The reporting engine generates duplicate entries because it cannot distinguish which project each report belongs to

> **Answer:** A

### Q14. Your platform needs to display both per-project financial isolation and company-wide portfolio summaries. How should the database support both views?

- **A.** Maintain two separate databases: one for individual project records and another that aggregates company-wide totals
- **B.** Run portfolio summaries by exporting all project data to a spreadsheet where the GC can build their own reports
- **C.** Use project-scoped queries for isolation and cross-project aggregation queries for portfolio views on the same schema  ✅
- **D.** Copy each project transaction into a central summary table nightly so the portfolio view always reads from the copy

> **Answer:** C

### Q15. Your document storage puts all project files in a single folder with no organization by project, type, or date. Why is this a problem at scale?

- **A.** The storage provider charges higher fees for unorganized files because they consume more indexing resources
- **B.** File names will eventually collide across projects causing uploads to overwrite existing documents silently
- **C.** Unorganized storage prevents the platform from applying different access permissions to different document types
- **D.** Finding a specific document requires scanning every file in storage instead of navigating a structured path hierarchy  ✅

> **Answer:** D

### Q16. Your AI creates a change order table that tracks the new amount but not the original contract value or the running total. What reporting gap does this create?

- **A.** The platform cannot generate a change order document because the PDF template requires the original contract value
- **B.** The GC cannot see the cumulative contract value after all changes which is essential for billing reconciliation  ✅
- **C.** The subcontractor cannot verify their payment amount because the change order table does not link to their scope
- **D.** The project schedule cannot reflect the time impact of change orders without the original contract start date stored

> **Answer:** B

### Q17. Your database has no concept of user roles or project assignment. Every authenticated user can query any project record. What must you add?

- **A.** Role-based access control with project assignment so users see only the projects and data their role permits  ✅
- **B.** An approval workflow where a project manager manually authorizes each data request from individual team members
- **C.** A read-only mode for all users except administrators since most construction team members only need to view data
- **D.** A logging system that records queries so unauthorized access can be detected after the fact during an audit

> **Answer:** A

### Q18. A daily report record in your database contains crew count, weather, and work description but no timestamp or author. What is the impact?

- **A.** The daily report cannot be displayed in the mobile interface because the rendering engine requires a timestamp field
- **B.** The project schedule is unable to calculate actual progress because the daily report must link to a schedule activity
- **C.** The report is automatically flagged as incomplete by the system and moved to a draft state until the fields are added
- **D.** The report has no legal standing as a project record because it cannot prove when it was written or by whom  ✅

> **Answer:** D

### Q19. Your platform stores all 15 active projects in a single database table with no partitioning. As data grows over years the table has millions of rows. What strategy helps?

- **A.** Delete records older than one year to keep the table size manageable and maintain fast query response times
- **B.** Switch to a NoSQL database because relational databases cannot handle tables with more than a million records
- **C.** Add composite indexes on project and date columns and consider partitioning by project or time range for scale  ✅
- **D.** Move each project to its own dedicated database instance to eliminate cross-project table scans and reduce contention

> **Answer:** C

### Q20. Your AI stores photos in the database as base64-encoded text fields. Each project has 2,000 photos. What architecture change should you make?

- **A.** Compress the base64 strings with a lossless algorithm to reduce the storage size of each photo record in the table
- **B.** Move photo files to object storage and keep only the metadata and URL reference in the database for each image  ✅
- **C.** Limit the number of photos per project to 500 to keep the database table within a manageable size for queries
- **D.** Create a separate database table for photos so the main project table is not affected by the large binary data

> **Answer:** B

### Q21. Your retention policy archives completed projects after 90 days. A project that finished two years ago needs records for an insurance claim. Are they available?

- **A.** Yes, archival means moving to cold storage for cost savings and the records should remain accessible for retrieval  ✅
- **B.** No, archival after 90 days means the records were deleted permanently and cannot be recovered for the claim
- **C.** Only if the project manager exported a backup copy before the 90 day archive window closed on the active records
- **D.** The insurance company must accept that archived records are unavailable and settle the claim based on other evidence

> **Answer:** A

### Q22. Your job costing report shows labor costs for the concrete division but cannot separate costs by project phase. What is missing from the schema?

- **A.** A time tracking integration that records which phase each worker was active in during their logged shift hours
- **B.** A separate labor cost table that duplicates the cost data with an additional phase column for filtered reporting
- **C.** A phase field on each cost transaction that tags spending to a specific project phase within the division structure  ✅
- **D.** A scheduling module that assigns each division of work to a phase so the cost system can inherit the phase mapping

> **Answer:** C

### Q23. Your database migration adds a required project_id column to the daily reports table. Existing reports have no project association. What must the migration handle?

- **A.** Delete all existing reports that cannot be associated with a project since they provide no value without the link
- **B.** Set the new column to nullable and leave existing reports without a project ID to avoid blocking the migration
- **C.** Reject the migration entirely until all existing reports have been manually assigned a project ID by an administrator
- **D.** Provide a data backfill strategy that assigns existing reports to projects based on user assignment and date context  ✅

> **Answer:** D

### Q24. Your platform generates a PDF report of all RFIs for a completed project. The report takes 10 minutes to compile from the database. What optimization should you add?

- **A.** Cache the compiled PDF permanently so the report only generates once and all future requests serve the cached file
- **B.** Add database indexes on the project and document type columns and use pagination to generate the report in chunks  ✅
- **C.** Move all completed project data to a faster database engine that is optimized for read-heavy reporting workloads
- **D.** Reduce the RFI data stored per record so each row is smaller and the query can read more records per second overall

> **Answer:** B

### Q25. You audit your construction database architecture and it passes all checks. How often should the schema and data integrity be re-verified?

- **A.** After every schema migration and periodically because new data patterns or volumes can reveal integrity issues  ✅
- **B.** Only when a user reports missing or incorrect data since a passing audit confirms the schema is structurally sound
- **C.** Once per year during an annual database review when the storage costs and retention policies are also evaluated
- **D.** Schema verification is not needed again unless the database engine is upgraded to a new major version release

> **Answer:** A


---
_Take it in the browser: https://the-faction.mn.co/posts/104450669_
