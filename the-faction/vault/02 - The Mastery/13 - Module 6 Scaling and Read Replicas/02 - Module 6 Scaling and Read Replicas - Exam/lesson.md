---
course: "The Mastery"
module: "Module 6: Scaling and Read Replicas"
lesson: "Module 6: Scaling and Read Replicas — Exam"
type: "course_quiz"
post_id: 105097995
space_id: 24191170
source: "https://the-faction.mn.co/posts/105097995"
updated: "2026-08-10T20:44:09Z"
---

# Module 6: Scaling and Read Replicas — Exam

> Exam for **Module 6: Scaling and Read Replicas** (The Mastery) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. Your app is slowing under load. What should happen before any scaling decision?

- **A.** Doubling the server size immediately, since capacity is cheaper than any investigation time
- **B.** Adding a caching layer everywhere, since caches help regardless of the actual cause
- **C.** Rewriting the app in a faster language, since code speed is the root of database load
- **D.** Measuring where the load actually comes from, since scaling the wrong layer buys nothing  ✅

> **Answer:** D

### Q2. What is vertical scaling for a database?

- **A.** Stacking replicas in the same rack so network distance between the copies approaches zero
- **B.** Moving tables into a column-oriented engine, which stores data vertically by design
- **C.** Giving the existing server more power: more CPU, more memory, or faster storage  ✅
- **D.** Distributing rows across servers by date, with newer data on taller hardware tiers

> **Answer:** C

### Q3. What is a read replica?

- **A.** A cached copy of your most frequent query results, refreshed on a fixed schedule
- **B.** A continuously synced copy of the database that serves reads, taking load off the primary  ✅
- **C.** A backup restored monthly for analysts, isolated completely from live replication
- **D.** A second app server that reads from the same database over a dedicated connection

> **Answer:** B

### Q4. Which workload is the classic first candidate to move onto a read replica?

- **A.** Heavy reporting and analytics queries that compete with customer traffic on the primary  ✅
- **B.** Password verification, since login reads are the most frequent query in most apps
- **C.** Payment writes, since financial transactions deserve the most isolated infrastructure available
- **D.** Schema migrations, since structural changes run fastest on read-optimized copies

> **Answer:** A

### Q5. What is replication lag, and why must your app's design respect it?

- **A.** The license delay before a new replica may serve traffic, set by the database vendor itself
- **B.** The startup time of a new replica, which caps how fast you can scale reads upward
- **C.** Clock drift between servers, which corrupts timestamps unless synchronized nightly
- **D.** Replicas trail the primary slightly, so a read right after a write may not see that write  ✅

> **Answer:** D

### Q6. A user saves a change, the page reloads from a replica, and their change is missing. What pattern fixes this?

- **A.** Slowing page reloads by a fixed two seconds, giving the replication layer time to catch up
- **B.** Read-your-own-writes: route that user's next reads to the primary until replicas catch up  ✅
- **C.** Disabling replicas during business hours, when users are most likely to notice gaps
- **D.** Showing a warning banner that recent changes may take a minute to appear anywhere

> **Answer:** B

### Q7. What is connection pooling, and why does it matter as you scale?

- **A.** Reusing a managed set of database connections, since opening one per request overwhelms it  ✅
- **B.** Sharing one login across all services, reducing the credentials that need rotation
- **C.** Grouping users by region into pools, so each pool's queries stay on nearby servers
- **D.** Batching every query into hourly pools, trading latency for far higher throughput

> **Answer:** A

### Q8. When does vertical scaling stop being the right answer?

- **A.** Immediately; serious applications should never scale by resizing a single machine
- **B.** When the vendor's invoice arrives, since bigger machines are always the costliest path
- **C.** When you near the ceiling of one machine, or one machine becomes an availability risk  ✅
- **D.** After the first slow query appears, the signal that a machine has reached its limit

> **Answer:** C

### Q9. Your AI proposes caching to cut database load. What must every cache entry have?

- **A.** A defined invalidation story: when it expires or updates, so users don't see stale data forever  ✅
- **B.** A backup copy in the database, so cache failures can be restored like any other table
- **C.** An owner on the team roster, accountable for that entry's hit rate in weekly reviews
- **D.** Encryption at rest, since caches are legally databases in most data protection law

> **Answer:** A

### Q10. The primary database fails. What determines whether users notice?

- **A.** The size of the database, since smaller datasets restart quickly enough to hide outages
- **B.** The time of day, since failures outside business hours are absorbed by low traffic
- **C.** The vendor's status page cadence, which sets how fast the incident becomes public
- **D.** Failover design: whether a replica is promoted quickly and the app reconnects to it  ✅

> **Answer:** D

### Q11. What is sharding, and why treat it as a last resort for most AI-built apps?

- **A.** Compressing old rows into cold storage; a last resort since retrieval becomes slow
- **B.** Renting capacity from other tenants; a last resort since neighbors affect your speed
- **C.** Splitting data across databases; powerful but adds complexity most apps never need  ✅
- **D.** Duplicating the primary in another region; a last resort due to bandwidth pricing

> **Answer:** C

### Q12. Traffic spikes every day at noon and the database struggles for twenty minutes. What is the measured response?

- **A.** Provision for the peak permanently, accepting idle capacity as the cost of stability
- **B.** Identify what the spike actually does, then target it: cache it, replicate it, or queue it  ✅
- **C.** Rate-limit lunchtime users, spreading the demand into the quieter afternoon hours
- **D.** Move the database to a timezone where noon arrives during the app's quietest period

> **Answer:** B

### Q13. Which metric most directly tells you the database itself is the bottleneck?

- **A.** Query latency and connection saturation rising while app server capacity sits unused  ✅
- **B.** The monthly bill rising, since database cost tracks load more precisely than metrics
- **C.** Support tickets doubling, since users detect database strain before dashboards do
- **D.** Disk usage crossing fifty percent, which is the threshold where engines begin to degrade

> **Answer:** A

### Q14. Your analytics vendor wants to run heavy queries hourly. Where do you point them, and why?

- **A.** The primary, since analytics accuracy requires the freshest possible data at all times
- **B.** A nightly export emailed as spreadsheets, keeping vendors out of infrastructure entirely
- **C.** A replica or dedicated analytics copy, so their load can never degrade customer traffic  ✅
- **D.** The staging environment, since its data is close enough for third-party reporting

> **Answer:** C

### Q15. What quietly breaks when you add replicas but keep sending every read to the primary?

- **A.** The replicas corrupt from idleness, since replication requires steady daily read traffic
- **B.** Nothing improves; you're paying for capacity the application was never wired to use  ✅
- **C.** The primary slows further, since each idle replica adds synchronization overhead
- **D.** Failover stops working, since promotion requires replicas that serve live reads

> **Answer:** B

### Q16. How should the decision between scaling up and scaling out be framed for a growing app?

- **A.** Scale out immediately, since horizontal architecture is the mark of professional systems
- **B.** Whichever the AI recommends, since agents observe load patterns humans can't see
- **C.** Always up first, always out second, in fixed order regardless of the workload shape
- **D.** Match the fix to the constraint: a bigger machine for raw capacity, more machines for resilience  ✅

> **Answer:** D

### Q17. What is the risk of autoscaling the database tier aggressively on cost triggers?

- **A.** Scale-downs can hit during real demand, trading user experience for small savings  ✅
- **B.** Autoscaling voids most uptime guarantees, since vendors can't warrant moving targets
- **C.** Each scale event renumbers the tables, breaking queries that reference them by position
- **D.** None; autoscaling is strictly superior to any capacity plan a human could write out

> **Answer:** A

### Q18. A background job now takes six hours and slows the app while it runs. What is the architectural read?

- **A.** Six hours is fine for background work; by definition it isn't affecting any real users
- **B.** Heavy batch work is competing with live traffic and belongs on separate capacity or a replica  ✅
- **C.** The job needs a progress bar, since perceived slowness is the actual complaint here
- **D.** The app should pause during the job, converting all silent slowness into a visibly honest outage

> **Answer:** B

### Q19. What should be true before you trust a replica for failover, not just for reads?

- **A.** It must run in the same rack as the primary, since promotion requires true physical adjacency
- **B.** It must be at least thirty days old, since young replicas fail the promotion checks
- **C.** You've tested promotion: the replica actually took over in a drill and the app followed it  ✅
- **D.** It must be larger than the primary, since promoted replicas absorb recovery traffic

> **Answer:** C

### Q20. Where do most scaling problems in AI-built apps actually originate?

- **A.** Inefficient queries and missing indexes, not insufficient hardware underneath them  ✅
- **B.** The hosting provider's network, which throttles growing apps to sell them larger plans
- **C.** User behavior, since customers refresh pages far more than any design anticipates
- **D.** The programming language, since interpreted languages cap database throughput

> **Answer:** A

### Q21. What does "the database is a single point of failure" mean for a launched product?

- **A.** The database is the only component that can fail, since app servers are stateless
- **B.** One database license covers the company, so a billing lapse stops everything all at once
- **C.** All engineers depend on one schema, so a bad migration idles the entire team
- **D.** If that one system goes down, everything goes down; resilience requires a tested second  ✅

> **Answer:** D

### Q22. Your AI recommends a queue between the app and the database for write spikes. What trade are you accepting?

- **A.** Queues double storage costs, since every write exists twice until it is confirmed
- **B.** Queued writes can't be validated, so bad data reaches the database more easily
- **C.** Writes become eventual rather than instant, and the app must reflect that honestly  ✅
- **D.** The queue vendor gains read access to your data, expanding your trust boundary outward

> **Answer:** C

### Q23. When is it correct to do nothing about scaling?

- **A.** Never; capacity work should always run ahead of growth by at least two full quarters
- **B.** When measurements show headroom and projections say growth won't consume it soon  ✅
- **C.** When the app is under two years old, since young products rarely see real load
- **D.** When using a managed database, since the platform absorbs all scaling concerns

> **Answer:** B

### Q24. What is the honest cost of every added replica, cache, and queue?

- **A.** Only money; managed platforms have reduced added components to pure billing entries
- **B.** Vendor lock-in; each component ties the stack more tightly to a single provider
- **C.** Latency; every additional component slows down the very system it was intended to speed up
- **D.** Complexity: more parts to monitor, more failure modes, more places for state to disagree  ✅

> **Answer:** D

### Q25. Which principle should govern every scaling decision you direct?

- **A.** Measure first, scale the proven constraint, and prefer the simplest fix that buys real headroom  ✅
- **B.** Build for a million users on day one, since re-architecting later is always costlier
- **C.** Add capacity on a calendar schedule, since predictable spending beats measurement
- **D.** Scale whatever the loudest customer complains about, since perception is performance

> **Answer:** A


---
_Take it in the browser: https://the-faction.mn.co/posts/105097995_
