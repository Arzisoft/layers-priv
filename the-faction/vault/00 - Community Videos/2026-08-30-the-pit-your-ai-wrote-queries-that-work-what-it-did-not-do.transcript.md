---
type: transcript
lesson: "Your AI wrote queries that work. What it did not do is make them fast. Every que"
course: "The Pit"
author: "Matt Murphy"
post_id: 106569214
published: "2026-08-30T14:00:15Z"
source_url: "https://the-faction.mn.co/posts/106569214"
duration: "2m16s"
words: 400
transcribed_by: "deepgram auto-captions (Mighty)"
---

# Transcript — Your AI wrote queries that work. What it did not do is make them fast. Every que

> Your AI wrote queries that work. What it did not do is make them fast. Every query scans every row in the table. At 500 rows, nobody notices. At 100,000 rows, your hosting provider throttles you for excessive resource usage. Today I walk through adding database indexes so queries find data instantly

Your database has been doing a full table scan on every single request since you launched it. You didn't even notice until your hosting provider throttled you for excessive resource usage on their platform. So your AI wrote the queries. Right? They worked, pages loaded, data showed up.

What you did not see is that every query was reading every row in the table to find the one row it needed. So at five hundred rows, that takes milliseconds, no biggie. At one hundred thousand rows, your server is doing the computational equivalent of reading every book in a library to find one title. So your hosting provider noticed before you did, started charging you for it. So your app is slow, your bill's climbing and your users, they're leaving.

Let's get it fixed. Step one, your AI never added indexes to your database. An index tells the database exactly where to find the data instead of scanning every single row. Without one, every query is a full table scan. The larger the table, the slower the request.

So direct your AI to identify every query your application is running and then determine which columns are used in filters and lookups and add those indexes to those columns. Test this before and after query speed, which is definitely gonna increase, test your actual data. Step two, your queries are pulling more data than your pages actually need. Your AI wrote queries that return every column on every matching row even when the page only displays three fields. So every unnecessary column is data your server processes and your network transmits for no reason at all.

What you need to do is direct your AI to audit every query and restrict the selected fields to only what the requesting page or features are actually using. That's a win. And step three, you have no visibility into which queries are slow. Your database has been running expensive queries since day one and you have no way to see them. Right?

Well, DirectoryAI to enable slow query logging. Set a threshold and build a dashboard that will show you which queries exceeded that threshold, how often they are running, and how much resource each one is consuming. Your database is working ten times harder than it ever needed to. So let's make sure we index it before your hosting provider shuts you down.

---
_Source: https://the-faction.mn.co/posts/106569214_
