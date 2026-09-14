---
type: transcript
lesson: "A user just queried your Neon database and downloaded every other user's records"
course: "The Pit"
author: "Matt Murphy"
post_id: 106982113
published: "2026-09-07T14:00:01Z"
source_url: "https://the-faction.mn.co/posts/106982113"
duration: "2m05s"
words: 307
transcribed_by: "deepgram auto-captions (Mighty)"
---

# Transcript — A user just queried your Neon database and downloaded every other user's records

> A user just queried your Neon database and downloaded every other user's records. Customer data, transaction history, private messages. Your AI created the tables, connected your app, and moved on. RLS is off by default in PostgreSQL. Any authenticated user can query any row in any table. Enable RLS

Your AI built the database in Neon, but it never turned on row level security. So your AI created the tables, connected your app, and moved right on. RLS is off by default in Postgres SQL. Right now, any authenticated user can query any row in any table. So let's fix three things before your next deploy.

Number one, enable RLS on every table immediately. Not after you launch, not when you have time, but right now. With RLS off, any logged in user can pull customer records, transaction history, private messages, or even internal notes. So not just their data, but everyone's data. So your app looks like it works because each user sees their own dashboard.

But one API call with a different user ID returns someone else's entire account. Nothing stops it. Nothing logs it. Your AI skipped one command per table and it turned your database into a shared spreadsheet. That's not a win.

Number two, create four policies per table scoped to the authenticated user. Select, insert, update, and delete. Each one filtering rows by the requesting user's ID matched against an owner column. Without these, enabling RLS locks out everyone, including your own app. So your AI needs to build these policies and test them in the same session.

That's a win. And three, verify with a second account. So DirectoryAI to log in as a different user and query the table. If it returns rows belonging to someone else, the policies are broken. So this takes less than a minute, but it answers a lot of questions.

A query that returns another user's data is not a bug you will fix later. Trust me. It is a breach happening right now that nobody has reported yet. So one command, four policies, every table, all day, every day for the win.

---
_Source: https://the-faction.mn.co/posts/106982113_
