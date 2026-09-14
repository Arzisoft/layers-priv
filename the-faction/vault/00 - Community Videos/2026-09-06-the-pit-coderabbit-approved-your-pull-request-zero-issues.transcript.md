---
type: transcript
lesson: "CodeRabbit approved your pull request. Zero issues. But your user profile endpoi"
course: "The Pit"
author: "Matt Murphy"
post_id: 106765203
published: "2026-09-06T14:00:02Z"
source_url: "https://the-faction.mn.co/posts/106765203"
duration: "1m40s"
words: 251
transcribed_by: "deepgram auto-captions (Mighty)"
---

# Transcript — CodeRabbit approved your pull request. Zero issues. But your user profile endpoi

> CodeRabbit approved your pull request. Zero issues. But your user profile endpoint accepts every field in the request body because your AI wrote an update handler that passes the whole body to the database. Send isAdmin true in a profile update and your server writes it. The code was syntactically c

CodeRabbit reviewed your code and found zero issues. That's a win, perhaps. But your API is accepting every field in a request body and a user sent a is admin true and your server wrote it back. So your AI built your user endpoints, CodeRabbit approved the pull request, but your update handler takes the entire request body and wrote it straight to the database. So that includes every field, ones your front end never even sends.

So your code review passed, but your security review did not. Let's get it fixed. Step one, whitelist allowed fields on every right endpoint. That means name, email, avatar. But it never means role, plan, permissions or account status.

Direct your AI to add field validation that rejects anything that's not on that list. That's a win. Step two, separate user endpoints from admin endpoints. A user updating their profile and an admin changing a role should never crash into each other on the same route. So direct your AI to create dedicated admin endpoints with elevated authorization and strip all admin level fields from user facing handlers.

That's a win. And three, test every endpoint by sending fields it should be rejecting. Is admin account type, whatever it is, DirectoryAI to write tests that submit prohibited fields to every updated endpoint. And then you verify the server rejects or strips them completely. Codebabbit, yeah, it'll review your code, but it does not review your attack surface.

That, still your job. Keep it up.

---
_Source: https://the-faction.mn.co/posts/106765203_
