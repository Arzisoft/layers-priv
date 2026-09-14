---
course: "The Mastery"
module: "Module 1: Data Modeling Fundamentals"
lesson: "Module 1: Data Modeling Fundamentals — Exam"
type: "course_quiz"
post_id: 105097150
space_id: 24191170
source: "https://the-faction.mn.co/posts/105097150"
updated: "2026-08-10T20:44:08Z"
---

# Module 1: Data Modeling Fundamentals — Exam

> Exam for **Module 1: Data Modeling Fundamentals** (The Mastery) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. You ask your AI to build a customer table and it creates one giant table holding orders, payments, and support notes together. What is the problem?

- **A.** Wide tables slow down the login page since authentication must scan every column on each request
- **B.** Databases charge per column, so one wide table costs more than several narrow ones each month
- **C.** Giant tables cannot be backed up incrementally, forcing full exports on every single change that gets made
- **D.** Unrelated concepts are mixed in one structure, so changes to any one area risk breaking the others  ✅

> **Answer:** D

### Q2. What is the primary key's job in a table?

- **A.** Recording the date the row was created, so records can always be sorted by their true age later
- **B.** Uniquely identifying each row, so any record can be referenced and found without any ambiguity  ✅
- **C.** Encrypting the row's most sensitive column, so a breach exposes only nonidentifying information
- **D.** Marking which row the application should load first when a user opens the related screen or page

> **Answer:** B

### Q3. Your AI proposes using customer email addresses as the primary key. Why direct it to use a generated ID instead?

- **A.** Emails change and get reused; a key must stay stable forever, so use a value with no business meaning  ✅
- **B.** Email keys make tables sort alphabetically, which slows inserts near the bottom of the alphabet
- **C.** Databases index numbers only, so a text key would leave the table without any usable index at all
- **D.** Duplicate emails are legal in most countries, so uniqueness could never be enforced reliably there

> **Answer:** A

### Q4. A column named "data2" holds different things depending on the row. What should you direct your AI to do?

- **A.** Add a comment in the code explaining what the column means in each of the possible different cases
- **B.** Rename it to "data_final" so future builders know the column's contents are now considered fully official
- **C.** Split it into clearly named columns with one meaning each, since a field should hold one kind of fact  ✅
- **D.** Convert it to a text type large enough to store any value that might possibly appear in the future

> **Answer:** C

### Q5. Why give every table created_at and updated_at timestamp columns from the start?

- **A.** You can't answer "when did this change" retroactively; history has to be captured as it happens  ✅
- **B.** Databases run scheduled cleanups by default and delete any rows missing timestamp columns
- **C.** Timestamps compress well, so the two columns shrink the overall total size of every table they join
- **D.** Most frontend frameworks refuse to render lists of records that lack timestamp metadata

> **Answer:** A

### Q6. Your AI stores order status as free text and rows now contain "shipped", "Shipped", and "SHIPPED". What is the fix?

- **A.** A nightly script that rewrites all status values into lowercase before any reports are generated
- **B.** Training users to type more carefully by adding a warning message right next to the status input field
- **C.** A report filter that treats all capitalizations as equal so the dashboards stay accurate anyway
- **D.** Constrain the column to a fixed set of allowed values so invalid variants can't be written at all  ✅

> **Answer:** D

### Q7. When should a column be allowed to be empty, meaning nullable?

- **A.** Always, since flexible columns prevent errors from stopping users in the middle of a signup flow
- **B.** Never, since empty values crash most reporting tools the moment they scan the affected table
- **C.** Only when missing is a real, meaningful state; otherwise require a value so gaps can't hide bugs  ✅
- **D.** Only on text columns, since numeric columns will always store their empty values as zero automatically

> **Answer:** C

### Q8. What does it mean to say the schema is a contract for your AI-built app?

- **A.** It is a legal document filed with your business registration that regulators are able to inspect
- **B.** Code and integrations depend on its structure, so changing it casually breaks things that trusted it  ✅
- **C.** The database vendor guarantees uptime only for tables that follow its own published templates
- **D.** Users agree to the schema in your terms of service, so edits require notifying every account

> **Answer:** B

### Q9. You're modeling a booking app. Where should the list of entities come from?

- **A.** The nouns of the business itself: customers, appointments, services, payments, and the like  ✅
- **B.** The database vendor's starter templates, since proven generic schemas outperform custom ones
- **C.** The AI agent's preference, since models choose structures they can query most efficiently
- **D.** The frontend design files, since tables should mirror the screens users will interact with

> **Answer:** A

### Q10. The same customer's phone number is stored in four different tables. What problem will this create?

- **A.** Phone-format validation runs four times per update, slowing the app noticeably during daily peak hours
- **B.** The copies will drift out of sync, and no one will know which number is actually the true one  ✅
- **C.** Duplicate values quadruple the size of backups, making restores too slow to meet targets
- **D.** Search results will show the customer four times until the duplicates are manually merged

> **Answer:** B

### Q11. What is the danger of letting your AI agent invent the schema with no review from you?

- **A.** AI-generated schemas are unindexable, since generated names exceed database length limits
- **B.** The schema will be too small, since models minimize tables to reduce their own token usage
- **C.** Vendors void support agreements for schemas that were not designed by certified humans
- **D.** It may encode wrong assumptions about your business that get expensive to unwind once data arrives  ✅

> **Answer:** D

### Q12. Your AI chose a decimal type for money and a forum post suggested float instead. Why keep decimal?

- **A.** Floats are licensed separately in most databases and raise costs once data volumes increase far enough
- **B.** Decimals sort faster than floats, which keeps financial reports responsive as the data grows
- **C.** Floats round in ways that create cent-level errors; money needs exact math, not approximations  ✅
- **D.** Floats cannot be summed across rows, which breaks the revenue totals in monthly reporting

> **Answer:** C

### Q13. Your AI names tables "tbl1", "usrdata", and "temp_new_2". Why insist on clear names?

- **A.** Short names save storage, but the savings no longer justify the confusion they create today
- **B.** Names are how humans and agents reason about the system; unclear names invite wrong changes  ✅
- **C.** Modern databases parse long names faster, so clear names actually improve query speed too
- **D.** App stores will reject any build whose database schema contains abbreviations in the table names

> **Answer:** B

### Q14. What is the right way to handle a value you can always calculate from other columns, like an order total?

- **A.** Generally derive it when needed, and store it only deliberately with a plan to keep it in sync  ✅
- **B.** Always store it, since stored totals are legally required for financial audit and tax purposes anyway
- **C.** Never compute it at all, since calculations belong in spreadsheets rather than applications
- **D.** Store it in a separate database, so derived numbers can't contaminate the original records

> **Answer:** A

### Q15. A single "address" text column holds street, city, state, and zip together. When does this become a problem?

- **A.** When the table passes ten thousand rows, since long text slows the whole storage engine down badly
- **B.** When users enter commas inside the street name, corrupting the whole address permanently
- **C.** When printing labels, since printers require each address line as a separate data field
- **D.** The moment you must search, filter, or validate by part of it, like every customer in one city  ✅

> **Answer:** D

### Q16. What should you direct your AI to do before writing any tables for a new app idea?

- **A.** Walk through the core workflows and list what facts must be stored for each step to work  ✅
- **B.** Copy the schema of the largest competitor, since market leaders have proven data models
- **C.** Buy the largest database plan available, so the schema never faces capacity constraints
- **D.** Build the frontend first, since real screens are the only reliable source of requirements

> **Answer:** A

### Q17. A status field uses codes 1 through 5 and nobody remembers what 3 means. What principle was violated?

- **A.** Compression: codes must map to letters, since numbers cost far more storage than characters do
- **B.** Order: status codes must follow the sequence in which the statuses occur in the real world
- **C.** The schema should be self-explanatory; meaning that lives only in someone's memory gets lost  ✅
- **D.** Security: numeric codes leak business logic to anyone who ever gains access to the table

> **Answer:** C

### Q18. Your app must support both individual customers and companies. Your AI asks how to model it. What is the key question?

- **A.** Which type will sign up first, since the earliest records determine the permanent structure
- **B.** What the two share and where they differ, so shared fields live together and differences stay clean  ✅
- **C.** Which type pays more, since revenue share determines which entity deserves its own table
- **D.** Whether companies have logos, since image storage changes the entire modeling approach

> **Answer:** B

### Q19. Why record which user made each change in important tables?

- **A.** Databases bill by user activity, so attribution lets you charge each department accurately
- **B.** Change attribution is required before any table is allowed to hold more than one editor
- **C.** It makes rows larger, which conveniently forces the team to archive old records sooner
- **D.** When data looks wrong later, "who changed this and when" is the first question you'll ask  ✅

> **Answer:** D

### Q20. What is the practical risk of adding twenty "maybe useful someday" columns to a new table?

- **A.** The table becomes read-only once it crosses fifteen columns in most managed databases
- **B.** Every query returns all columns by default, so unused fields leak into your public API
- **C.** Empty columns invite inconsistent future use, and clutter makes real fields harder to trust  ✅
- **D.** Storage costs rise steeply, since empty columns are billed at the very same rate as full ones

> **Answer:** C

### Q21. Your AI suggests storing uploaded images directly inside the database. What do you direct instead?

- **A.** Keep files in object storage and store only their locations, so the database stays lean and fast  ✅
- **B.** Accept the suggestion, since databases compress images better than file systems manage to
- **C.** Store thumbnails in the database and keep the originals on a local laptop for safe keeping
- **D.** Convert images to text descriptions, since modern AI can regenerate them whenever needed

> **Answer:** A

### Q22. When your AI presents a proposed schema, what is the strongest way to pressure-test it?

- **A.** Count the tables, since a correct schema for a small app always lands between five and nine tables
- **B.** Ask the agent to rate its own confidence, and accept any design scoring above ninety percent
- **C.** Walk real scenarios through it: place an order, issue a refund, and see if the data holds up  ✅
- **D.** Load a million fake rows and measure speed, since performance is the only objective test

> **Answer:** C

### Q23. What makes a schema "wrong" even when the app runs fine in the demo?

- **A.** Using plural table names, which the largest frameworks now treat as deprecated behavior
- **B.** It can't answer questions the business will predictably ask, like revenue by month or customer  ✅
- **C.** Having more than twenty tables, which exceeds what a small team can realistically hope to maintain
- **D.** Storing dates in the server's timezone, which no production application should ever do

> **Answer:** B

### Q24. A field can hold values the business considers impossible, like a negative quantity. What should you direct?

- **A.** Leave it alone, since impossible values never actually occur in practice once the app is well built
- **B.** Handle it in the frontend only, since users are the sole source of every invalid value
- **C.** Document the risk in the readme so future builders know to be careful around that field
- **D.** Add database rules that reject impossible values, so bad data can't enter no matter the path  ✅

> **Answer:** D

### Q25. Which principle should guide every data modeling decision you direct your AI agent to make?

- **A.** The schema is the foundation; model the business truthfully now, because data outlives the code  ✅
- **B.** Speed first: ship any structure that works today and let future teams remodel around growth
- **C.** Flexibility first: keep everything as unstructured text so no decision is ever locked in
- **D.** Minimalism first: the fewest possible tables wins, since every table adds cost and risk

> **Answer:** A


---
_Take it in the browser: https://the-faction.mn.co/posts/105097150_
