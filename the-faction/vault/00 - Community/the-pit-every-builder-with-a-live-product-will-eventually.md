---
space: "The Pit"
author: "Matt Murphy"
post_id: 105667233
reactions: 5
comments: 1
published: "2026-08-08T14:00:01Z"
source: "https://the-faction.mn.co/posts/105667233"
---

# Every builder with a live product will eventually need to change their database

Every builder with a live product will eventually need to change their database schema. Your AI has no concept of how to do that without taking your app offline. Today I walk through migration scripts that run without downtime, rollback plans written before the migration starts, and staging environments where you test first. This maps directly to T4 Database Design Module 4.

**PROMPT:** Direct your AI: "I need to modify my production database schema. Before making any changes, build three things: (1) A migration script that follows the expand-contract pattern. Add the new column or table first, copy data over, update the application to use the new structure, then remove the old structure only after everything is confirmed working. Never drop and recreate. (2) A rollback script that reverses this migration completely. If the rollback cannot be described step by step, the migration is not ready to run. (3) A staging environment test plan. Clone my current production schema, run the migration against the clone with representative data, verify all queries and application functions still work, then document the results before touching production."

---

## Video transcript

_deepgram auto-captions (Mighty) · 2m08s_

Your AI built your database, but it never planned for the day you have to change it completely. So your app is live, customers are using it, and you just realized you need to add a field, rename a column, or restructure how two tables relate to each other. So that's a migration and your AI has no idea how to do one without taking your app completely offline. So here are three things you direct your AI to build before you touch any live database. Step one, a migration script that runs without downtime.

Your AI will default to dropping a column and recreating it. On a live database, that means every customer query that hits that column while the migration runs either fails or returns total garbage. So direct your AI to write migrations that add before they remove anything. New column goes up, data copies over, application switches to the new column, old column drops only after everything is confirmed by you. That sequence is the difference between a migration and an outage.

That's a win. Step two, a rollback plan written before the migration ever starts. If the migration breaks halfway through, you need to undo it right then. Not tomorrow, not after you debug it, but immediately. So direct your AI to write the rollback script at the same time it writes the migration plan.

If it cannot describe how to reverse it, the migration is not ready to run. And step three, a staging environment where you run the migration first. Not on production, not on a copy you made three weeks ago. A current mirror of your live database where you test the exact migration with real data shapes before it touches a single customer record. So direct your AI to set this up before you run anything at all.

The first time you test a migration should never be against the database your customers are depending on. Your AI built the database in minutes. Changing it safely takes engineering judgment and a little bit of time. And that is your job.


---

## Discussion

**Emekalam Chibuzor** · 2026-08-08

> Awesome 💯


---
_Source: https://the-faction.mn.co/posts/105667233_
