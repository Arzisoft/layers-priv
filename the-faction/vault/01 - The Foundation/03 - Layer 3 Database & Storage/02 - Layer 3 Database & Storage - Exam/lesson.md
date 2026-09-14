---
course: "The Foundation"
module: "Layer 3: Database & Storage"
lesson: "Layer 3: Database & Storage — Exam"
type: "course_quiz"
post_id: 102901435
space_id: 23777123
source: "https://the-faction.mn.co/posts/102901435"
updated: "2026-08-20T23:45:19Z"
---

# Layer 3: Database & Storage — Exam

> Exam for **Layer 3: Database & Storage** (The Foundation) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. AI built a tutoring app database with 'tutors' and 'students' tables but no bookings table. Lessons are stored as text inside the student table. What schema problem does this create?

- **A.** The text field approach is actually more flexible than structured tables and easier to keep working as the app grows, since any lesson detail can be recorded freely
- **B.** Bookings need their own table with typed columns (date, time, tutor_id, student_id) — text fields can't be searched, sorted, filtered, or validated properly  ✅
- **C.** The database engine only supports a maximum of two tables per project, so adding a third bookings table is simply not possible with this kind of setup
- **D.** Bookings data should be stored in a completely separate database from the tutors and students so that heavy lesson traffic never slows down the main application tables

> **Answer:** B

### Q2. Your AI-built invoicing app stores amounts as text. When sorting, '$1,000' appears before '$200' because text sorts alphabetically. What data type problem is this?

- **A.** Text-based sorting is actually the correct approach for handling and displaying financial data, because it keeps currency symbols attached to the values
- **B.** The amount column should use a numeric type like DECIMAL so values sort, sum, and compare correctly — storing prices as text breaks sorting and math  ✅
- **C.** The dollar sign character should be stripped out of the text before performing any sort operations, so the remaining digits can sort in a cleaner order
- **D.** A separate sort-order column should be added to the table and maintained by hand so that the invoices can be displayed in the correct numeric sequence

> **Answer:** B

### Q3. Your e-commerce app has customers and orders tables, but orders have no customer_id column. There's no way to know which customer placed which order. What's missing?

- **A.** The orders table should store each customer's full name as a plain text field inside every order record instead of using any linking column
- **B.** Customer and order data should be combined together into one single wide table so that the app never has to join two tables to answer a question
- **C.** A relationship — orders need a customer_id foreign key column that links each order to the customer who placed it, connecting the tables  ✅
- **D.** Orders do not actually need to be linked back to customers at all, because each order can stand alone as a fully independent record in the system

> **Answer:** C

### Q4. Users are creating duplicate accounts with the same email because the database allows duplicate values. What is missing from the schema?

- **A.** A longer email column with much more character capacity, which would help prevent the user typos and data entry errors that create duplicates
- **B.** A unique constraint on email that prevents the database from accepting a new record if that email value already exists in the table  ✅
- **C.** Frontend validation logic that checks the database for existing duplicate emails before the signup form is ever allowed to submit
- **D.** A manual deduplication cleanup process that an administrator runs on a weekly schedule to find and merge any repeated accounts it discovers

> **Answer:** B

### Q5. Your registration form requires name, email, and phone. But all three database columns are nullable. Users are created with just an email. What should change?

- **A.** Name and email should be NOT NULL in the schema since business rules require them — phone can stay optional if not needed for registration  ✅
- **B.** All of the columns should always remain nullable to provide maximum flexibility for whatever future changes the product might need
- **C.** Only the frontend form should enforce which fields are required, never the database layer that actually sits underneath the application
- **D.** Required field enforcement should only ever be handled at the API layer, because the database level is entirely the wrong place to keep business rules

> **Answer:** A

### Q6. AI returned 15 customers for a 'show orders this month' query. You're unsure the results are right. How should you verify the data?

- **A.** Check the frontend display to see if fifteen orders appear on the screen and assume the query results match what the app is showing
- **B.** Trust the query results without question because AI tools would never return incorrect or incomplete data from a working database
- **C.** Ask AI to run the exact same query one more time — if it returns identical results on the second run, the numbers must have been correct all along
- **D.** Open your database viewer, browse the orders table directly, filter by this month's dates, count records, and cross-reference with query results  ✅

> **Answer:** D

### Q7. You deleted a customer but their 15 orders remain with a customer_id that matches no one. These orphaned orders cause app errors. What should the database have done?

- **A.** The related orders should have been automatically deleted for you, or the customer deletion should have been blocked by the app's settings menu
- **B.** Orders should store the customer's full name as plain text instead of using a customer_id reference that can end up pointing at nobody
- **C.** A cascading rule: CASCADE (auto-delete orders) or RESTRICT (block deleting a customer with orders). Without either rule, you get orphaned data.  ✅
- **D.** The customer record should simply have been marked as inactive instead of being permanently deleted from the customers table in the first place by the app

> **Answer:** C

### Q8. AI built a recipe app database. Recipes have no user_id link to authors, and ingredients are stored as comma-separated text. What should you tell AI to fix?

- **A.** Add a user_id foreign key to recipes for author linking, and create a separate ingredients table with individual rows per ingredient — so they can be searched and filtered individually  ✅
- **B.** The schema actually looks fine as designed — comma-separated ingredient values are an efficient storage approach that keeps every recipe compact inside one single row
- **C.** Move all of the recipe, author, and ingredient data into one single table for simplicity, since having fewer tables in the schema means fewer things that can possibly break
- **D.** The database dashboard is probably just displaying incorrect data — the actual schema underneath is likely fine, so refresh the view and rebuild the dashboard before changing anything else

> **Answer:** A

### Q9. A co-founder asks: 'Why can't we use a spreadsheet instead of a database? Both have rows and columns.' What's the key difference for apps?

- **A.** Databases can only store numeric values while spreadsheets can also hold text, and that storage limitation is the main functional difference between the two of them
- **B.** Databases are more expensive to run than spreadsheets, and that higher monthly cost is essentially what makes them the better choice for serious companies
- **C.** There is no meaningful difference between the two — spreadsheets actually work perfectly fine as the production data store for real apps, and plenty of teams never migrate off them
- **D.** A database enforces data types, prevents duplicates, maintains table relationships, handles concurrent users, and responds to app requests automatically — unlike spreadsheets  ✅

> **Answer:** D

### Q10. AI created a user profiles table where every column (name, email, age, created_at, is_active) is VARCHAR. What schema problem do you see?

- **A.** Using VARCHAR for every single column is actually considered a best practice because text types provide the maximum possible flexibility for later changes
- **B.** VARCHAR is perfectly acceptable in this case because the frontend application layer will handle all of the data type enforcement on its behalf
- **C.** The profiles table simply has too many columns defined for one table — it should be split apart and simplified down to just a small handful of fields in total
- **D.** Wrong types: age should be INTEGER, created_at TIMESTAMP, is_active BOOLEAN. Text for everything removes all validation — 'banana' could be stored as an age.  ✅

> **Answer:** D

### Q11. Your app uses PostgreSQL. A friend uses MongoDB. They ask which is better. What is the correct comparison?

- **A.** PostgreSQL is universally superior for every possible use case — there is no legitimate reason for any project anywhere to ever choose MongoDB instead
- **B.** SQL (PostgreSQL) uses structured tables with relationships — ideal for app data. NoSQL (MongoDB) stores flexible documents. For most AI-built apps, SQL is the right default.  ✅
- **C.** MongoDB is always the better choice because it is the newer technology, and a more modern document architecture automatically beats an older relational one
- **D.** Both database systems are essentially identical in every way that matters — the product name printed on the label is really the only meaningful difference between the two of them

> **Answer:** B

### Q12. Three orders have customer_id values matching no customer. These orphaned records cause app errors. How could this have been prevented?

- **A.** By configuring the foreign key constraint properly — the database should reject any order with a customer_id that doesn't exist in the customers table, preventing orphans  ✅
- **B.** By manually double-checking every customer_id value by hand before each database insert operation is executed against the orders table in production
- **C.** By storing the customer's full name in the orders table as a plain text value instead of using a customer_id field that has to match a row in another table
- **D.** By running a nightly automated cleanup job that scans the orders table and deletes any order rows whose customer_id values no longer match any existing customer record at all

> **Answer:** A

### Q13. AI built a database from your description. You want to verify it's correct. What is the first thing you should do?

- **A.** Trust that AI built the schema correctly this time and move directly on to building the frontend interface so that the project keeps up its momentum
- **B.** Start adding real customer data immediately so you can find out whether anything breaks once the tables are being used for actual day-to-day work
- **C.** Open a database viewer, inspect AI's tables, check column types and constraints, verify relationships exist, create test records, and confirm data saves and loads  ✅
- **D.** Ask AI to self-confirm that the schema it just generated is structured correctly and complete, and then simply accept its own answer as your entire verification step

> **Answer:** C

### Q14. After a month of building, you finally open the database and find hundreds of duplicates, missing relationships, and wrong data types. What pitfall is this?

- **A.** Not testing the application interface on real mobile devices before launching the product out to the production users who depend on it
- **B.** Never looking at your actual data — trusting AI's database setup without opening a viewer to inspect tables, relationships, and data quality  ✅
- **C.** Selecting the wrong database provider for your application's specific use case, its expected growth pattern, and its storage requirements
- **D.** Not writing a comprehensive automated unit test suite that covers every single database operation the application performs during regular use

> **Answer:** B

### Q15. A server failure wipes your production database. There are no backups. All 2,000 users' data is permanently lost. What pitfall caused this?

- **A.** No backups — or untested ones. A backup you've never restored is just a feel-good file. You need automated backups AND tested restore procedures.  ✅
- **B.** Choosing the wrong hosting provider — a better quality host would have prevented this kind of total server failure from ever happening to you
- **C.** The server failure was an unprecedented event that no reasonable person could realistically have planned for or protected against in advance
- **D.** All modern databases already ship with automatic backups enabled by default, so a total loss scenario like this one is simply not possible anymore

> **Answer:** A

### Q16. AI stored profile photos as binary data in the database. After 1,000 uploads, it grew from 50MB to 15GB and queries slowed. What should have been done differently?

- **A.** Limit each user to only one profile photo upload apiece so that the total size of the database always stays manageable as the user base grows
- **B.** Compress every image down to a much smaller file size before storing it as binary data in the database so that the table grows far more slowly
- **C.** Upgrade to a larger and more powerful database server with plenty of extra disk space so it can easily handle the increased storage demands from the photo uploads
- **D.** Store files in a dedicated service (like Supabase Storage or S3) and save only the URL in the database — databases are for structured data, not large files  ✅

> **Answer:** D

### Q17. Your app worked fine with 50 test records but search takes 15 seconds with 5,000 users. What did you fail to consider about data growth?

- **A.** Five thousand users is simply too many for any standard database system to handle effectively, so slowdowns at this size are completely expected behavior
- **B.** The search feature should be removed entirely from the app because a fifteen-second wait means it is far too slow for anyone to realistically use day to day
- **C.** Without indexes on searched columns, the database scans every row. 50 records = instant; 50,000 = painfully slow. You should have asked AI to add indexes on search columns.  ✅
- **D.** You need to switch over to a completely different database technology that supports much faster queries, since your current one has clearly reached its practical scaling limit

> **Answer:** C

### Q18. No unique constraint on email. 47 users created duplicate accounts. Login breaks, password resets fail. What should have been in place from the start?

- **A.** A manual email verification process that requires a member of the administrative team to review each new signup before the account gets created
- **B.** A weekly automated cleanup script that finds and removes all of the duplicate accounts that appeared in the system during the previous seven days
- **C.** Frontend validation code that checks the users table for existing duplicates before allowing the account creation request to go through from the signup form itself
- **D.** A unique constraint on email preventing duplicate values — making it impossible for two accounts to share the same address, catching duplicates at the data layer  ✅

> **Answer:** D

### Q19. You manually added a NOT NULL phone_number column to production with no default value. 500 existing records violate the constraint and the app crashes. What should you have done?

- **A.** Used a migration — a testable database change verified in dev first, with a default value for existing records or a nullable column initially  ✅
- **B.** Added the column as NOT NULL anyway — the resulting crash is actually a hosting configuration issue rather than any kind of schema problem
- **C.** Deleted all of the existing user records from the database before adding the new required column so that nothing could possibly violate it
- **D.** Made the exact same schema change but scheduled it to run during off-peak hours so that far fewer active users would actually feel the resulting impact

> **Answer:** A

### Q20. You want AI to create a database for a pet-sitting app. Which description would produce the best schema?

- **A.** A vague prompt like 'build me a database for a pet-sitting app' that leaves every column and data type decision entirely up to the AI
- **B.** A detailed prompt specifying tables, columns, types, constraints (UNIQUE, NOT NULL), relationships (REFERENCES), and indexes on searchable columns  ✅
- **C.** A generic request like 'I need tables for the pet-sitting app data' with no further specifics about the columns or the relationships
- **D.** A platform-only prompt like 'set up Supabase for my project' that names the hosting platform but includes no actual schema details of any kind at all

> **Answer:** B

### Q21. AI created a products table where price, weight, in_stock, and created_at are all VARCHAR. What problems should you flag?

- **A.** Wrong types: price should be DECIMAL, weight NUMERIC, in_stock BOOLEAN, created_at TIMESTAMP. VARCHAR for everything prevents sorting, calculations, and validation.  ✅
- **B.** The table appears correctly structured just as delivered — VARCHAR is an acceptable default type for every column in a modern products table
- **C.** Only the price column actually has the wrong data type here — the other VARCHAR columns in the table are all perfectly acceptable as they stand
- **D.** UUID is the wrong type for the id column — it should be swapped out for a simple auto-incrementing integer before anything else in this table gets looked at or fixed

> **Answer:** A

### Q22. You inserted a user with 'test@example.com', then tried inserting another with the same email. The database rejected it. What did you just test successfully?

- **A.** That your database has a unique constraint on email that prevents duplicates — confirming this data-layer protection is working correctly  ✅
- **B.** That the database server is online, fully operational, and currently accepting new inbound connections from your running application
- **C.** That the database is validating the email format by itself and rejecting improperly structured email addresses before they can save
- **D.** That the database engine is able to hold more than one record at a time and is not limited to storing just a single entry in each one of its tables

> **Answer:** A

### Q23. Your database was deleted during migration. You restored from a Supabase backup — all 3,200 records recovered in 30 minutes. What made this possible?

- **A.** Having a premium hosting provider with high reliability guarantees and unusually strong underlying server infrastructure behind it
- **B.** Having a simple application with very few tables, which made the restoration process much faster than it otherwise would have been
- **C.** Having a small database with a limited number of records that are quick and easy to restore from almost any backup source that you might have available
- **D.** Automated backups AND a tested restore process — knowing your backups work and that you can restore from them is what made recovery possible  ✅

> **Answer:** D

### Q24. Your co-founder says never delete customers — mark them inactive. If hard-deleted, preserve their orders for accounting. How do you describe this to AI?

- **A.** Tell AI to cascade-delete everything related to a customer whenever that customer is removed, so their orders disappear from the accounting reports along with them
- **B.** Don't bother describing deletion rules at all — customer deletions happen so rarely in a real business that they simply aren't worth planning for in the schema
- **C.** Tell AI to use soft deletion (is_active flag) for customers, and SET NULL on the orders foreign key — so hard-deleted customers' orders remain with a null customer_id for accounting  ✅
- **D.** Store a full duplicated copy of the customer's data inside every individual order record as a safeguard, so that the accounting numbers survive whatever happens later to the customers table

> **Answer:** C

### Q25. Product search takes 8 seconds. The query analyzer shows a full scan of 50,000 rows because the name column has no index. What should you do?

- **A.** Purchase a faster and much more powerful database server with higher processing capacity so that the very same full scan finishes in less time
- **B.** Remove the product search feature entirely from the application, since eight seconds for every search means it is far too slow to keep around
- **C.** Ask AI to add an index on name (and other searched columns) — indexes let the database find matches without scanning every row, dramatically improving speed  ✅
- **D.** Reduce the total number of products that are stored in the database so that there are far fewer rows for the slow search query to scan through on each request

> **Answer:** C


---
_Take it in the browser: https://the-faction.mn.co/posts/102901435_
