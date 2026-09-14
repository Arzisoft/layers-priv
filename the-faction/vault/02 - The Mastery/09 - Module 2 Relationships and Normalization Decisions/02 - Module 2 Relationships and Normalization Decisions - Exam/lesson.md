---
course: "The Mastery"
module: "Module 2: Relationships and Normalization Decisions"
lesson: "Module 2: Relationships and Normalization Decisions — Exam"
type: "course_quiz"
post_id: 105097312
space_id: 24191170
source: "https://the-faction.mn.co/posts/105097312"
updated: "2026-08-10T20:44:09Z"
---

# Module 2: Relationships and Normalization Decisions — Exam

> Exam for **Module 2: Relationships and Normalization Decisions** (The Mastery) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. A customer can have many orders. How is this relationship modeled correctly?

- **A.** A copy of the customer's details is stored inside each order row so the link is always visible
- **B.** Each order row carries the customer's ID, pointing every order back to exactly one customer  ✅
- **C.** The customer row holds a text list of order numbers, updated every time a new order arrives
- **D.** Orders and customers share one table, with a type column marking which kind each row is

> **Answer:** B

### Q2. What is a foreign key actually for?

- **A.** Granting external partners limited access to specific tables in your production database
- **B.** Encrypting cross-table references so relationships stay hidden from any database intruder
- **C.** Enforcing that a reference points to a real row, so links between tables can't silently break  ✅
- **D.** Speeding up joins by caching the referenced row inside the referencing table itself automatically

> **Answer:** C

### Q3. Students enroll in many courses, and courses hold many students. What structure does this require?

- **A.** Two mirrored columns, with each table holding a list of the other's IDs kept in sync nightly
- **B.** A parent-child setup where students belong to their first course and visit the others as guests
- **C.** Duplicating student rows once per course, so every enrollment is a complete standalone record
- **D.** A separate join table where each row links one student to one course, one row per enrollment  ✅

> **Answer:** D

### Q4. What does normalization mean in practical terms for your AI-built app?

- **A.** Each fact is stored once, in one place, so updates happen once and nothing drifts out of sync  ✅
- **B.** All tables are renamed to a standard naming scheme published officially by the database's own vendor
- **C.** Text values are converted to lowercase so searches behave the same across every language
- **D.** Every table is padded to the same column count, keeping the schema visually balanced

> **Answer:** A

### Q5. You delete a customer and their orders remain, pointing at a customer who no longer exists. What are these rows, and why do they matter?

- **A.** Orphaned records; they break reports and code that assume every order has a real customer  ✅
- **B.** Ghost rows; they are harmless duplicates that the database will clean up on its own schedule
- **C.** Legacy rows; they are required by tax law to remain untouched for a period of seven years
- **D.** Shadow records; they improve performance by keeping deleted relationships warm in cache

> **Answer:** A

### Q6. When is denormalizing, meaning deliberately duplicating data, a legitimate choice?

- **A.** Whenever it saves the AI agent tokens during the build, since efficiency compounds over time
- **B.** When a measured read pattern justifies it and you have a plan to keep the copies consistent  ✅
- **C.** Never; duplication is always a defect regardless of the performance problem it addresses
- **D.** Whenever tables pass one thousand rows, the point where joins stop being dependable

> **Answer:** B

### Q7. Your AI asks whether deleting a customer should automatically delete their orders too. What is this decision really about?

- **A.** Storage planning, since cascade rules exist mainly to keep the table sizes under control
- **B.** Query speed, since automatic deletes keep join performance stable as the app grows larger
- **C.** Cascade behavior; whether removing a parent removes its children is a business decision  ✅
- **D.** Backup frequency, since cascading deletes change how often snapshots must be taken

> **Answer:** C

### Q8. An orders table repeats the product's name and price in every order row. When is this actually correct?

- **A.** Never; the correct approach is always joining to the products table so details stay current
- **B.** Only while the catalog remains small, since repetition stops scaling past a few hundred items
- **C.** Only for digital goods, since physical products carry prices that change far too often to copy safely
- **D.** When capturing history: the order records what was true at purchase, even if the product changes  ✅

> **Answer:** D

### Q9. What is the risk of modeling everything into one huge "users" table with fifty columns covering every possible role?

- **A.** Databases cap tables at forty columns, so the design will fail the moment it is deployed
- **B.** Most columns sit empty for most rows, meaning gets unclear, and every change touches everything  ✅
- **C.** Login slows for every user, since authentication must scan all fifty columns each session
- **D.** The table cannot be exported to spreadsheets, blocking the reporting workflows later on

> **Answer:** B

### Q10. How do you decide between one-to-one, one-to-many, and many-to-many for two entities?

- **A.** State the relationship in plain business language first; the words tell you which structure fits  ✅
- **B.** Always choose many-to-many, since it safely covers both of the simpler cases anyway
- **C.** Count the rows you expect in each table and let the larger table own the relationship
- **D.** Let the AI agent decide from the column names, since naming reveals the true relationship

> **Answer:** A

### Q11. Your AI stored tags as a comma-separated string in one column. Searching by tag is now slow and buggy. What is the fix?

- **A.** Standardize the commas, since most tag bugs come from inconsistent spacing between values
- **B.** Cap tags at five per row so the string stays short enough for reliable searching at scale
- **C.** Switch the column to uppercase, making text matching consistent across all of the rows
- **D.** Model tags as their own table with a join table, so each tag link is a row you can query  ✅

> **Answer:** D

### Q12. What does referential integrity protect you from, day to day?

- **A.** Attackers reading data through injection, since integrity rules inspect all incoming queries
- **B.** Large bills, since integrity checks compress the foreign keys that dominate storage growth
- **C.** Broken links between tables: rows referencing parents that were deleted or never existed  ✅
- **D.** Slow queries, since verified relationships allow the database to skip the joins entirely

> **Answer:** C

### Q13. A one-to-one split: a profiles table separate from the users table. When does this split earn its place?

- **A.** Whenever the AI suggests it, since agents propose splits only after detecting real structural problems
- **B.** When the extra fields are optional, sensitive, or rarely loaded, so the core table stays lean  ✅
- **C.** Never; one-to-one splits are a legacy pattern that modern databases have made obsolete
- **D.** Only past one million users, when the physical size of a single table becomes the issue

> **Answer:** B

### Q14. What is the practical test for "too normalized" in an AI-built app?

- **A.** Everyday screens need six or seven joins for basic data, and simple features feel hard to build  ✅
- **B.** The schema has more than ten tables, the ceiling most teams can hold in working memory
- **C.** The AI agent starts refusing to write queries, its signal that complexity crossed a line
- **D.** Storage usage drops below projections, showing data is spread across too many tables

> **Answer:** A

### Q15. Two features need the same customer data shaped differently. What keeps this from becoming duplication drift?

- **A.** Giving each feature its own copy of the table and assigning an owner to reconcile them weekly
- **B.** Alternating which feature reads live data by day, so the copies never disagree at the same time
- **C.** One source-of-truth table, with each feature deriving its own shape through queries or views  ✅
- **D.** Storing both shapes in the same row, doubling columns but guaranteeing total consistency

> **Answer:** C

### Q16. Your AI proposes deleting rows as the app's only way to remove anything. For which records should you require history instead?

- **A.** None; clean deletion everywhere is the simplest policy and simplicity should nearly always win out
- **B.** All records equally, since retaining every keystroke forever is the safest legal position
- **C.** Only images and files, since binary data is the only content that is costly to recreate
- **D.** Records with financial or legal weight: orders, payments, consent, where history must survive  ✅

> **Answer:** D

### Q17. When a many-to-many join table needs its own facts, like enrollment date and grade, what does that tell you?

- **A.** The relationship is a real entity itself and deserves first-class modeling with its own fields  ✅
- **B.** The design is broken, since join tables that accumulate fields clearly indicate failed normalization
- **C.** The two joined tables should merge, since data on the link means the split was artificial
- **D.** A document database is required, since relational systems can't attach data to the links

> **Answer:** A

### Q18. What is the danger in letting each new feature add its own slightly different "status" or "type" columns across tables?

- **A.** Databases limit the total number of status columns, and the app will hit that hard cap very quickly
- **B.** Inconsistent vocabularies emerge, and cross-table reporting becomes guesswork and translation  ✅
- **C.** Status columns can't be indexed, so each addition slows every query in the application
- **D.** Users see raw status values in error messages, leaking internal terminology publicly

> **Answer:** B

### Q19. Your AI suggests copying the user's current subscription tier onto every activity row for convenience. What do you ask first?

- **A.** Whether the activity table has the space, since wide rows are the main real constraint at scale
- **B.** Whether the AI can write the copy code quickly, since build speed determines the choice
- **C.** What happens when the tier changes: are millions of old rows now wrong, and does it matter?  ✅
- **D.** Whether tiers are text or numbers, since only numeric fields copy safely between tables

> **Answer:** C

### Q20. How should you handle a "category" that today has four fixed values but the business says may grow?

- **A.** A small categories table the business can add rows to, so growth needs no schema changes  ✅
- **B.** Four boolean columns, one per category, adding a new column whenever a new category appears
- **C.** Hard-code the four values into every query, since compiled values outperform lookups
- **D.** A free-text column, since typing category names keeps the design maximally flexible

> **Answer:** A

### Q21. What breaks when two tables both try to own the same relationship, each holding a reference to the other?

- **A.** Nothing; mutual references are the standard pattern for any truly strong two-way relationship
- **B.** Only performance, since two-way links double the index count on each of the two tables
- **C.** Backups, since circular references prevent most tools from ordering tables at export
- **D.** Consistency: the two links can disagree, and now the schema itself can hold a contradiction  ✅

> **Answer:** D

### Q22. The business asks which customers bought product X this quarter, and your schema can't answer it cleanly. What went wrong upstream?

- **A.** The database engine is underpowered; that query is heavy and needs a bigger plan to run
- **B.** Relationships weren't modeled for the questions the business asks; orders and products don't connect  ✅
- **C.** The AI agent was underprompted; longer instructions would have produced better queries
- **D.** Marketing asked too late; that question needed to be scheduled before the quarter began

> **Answer:** B

### Q23. When should you let your AI restructure existing relationships in a live schema?

- **A.** Freely, since agents propose restructures only when the benefit is already overwhelming
- **B.** Never, since a schema that reached production must be treated as permanently frozen
- **C.** On a fixed monthly schedule, so restructuring becomes a routine rather than an event
- **D.** With a migration plan and a staging test, since restructuring live relationships moves real data  ✅

> **Answer:** D

### Q24. What is the honest trade-off at the heart of every normalization decision?

- **A.** Cost versus security: normalized schemas are cheaper but expose more attack surface
- **B.** Beauty versus function: normalized schemas read better but consistently perform much worse
- **C.** Consistency versus convenience: one copy is always right, but sometimes slower to read  ✅
- **D.** Speed versus legality: duplication is faster but restricted under data protection law

> **Answer:** C

### Q25. Which principle should govern every relationship decision in your schemas?

- **A.** Model relationships as the business truly works, keep one source of truth, duplicate on purpose  ✅
- **B.** Minimize tables above all else, since every join is a future performance incident waiting
- **C.** Duplicate freely from the start, since storage is cheap and consistency tools are mature
- **D.** Avoid foreign keys in production, since enforcement belongs entirely to application code

> **Answer:** A


---
_Take it in the browser: https://the-faction.mn.co/posts/105097312_
