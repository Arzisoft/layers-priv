---
space: "The Pit"
author: "Matt Murphy"
post_id: 106982113
reactions: 0
comments: 0
published: "2026-09-07T14:00:01Z"
source: "https://the-faction.mn.co/posts/106982113"
---

# A user just queried your Neon database and downloaded every other user's records

A user just queried your Neon database and downloaded every other user's records. Customer data, transaction history, private messages. Your AI created the tables, connected your app, and moved on. RLS is off by default in PostgreSQL. Any authenticated user can query any row in any table. Enable RLS on every table immediately. With it off, one API call with a different user ID returns someone else's entire account. Create four policies per table. Select, insert, update, delete. Each one filtered by the authenticated user's ID. Without policies, enabling RLS locks everyone out. Verify by logging in as a different user and querying the table. If you see someone else's data, the policies are wrong. One command. Four policies. Every table.

**PROMPT:** You are a PostgreSQL security auditor for Neon databases. Review the following database for Row Level Security gaps. For every table, check: (1) Is RLS enabled? Run SELECT relname, relrowsecurity FROM pg_class WHERE relkind = 'r'. Flag any table with relrowsecurity = false as CRITICAL. (2) Are there SELECT, INSERT, UPDATE, and DELETE policies? List missing policies per table. (3) Do existing policies filter by the authenticated user's ID matched against an owner/user_id column? Flag any policy that does not scope to the current user. (4) Are there any queries using service role or bypassing RLS with SECURITY DEFINER functions? Flag those. (5) Test with a simulated second user: would a query from user B return user A's rows? For each finding, provide the exact SQL to enable RLS and create properly scoped policies.

---

## Video transcript

_deepgram auto-captions (Mighty) · 2m05s_

Your AI built the database in Neon, but it never turned on row level security. So your AI created the tables, connected your app, and moved right on. RLS is off by default in Postgres SQL. Right now, any authenticated user can query any row in any table. So let's fix three things before your next deploy.

Number one, enable RLS on every table immediately. Not after you launch, not when you have time, but right now. With RLS off, any logged in user can pull customer records, transaction history, private messages, or even internal notes. So not just their data, but everyone's data. So your app looks like it works because each user sees their own dashboard.

But one API call with a different user ID returns someone else's entire account. Nothing stops it. Nothing logs it. Your AI skipped one command per table and it turned your database into a shared spreadsheet. That's not a win.

Number two, create four policies per table scoped to the authenticated user. Select, insert, update, and delete. Each one filtering rows by the requesting user's ID matched against an owner column. Without these, enabling RLS locks out everyone, including your own app. So your AI needs to build these policies and test them in the same session.

That's a win. And three, verify with a second account. So DirectoryAI to log in as a different user and query the table. If it returns rows belonging to someone else, the policies are broken. So this takes less than a minute, but it answers a lot of questions.

A query that returns another user's data is not a bug you will fix later. Trust me. It is a breach happening right now that nobody has reported yet. So one command, four policies, every table, all day, every day for the win.


---
_Source: https://the-faction.mn.co/posts/106982113_
