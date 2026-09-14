---
type: transcript
lesson: "Your AI wrote Firebase Cloud Functions using the Admin SDK. The Admin SDK has un"
course: "The Pit"
author: "Matt Murphy"
post_id: 106765111
published: "2026-09-05T14:00:02Z"
source_url: "https://the-faction.mn.co/posts/106765111"
duration: "2m15s"
words: 331
transcribed_by: "deepgram auto-captions (Mighty)"
---

# Transcript — Your AI wrote Firebase Cloud Functions using the Admin SDK. The Admin SDK has un

> Your AI wrote Firebase Cloud Functions using the Admin SDK. The Admin SDK has unrestricted access to your entire database. No security rules apply to it. Your function takes user input from the request, builds a query, and runs it with full admin privileges. If a user changes the collection name or 

Your AI built Firebase Cloud Functions with the admin SDK. Well, the admin SDK bypasses every security rule, so your AI wrote Firebase Cloud Functions to handle your back end logic, which has unrestricted access to your entire database. No security rules apply. Your function takes user input directly from the request, builds a database query, and executes it with full admin privileges. So if a user changes the collection name or document ID in their request, your function queries whatever they wanna ask for.

So your security rules protect the front end, but your cloud functions have no rules at all. Let's get it fixed. Step one, validate every input parameter before it reaches the database. So your Firebase cloud function should never pass raw user input into a database query. Directory add input validation to every cloud function that checks parameter types, enforces allowed values and rejects any request with unexpected fields or values before the query executes.

That's definitely a win. Step two. Scope every query to the authenticated user's data. The admin SDK will query anything. Your function, well, it should not.

So even though the admin SDK has full access, every query should filter by the authenticated users ID. So Directory AI to add user scoping to every database operation in every cloud function. So a function never returns or modifies data belonging to another user. And step three, audit the gap between what your functions can access and what they should access. The admin SDK can read and write every collection, every document, and every field.

So DirectoryAI to list every cloud function, document what data it accesses, and verify each function only touches what the requesting user is authorized to see. Flag any function that reaches beyond the authenticated user's own data. So your security rules, they stop the client. Your cloud functions start where those rules end. And right now, they have no boundaries of their own.

So let's get them locked in.

---
_Source: https://the-faction.mn.co/posts/106765111_
