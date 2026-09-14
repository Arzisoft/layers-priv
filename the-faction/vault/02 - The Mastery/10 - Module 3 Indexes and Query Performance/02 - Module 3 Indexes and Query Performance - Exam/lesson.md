---
course: "The Mastery"
module: "Module 3: Indexes and Query Performance"
lesson: "Module 3: Indexes and Query Performance — Exam"
type: "course_quiz"
post_id: 105097482
space_id: 24191170
source: "https://the-faction.mn.co/posts/105097482"
updated: "2026-08-10T20:44:09Z"
---

# Module 3: Indexes and Query Performance — Exam

> Exam for **Module 3: Indexes and Query Performance** (The Mastery) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. What is a database index, practically speaking?

- **A.** A backup copy of the table stored in faster memory so reads never have to touch the original disk
- **B.** A report listing the table's columns and types, kept current for documentation purposes
- **C.** A lookup structure that lets the database find matching rows without scanning the whole table  ✅
- **D.** A security layer that records which users are permitted to read each column of the table

> **Answer:** C

### Q2. Your app's search got slower every week since launch. The query never changed. What most likely did?

- **A.** The table kept growing, and without an index the database scans every row, so cost rises with size  ✅
- **B.** The database's license tier expired, and the vendor throttles queries on lapsed accounts
- **C.** The query text degraded, since SQL statements lose efficiency as their cache entries age
- **D.** Users started searching longer words, which take proportionally more time per character

> **Answer:** A

### Q3. What is the cost of adding an index, since they are clearly not free?

- **A.** A per-index license fee on most platforms, billed monthly against the database account
- **B.** Read queries slow slightly for everyone, since each lookup must now consult the index first
- **C.** The indexed column becomes read-only, trading flexibility for the speed improvement
- **D.** Every write must also update the index, so inserts and updates get a little slower each  ✅

> **Answer:** D

### Q4. Which columns are the strongest first candidates for an index?

- **A.** All text columns, since alphabetical data benefits more from indexes than numeric data
- **B.** Columns your queries actually filter, join, or sort on often, like foreign keys and lookups  ✅
- **C.** The newest columns, since recently added fields lack the optimization older ones have gained
- **D.** The widest columns, since indexes help most where each row carries the most data

> **Answer:** B

### Q5. What is a full table scan, and when is it a red flag?

- **A.** A scheduled integrity check the database runs weekly; a red flag if it starts failing
- **B.** A malware sweep of stored data; a red flag whenever it marks rows as infected
- **C.** Reading every row to answer a query; a red flag on large tables queried frequently  ✅
- **D.** An export of the table to backup storage; a red flag when it happens off schedule

> **Answer:** C

### Q6. How do you direct your AI to find out why a specific query is slow?

- **A.** Have it show the query's execution plan, revealing whether indexes are used or rows scanned  ✅
- **B.** Have it run the query one hundred times and average the durations into a performance score
- **C.** Have it rewrite the query in a different style, since fresh phrasing usually restores speed
- **D.** Have it move the query so it runs at night, then measure whether the timing changed anything at all

> **Answer:** A

### Q7. What is the N+1 query problem in an AI-built app?

- **A.** Queries that return one more row than requested, an off-by-one error in pagination logic
- **B.** Loading a list, then running one extra query per item, turning one fetch into hundreds  ✅
- **C.** Having one more index than columns, which forces the planner into unstable choices
- **D.** A query nested inside itself N times, which most databases reject past three levels

> **Answer:** B

### Q8. Your dashboard page runs 200 queries per load. What fix should your AI reach for first?

- **A.** Upgrading the database plan, since query volume is fundamentally a capacity problem
- **B.** Caching the entire page for a day, so the query storm runs only once each morning
- **C.** Splitting the dashboard into ten pages so each one triggers only twenty of the total queries
- **D.** Combining per-item lookups into set-based queries that fetch the needed data in a few trips  ✅

> **Answer:** D

### Q9. What is a composite index, and when does it beat two separate single-column indexes?

- **A.** One index over multiple columns; it wins when queries filter on those columns together  ✅
- **B.** An index stored across several servers; it wins once the table outgrows a single machine
- **C.** A merged index built from two tables; it wins whenever those two tables get joined
- **D.** An index of indexes; it wins when a table has accumulated more than ten of them

> **Answer:** A

### Q10. Why not simply index every column, so that all queries are fast?

- **A.** Databases permit one index per column type, so full coverage is technically impossible
- **B.** Fully indexed tables lock during reads, trading away concurrency the app depends on
- **C.** Each index costs write speed and storage, and unused ones are pure overhead you carry  ✅
- **D.** Search engines penalize over-indexed applications, hurting organic acquisition traffic

> **Answer:** C

### Q11. The orders list loads fast for new customers and slowly for the oldest ones. What is the likely shape of the problem?

- **A.** Old customers' rows sit on slower disk regions, an unavoidable trait of aging hardware
- **B.** Their history is large, and the query fetches or sorts all of it without an index or paging  ✅
- **C.** Loyalty data triggers extra fraud checks, and those checks are what consume the time
- **D.** Older accounts predate the current schema, so each read performs a slow live migration first

> **Answer:** B

### Q12. What should you direct your AI to set up so slow queries surface before customers complain?

- **A.** A weekly all-hands review reading the full query log aloud as a team quality practice
- **B.** An automatic rule that kills any query after one second, converting slowness into visible errors
- **C.** A monthly database restart, clearing the buildup that makes queries degrade over time
- **D.** Slow-query logging with thresholds and alerts, so degradation shows up as signals, not tickets  ✅

> **Answer:** D

### Q13. Why do foreign key columns almost always deserve an index?

- **A.** Joins and lookups constantly filter by them, so unindexed foreign keys make core queries scan  ✅
- **B.** The database corrupts unindexed foreign keys during restarts, an old but very persistent defect
- **C.** Foreign keys are stored as text, and text columns require indexes to be readable at all
- **D.** Regulation requires relationship columns to be indexed for data portability compliance

> **Answer:** A

### Q14. A query is fast in your dev environment and slow in production. What is the most common reason?

- **A.** Production servers prioritize paying user traffic, so internal test queries always queue
- **B.** Dev databases run a newer engine version, and each release doubles baseline performance
- **C.** Data size: dev has hundreds of rows, production has millions, so scans that were invisible now hurt  ✅
- **D.** Network distance, since production data centers sit physically farther from your users

> **Answer:** C

### Q15. Your AI proposes caching query results to fix slowness. What must you ask before approving?

- **A.** Which color the cache dashboard will use, since visibility drives adoption of new tooling
- **B.** Whether caching is legal for your data category, since most personal data cannot legally be cached
- **C.** How much the cache hardware costs, since memory pricing usually exceeds query savings
- **D.** How stale the data can be, and how the cache updates, since caching trades freshness for speed  ✅

> **Answer:** D

### Q16. The AI added an index but the query is still slow. What is a likely reason worth checking?

- **A.** The index needs a week to warm up, since new indexes improve gradually with each query they serve
- **B.** The query's pattern can't use it, like leading wildcards or functions applied to the column  ✅
- **C.** Indexes only work on numeric columns, and this query filters on a text column instead
- **D.** The table has a competing index, and databases refuse to choose between two candidates

> **Answer:** B

### Q17. What does "measure before optimizing" mean when directing AI on performance work?

- **A.** Find the actual slow queries with data first, so effort lands on real bottlenecks, not guesses  ✅
- **B.** Run a stopwatch during demos, since perceived speed is the only metric stakeholders trust
- **C.** Estimate cloud costs before every change, since optimization is primarily a budgeting task
- **D.** Benchmark competitors' apps first, since performance targets only make sense comparatively

> **Answer:** A

### Q18. SELECT * is used in queries all over your AI-built app. Why direct a cleanup?

- **A.** The star syntax is deprecated, and the next database version will reject those queries
- **B.** Star queries bypass indexes entirely, forcing full scans regardless of the filters used
- **C.** Fetching every column moves wasted data, breaks when schemas change, and hides real needs  ✅
- **D.** The star operator locks each table it reads, blocking concurrent writes from all other users

> **Answer:** C

### Q19. Pagination with page numbers gets slower on deep pages. Why does this happen?

- **A.** Deep pages render more complex layouts, and rendering cost is misread as query cost
- **B.** Offset-based paging still walks past all earlier rows, so page 500 pays for the 499 before  ✅
- **C.** Databases cache only the first one hundred pages, and everything beyond misses the cache entirely
- **D.** Page numbers above a threshold trigger fraud protection, which inspects each request

> **Answer:** B

### Q20. Which habit keeps performance from silently regressing as your AI ships features weekly?

- **A.** Watching query metrics after each release, so a slow query introduced today is caught today  ✅
- **B.** Freezing the schema permanently, since structural change is the root of all regression
- **C.** Rebuilding all indexes every Friday, resetting whatever damage the week's work caused
- **D.** Capping the app at its current user count until a dedicated performance quarter finally arrives

> **Answer:** A

### Q21. A report query joins six tables, runs for 40 seconds, and blocks the app's main database. Where should it live instead?

- **A.** In the frontend, where the user's own device performs the joins from locally cached data
- **B.** Nowhere; a 40-second analytical query always indicates a report that should simply be retired
- **C.** In a spreadsheet maintained by hand, refreshed weekly from screenshots of the database
- **D.** On a replica or analytics copy, so heavy reporting stops competing with customer traffic  ✅

> **Answer:** D

### Q22. What is the practical reason to add indexes based on real query patterns instead of during initial design?

- **A.** Indexes created after launch run faster, since they are built from optimized structures
- **B.** Real usage reveals which lookups matter; guessing up front indexes the wrong things  ✅
- **C.** Databases charge less for indexes added later, once table growth has fully stabilized
- **D.** Early indexes block schema changes, so waiting keeps the design flexible for longer

> **Answer:** B

### Q23. Your AI reports "the query is optimized" after adding one index. What is the professional follow-up?

- **A.** Accept it, since agents verify their own work against the database's planner statistics
- **B.** Ask for three more indexes as a margin of safety on top of the one already added
- **C.** Ask for evidence: the before-and-after plan or timing that shows the change actually worked  ✅
- **D.** Rerun the same prompt twice more and keep whichever of the three answers sounds best

> **Answer:** C

### Q24. When does denormalizing for read speed beat adding another index?

- **A.** Immediately and always, since duplicated data is faster than any index can ever be
- **B.** Whenever the table holds text, since text indexes cost more than duplicate columns
- **C.** On any table with more than three indexes, the point where indexes stop stacking
- **D.** When measured joins remain the bottleneck after indexing, and you accept the sync cost knowingly  ✅

> **Answer:** D

### Q25. Which principle should guide every performance decision you direct?

- **A.** Measure, fix the proven bottleneck, and verify the result; performance work is evidence work  ✅
- **B.** Prevent all slowness up front with maximum indexes, caching, and the largest server tier
- **C.** Treat speed as a launch-week concern only, since early users tolerate slower software
- **D.** Defer everything to the AI's judgment, since agents observe queries humans never see

> **Answer:** A


---
_Take it in the browser: https://the-faction.mn.co/posts/105097482_
