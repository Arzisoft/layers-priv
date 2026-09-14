---
course: "The Vault"
module: "Module 3 — Protecting Your Database"
lesson: "Module 3: Protecting Your Database — Exam"
type: "course_quiz"
post_id: 104378498
space_id: 24302166
source: "https://the-faction.mn.co/posts/104378498"
updated: "2026-08-27T20:10:51Z"
---

# Module 3: Protecting Your Database — Exam

> Exam for **Module 3 — Protecting Your Database** (The Vault) — 25 questions. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. Your AI-built application constructs a database query by concatenating user input directly into the SQL string. An attacker enters a crafted string in the search field and extracts your entire user table. What vulnerability is this?

- **A.** SQL Injection — user input concatenated into query strings lets attackers modify the SQL logic to read, change, or delete database contents  ✅
- **B.** Cross-Site Scripting — the search input is reflected back to the browser and executed as JavaScript code in the attacker's current session
- **C.** Command Injection — the search input is passed to the operating system shell where it executes as a system-level command on your server
- **D.** NoSQL Injection — the query syntax targets document databases like MongoDB using JSON-based operators to bypass query filter conditions

> **Answer:** A

### Q2. Your AI tool generated database queries using an ORM. A security auditor finds one endpoint where the developer bypassed the ORM and wrote raw SQL with string interpolation. Why does this single endpoint matter?

- **A.** Raw SQL queries perform better than ORM-generated queries so the developer made a valid optimization choice for that specific high-traffic endpoint
- **B.** One unparameterized query is enough for a full database breach — SQL injection only needs a single vulnerable entry point to compromise everything  ✅
- **C.** The ORM and raw SQL use different database connections so the raw query operates with separate credentials that limit the potential breach scope
- **D.** Raw SQL queries are acceptable as long as the endpoint is only accessible to authenticated admin users who are trusted with database-level access

> **Answer:** B

### Q3. Your application connects to the production database using the root account with full administrative privileges. The application only needs to read and write to three specific tables. What security principle is being violated?

- **A.** Connection pooling — the root account creates a single shared connection instead of managing a pool of limited-privilege individual connections
- **B.** Credential rotation — the root account password is typically never changed because rotating it would require updating all dependent service connections
- **C.** Least privilege — the application should use a dedicated database user with permissions limited to only the specific tables and operations it needs  ✅
- **D.** Separation of duties — the root account should be split into separate read-only and write-only accounts for different application functionality paths

> **Answer:** C

### Q4. Your database stores user passwords as MD5 hashes. A security reviewer explains that an attacker with a GPU can compute billions of MD5 hashes per second. What hashing algorithm should replace MD5?

- **A.** SHA-256 which produces a longer hash output that is more resistant to collision attacks and is the current standard for data integrity verification
- **B.** SHA-512 which doubles the hash length compared to SHA-256 making it exponentially more difficult for attackers to reverse the hash to plain text
- **C.** AES-256 encryption which converts passwords to ciphertext that can only be decrypted with the correct encryption key stored separately on the server
- **D.** bcrypt or Argon2 which are deliberately slow algorithms designed specifically for password hashing that resist GPU-based brute force attacks effectively  ✅

> **Answer:** D

### Q5. You check your cloud database configuration and find the database is listening on a public IP address with port 5432 open to all incoming traffic. Your application server connects from a single known IP. What should change?

- **A.** Restrict database access to only your application server's IP address — the database port should never accept connections from the public internet  ✅
- **B.** Add a strong password to the database which is sufficient protection since attackers cannot connect without the correct authentication credentials
- **C.** Change the database port from the default 5432 to a non-standard port number so automated scanners do not detect the database service running
- **D.** Enable SSL on the database connection to encrypt all traffic between the application and database which prevents interception of credentials in transit

> **Answer:** A

### Q6. Your nightly database backup is stored as an unencrypted SQL dump file in an S3 bucket. The bucket permissions allow public read access. Anyone who finds the URL can download your entire database. What are the two problems?

- **A.** The backup frequency should be increased to hourly so that the publicly accessible backup always contains the most current version of all data records
- **B.** The SQL dump format is inefficient for large databases and should be replaced with a binary backup format that compresses the data more effectively
- **C.** Backups must be encrypted at rest and stored with restricted access controls — public S3 buckets containing database dumps are a critical data exposure  ✅
- **D.** The backup should be stored in a different cloud region from the production database to provide geographic redundancy in case of regional service outages

> **Answer:** C

### Q7. Your application logs database queries for debugging. The log entries contain the full SQL including parameter values. A log entry reads: SELECT * FROM users WHERE ssn = '123-45-6789'. What is being exposed?

- **A.** Query structure information that reveals your database table names and column names which helps attackers understand your data model architecture
- **B.** Sensitive user data in log files — Social Security numbers and other PII in query logs create a secondary data exposure outside the database itself  ✅
- **C.** Database performance metrics since full query logging increases disk usage and slows database response times during high-traffic periods significantly
- **D.** Debug information that should only appear when the application runs in development mode and is automatically suppressed in production environments

> **Answer:** B

### Q8. Your application allows users to search by name using a text input. The backend constructs the query as: WHERE name LIKE '%' + userInput + '%'. An attacker enters a LIKE pattern that causes the database to perform a full table scan on 10 million records. What is the performance attack?

- **A.** The LIKE operator is inherently unsafe for user-facing search and should be replaced with full-text search indexes for all text query operations always
- **B.** Adding a query timeout of 5 seconds would prevent the full table scan from completing and protect the database from sustained performance degradation
- **C.** The database query optimizer should automatically detect expensive LIKE patterns and reject them before execution to protect server resource utilization
- **D.** ReDoS-style query abuse — crafted input forces expensive operations consuming database resources, potentially causing denial of service for all users  ✅

> **Answer:** D

### Q9. Your database has no audit logging enabled. An administrator suspects that a former employee accessed customer records before their departure. There is no evidence to confirm or deny the access. What should have been enabled?

- **A.** Database audit logging that records which users accessed which tables and rows, when, and what operations they performed for accountability and compliance  ✅
- **B.** Application-level access logging that tracks user interface interactions like page views and button clicks which can imply database access patterns indirectly
- **C.** Network packet logging on the database server that captures all TCP connections and can be analyzed to reconstruct database query activity after the fact
- **D.** Regular database snapshots taken every hour that can be compared to identify which records were viewed or modified between consecutive snapshot intervals

> **Answer:** A

### Q10. Your AI tool created a database migration that drops a column containing customer addresses. After deploying to production, you realize the column was still needed by a reporting feature. The data is permanently gone. What migration practice was skipped?

- **A.** A code review process where another developer verifies the migration script before it runs against any environment including development and staging
- **B.** A database backup taken immediately before the migration so the dropped column data could be restored from the pre-migration backup if problems arise
- **C.** A feature flag that disables the reporting feature before the migration runs so users do not encounter errors from the missing column during the transition
- **D.** Testing on staging with production-like data first — destructive migrations must be validated against realistic data before running on production databases  ✅

> **Answer:** D

### Q11. Your database stores credit card numbers in plain text for a subscription billing feature. A security audit flags this as a PCI DSS violation. Your team says they need the full card number for recurring charges. What is the correct approach?

- **A.** Encrypt the credit card numbers using AES-256 encryption with the decryption key stored in the application's environment variables for secure access
- **B.** Hash the credit card numbers using bcrypt so they cannot be reversed but can still be compared against new card submissions for duplicate detection
- **C.** Use a payment processor's tokenization — store a token that references the card at the processor instead of storing the actual card number yourself  ✅
- **D.** Store only the last four digits of the card number for display purposes and require customers to re-enter their full card number for each billing cycle

> **Answer:** C

### Q12. Your application uses a single database for all environments: development, staging, and production. A developer accidentally deletes test records that turn out to be real customer data. What environment practice was missing?

- **A.** Role-based database access that restricts developer accounts to read-only permissions on all tables to prevent accidental data modification or deletion
- **B.** Separate databases per environment — development and staging should use synthetic data so developer actions never touch real production customer records  ✅
- **C.** A soft-delete mechanism that marks records as deleted without actually removing them from the database so they can be recovered by an administrator later
- **D.** A mandatory confirmation prompt before any delete operation that requires the developer to type the record identifier to confirm intentional deletion

> **Answer:** B

### Q13. Your database connection string is hardcoded in your application's source code and committed to a public GitHub repository. You rotate the database password immediately. Is the problem fully resolved?

- **A.** No — the old credential is still in Git history. Anyone who cloned the repo before rotation has it. Rotate credentials AND audit for unauthorized access  ✅
- **B.** Yes — rotating the password invalidates the exposed credential and since the repository is public the old password is no longer useful to any attacker
- **C.** Partially — the password is rotated but you also need to delete the commit containing the old password from the Git history using a force push command
- **D.** No — you need to take the database offline temporarily and migrate all data to a new database instance with completely fresh credentials and configuration

> **Answer:** A

### Q14. Your database has a users table with 50,000 records. Every query from the application runs as SELECT * FROM users even when only the user's name is needed. What are the security and performance implications?

- **A.** SELECT * queries are standard practice during development and should only be replaced with specific column selections during production optimization phases
- **B.** Over-fetching exposes all columns including sensitive fields to the application layer — specify only needed columns to minimize data in memory and in transit  ✅
- **C.** The database query optimizer automatically reduces SELECT * to only the indexed columns so the full table scan is avoided regardless of the query structure
- **D.** Application frameworks filter sensitive columns from the result set before returning data to the calling function so SELECT * is safe at the database level

> **Answer:** B

### Q15. Your application stores user sessions in the database. The sessions table has grown to 5 million rows because expired sessions are never cleaned up. Login queries are slowing down. What maintenance is missing?

- **A.** Add database indexes on the sessions table to improve query performance regardless of table size so expired sessions do not impact active session lookups
- **B.** Partition the sessions table by date so queries only scan the partition containing recent sessions and older partitions are ignored automatically by default
- **C.** Switch from database-backed sessions to JWT tokens stored on the client so the server does not need to maintain any session state in the database at all
- **D.** Automated session cleanup that purges expired sessions on a schedule — unbounded table growth degrades performance and wastes storage on unusable records  ✅

> **Answer:** D

### Q16. Your database accepts connections using TLS 1.0 which has known vulnerabilities. A security scan flags this as a weak transport configuration. What should the minimum accepted TLS version be?

- **A.** TLS 1.0 is acceptable for internal database connections that do not traverse the public internet since the traffic stays within your private network
- **B.** TLS 1.1 which resolved the most critical vulnerabilities in TLS 1.0 while maintaining broad compatibility with older database client libraries and drivers
- **C.** TLS 1.2 minimum — both TLS 1.0 and 1.1 have known vulnerabilities and are deprecated by industry standards and major cloud providers for all connections  ✅
- **D.** TLS 1.3 exclusively which provides the strongest encryption but may require database driver updates that could temporarily break existing application connections

> **Answer:** C

### Q17. Your database schema includes a column called is_admin as a boolean on the users table. There is no separate roles or permissions table. An attacker who gains write access to the users table can set any user's is_admin to true. What schema pattern is more secure?

- **A.** A separate roles and permissions table with database-enforced constraints — role assignments should not be a simple editable field on the user record  ✅
- **B.** Encrypt the is_admin column value so that even if an attacker can write to the users table they cannot set a meaningful value without the encryption key
- **C.** Add a database trigger that logs all changes to the is_admin column and sends an alert notification when the value is modified outside of normal operations
- **D.** Move the admin flag to the application config file so admin users are defined by deployment configuration rather than database records

> **Answer:** A

### Q18. Your database replication lag causes a race condition. A user changes their password on the primary database. The attacker uses the old password against a read replica that hasn't received the update yet. What is the security impact?

- **A.** Replication lag is a performance issue not a security concern because authentication queries should run against the primary database instance directly
- **B.** The old password would not work on the replica because password hashes are verified against a shared authentication cache that updates independently of replication
- **C.** Modern database replication is synchronous so both the primary and all replicas update simultaneously eliminating any window for the old password to remain valid
- **D.** Authentication queries must route to the primary database — reading from replicas with lag creates a window where revoked or changed credentials still work  ✅

> **Answer:** D

### Q19. Your database backup strategy creates daily snapshots but stores all backups in the same cloud region as the production database. A regional outage takes down both production and all backups simultaneously. What is missing?

- **A.** Cross-region backup replication — store backup copies in a different geographic region so a regional outage does not eliminate both production and recovery data  ✅
- **B.** More frequent backup intervals that create snapshots every hour instead of daily reducing the maximum data loss from 24 hours to 1 hour during any outage event
- **C.** A secondary backup system from a different vendor that runs alongside the primary backup process providing redundancy within the same geographic cloud region
- **D.** An automated failover system that promotes the most recent backup to production status within the same region when the primary database becomes unavailable

> **Answer:** A

### Q20. Your application stores user-uploaded documents in a database BLOB column alongside transactional data. The table has grown to 500GB and routine queries that don't involve documents have slowed dramatically. What should be different?

- **A.** Increase the database server's allocated memory and storage to handle the larger table size which will restore query performance to acceptable response times
- **B.** Add database indexes specifically optimized for the BLOB column to improve query performance when scanning or filtering rows that contain large document data
- **C.** Store documents in object storage like S3 and keep only a reference URL in the database — large files in database tables degrade all query performance  ✅
- **D.** Partition the table into a document partition and a transactional partition so queries that do not involve documents skip the large BLOB data automatically

> **Answer:** C

### Q21. Your database has Row-Level Security policies that restrict users to seeing only their own records. A developer creates a new reporting endpoint that queries the database with a service account that bypasses RLS. The endpoint returns all users' data. What went wrong?

- **A.** RLS policies should automatically apply to all database connections including service accounts without requiring any additional configuration for each account
- **B.** Service accounts that bypass RLS defeat the security model — reporting queries must either use RLS-bound accounts or implement equivalent filtering in code  ✅
- **C.** The reporting endpoint should use a separate read-only database replica where RLS policies are independently configured for reporting-specific access patterns
- **D.** The developer should add a WHERE clause to the reporting query that manually filters records to match what RLS would return for the requesting user's context

> **Answer:** B

### Q22. Your database stores timestamps in the application server's local timezone. Your servers are in US-East but users are worldwide. A user in Tokyo creates a record at 9am local time but the database stores it as 8pm the previous day. What is the data integrity issue?

- **A.** Display the stored timestamp with a timezone indicator so users understand that the time shown reflects the server's location rather than their own local time
- **B.** Store a separate timezone column alongside each timestamp so the application can convert the display time to the user's local timezone during rendering on screen
- **C.** Configure the application servers to use the timezone of the majority of your user base so timestamps are accurate for the largest portion of your audience
- **D.** Store all timestamps in UTC and convert to the user's local timezone only for display — UTC eliminates timezone confusion across global users and server locations  ✅

> **Answer:** D

### Q23. Your database has no foreign key constraints. An application bug deletes a user record but leaves their orders, invoices, and support tickets orphaned with no parent reference. What database integrity feature prevents this?

- **A.** Foreign key constraints with CASCADE or RESTRICT rules that prevent deleting parent records while child records still reference them in related tables  ✅
- **B.** Application-level referential integrity checks that verify all child records are handled before allowing deletion of any parent record in the user interface
- **C.** Soft delete patterns that mark records as inactive rather than physically removing them so parent-child relationships are preserved across all related tables
- **D.** Database triggers that automatically fire cleanup procedures when a parent record is deleted to remove or reassign all orphaned child records from related tables

> **Answer:** A

### Q24. Your team runs database migrations during business hours. A migration adds a new index to a table with 10 million rows. The index creation locks the table for 8 minutes. During that time, no user can read or write to that table. What should have been done differently?

- **A.** Increase the database server resources temporarily during the migration window to reduce the index creation time from 8 minutes to under 30 seconds
- **B.** Schedule the migration during a 15-minute maintenance window and notify all users that the platform will be briefly unavailable during the index creation process
- **C.** Use a concurrent index creation method that builds the index without locking the table — and schedule migrations outside business hours as standard practice  ✅
- **D.** Create the index on a database replica first and then promote the replica to primary during a brief switchover window to minimize user-facing lock duration

> **Answer:** C

### Q25. Your application's database has been running for two years without any performance optimization. Queries that took 50ms at launch now take 3 seconds. Table sizes have grown from thousands to millions of rows. What maintenance was neglected?

- **A.** The database server hardware should be upgraded every 12 months to keep pace with growing data volumes and maintain consistent query response times over time
- **B.** Regular performance maintenance — index optimization, query plan analysis, table statistics updates, and archiving historical data to keep active tables lean  ✅
- **C.** Database queries should be rewritten to use more efficient syntax since the original queries were designed for small datasets and do not scale to larger volumes
- **D.** The application should implement query result caching so frequently executed queries return cached results instead of hitting the database on every single request

> **Answer:** B


---
_Take it in the browser: https://the-faction.mn.co/posts/104378498_
