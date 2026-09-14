---
space: "The Pit"
author: "Matt Murphy"
post_id: 106569214
reactions: 0
comments: 0
published: "2026-08-30T14:00:15Z"
source: "https://the-faction.mn.co/posts/106569214"
---

# Your AI wrote queries that work. What it did not do is make them fast. Every que

Your AI wrote queries that work. What it did not do is make them fast. Every query scans every row in the table. At 500 rows, nobody notices. At 100,000 rows, your hosting provider throttles you for excessive resource usage. Today I walk through adding database indexes so queries find data instantly instead of scanning everything, restricting queries to only the fields your page actually needs, and enabling slow query logging so you can see which queries are killing your performance. If your app has been getting slower as it grows, start here.

**PROMPT:** Direct your AI: "Perform a database performance audit on my application with three components: (1) Index analysis. List every database query my application executes. For each query, identify which columns are used in WHERE clauses, JOIN conditions, ORDER BY, and GROUP BY operations. Check whether indexes exist on those columns. For any column used in a filter or lookup that does not have an index, create one. Run an EXPLAIN or query plan on each query before and after adding indexes and report the performance difference. (2) Query optimization. Audit every query for unnecessary data retrieval. Identify queries that select all columns when only a subset is needed. Identify queries that return more rows than the application uses. Rewrite each query to select only the columns the requesting feature displays and add appropriate LIMIT clauses where pagination is expected but not implemented. (3) Slow query monitoring. Enable slow query logging on my database with a threshold of 500 milliseconds. Configure it to log the full query text, execution time, rows scanned, and rows returned. Build a monitoring view that shows the top 10 slowest queries by average execution time, how frequently each runs, and the total resource consumption. Set up an alert when any query exceeds 2 seconds."

---

## Video transcript

_deepgram auto-captions (Mighty) · 2m16s_

Your database has been doing a full table scan on every single request since you launched it. You didn't even notice until your hosting provider throttled you for excessive resource usage on their platform. So your AI wrote the queries. Right? They worked, pages loaded, data showed up.

What you did not see is that every query was reading every row in the table to find the one row it needed. So at five hundred rows, that takes milliseconds, no biggie. At one hundred thousand rows, your server is doing the computational equivalent of reading every book in a library to find one title. So your hosting provider noticed before you did, started charging you for it. So your app is slow, your bill's climbing and your users, they're leaving.

Let's get it fixed. Step one, your AI never added indexes to your database. An index tells the database exactly where to find the data instead of scanning every single row. Without one, every query is a full table scan. The larger the table, the slower the request.

So direct your AI to identify every query your application is running and then determine which columns are used in filters and lookups and add those indexes to those columns. Test this before and after query speed, which is definitely gonna increase, test your actual data. Step two, your queries are pulling more data than your pages actually need. Your AI wrote queries that return every column on every matching row even when the page only displays three fields. So every unnecessary column is data your server processes and your network transmits for no reason at all.

What you need to do is direct your AI to audit every query and restrict the selected fields to only what the requesting page or features are actually using. That's a win. And step three, you have no visibility into which queries are slow. Your database has been running expensive queries since day one and you have no way to see them. Right?

Well, DirectoryAI to enable slow query logging. Set a threshold and build a dashboard that will show you which queries exceeded that threshold, how often they are running, and how much resource each one is consuming. Your database is working ten times harder than it ever needed to. So let's make sure we index it before your hosting provider shuts you down.


---
_Source: https://the-faction.mn.co/posts/106569214_
