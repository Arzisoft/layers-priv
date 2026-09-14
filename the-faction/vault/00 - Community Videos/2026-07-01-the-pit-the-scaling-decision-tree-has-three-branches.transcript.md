---
type: transcript
lesson: "The scaling decision tree has three branches."
course: "The Pit"
author: "Matt Murphy"
post_id: 104007819
published: "2026-07-01T16:00:07Z"
source_url: "https://the-faction.mn.co/posts/104007819"
duration: "2m31s"
words: 385
transcribed_by: "deepgram auto-captions (Mighty)"
---

# Transcript — The scaling decision tree has three branches.

> The scaling decision tree has three branches.

Your Vibe Coded app just hit that wall. Users are complaining. Pages are loading slow. The database is sweating like it's running a marathon. The instinct?

Throw more money and resources at it. Bigger servers, more replicas, higher tier plans. Right? Well, here's what I actually tell clients before they spend a dollar solving this problem. The scaling decision tree has three branches, and you must check them in this order.

Branch one. Is it a connection problem or a capacity problem? Right? Most of the time, it's a connection problem. Ninety percent of the time.

Your database, it can handle all the queries you can throw at it, but it cannot handle two hundred connections that are fighting for fifty slots. A connection pooler fixes this for zero. PG Bouncer, supervisor, built in pooling on most managed platforms. So that's a win. If you add a read replica before you add a pooler, you just doubled your infrastructure cost to solve a problem that costs nothing to fix.

That's not the win. So you gotta check your connections first. Next is branch two. Is it a query problem or a volume problem? P g underscore stat underscore statements tells you which queries consume the most time.

Your slowest query might not be the problem. Your most frequent query running ten thousand times a day at forty milliseconds each, well, that's four hundred seconds of unnecessary database time. One index, one cache, one query optimization. The database, it's not slow, but that query, super expensive. Branch three.

Is it a read problem or a write problem? Eighty percent of database operations are reads. A read replica handles reads. It does not, though, help with contention. So if your writes are the bottleneck, replicas do nothing but make it worse.

You need queue processing, background jobs, write batching. So before you scale horizontally, know which access you're scaling on. The decision tree matters because every wrong branch costs money and solves nothing if you use it wrong. Connection pooling, query optimization, and readwrite separation. Go through it in that order.

That's where you're going to find the win. And clients who follow this order spend thousands. The ones who skip the replicas spend tens of thousands. Same result, different bill. Help your clients find the answer.

---
_Source: https://the-faction.mn.co/posts/104007819_
