---
space: "The Pit"
author: "Matt Murphy"
post_id: 106765203
reactions: 3
comments: 0
published: "2026-09-06T14:00:02Z"
source: "https://the-faction.mn.co/posts/106765203"
---

# CodeRabbit approved your pull request. Zero issues. But your user profile endpoi

CodeRabbit approved your pull request. Zero issues. But your user profile endpoint accepts every field in the request body because your AI wrote an update handler that passes the whole body to the database. Send isAdmin true in a profile update and your server writes it. The code was syntactically clean. The vulnerability is in what it accepts, not how it processes it. Today I walk through whitelisting allowed fields on every write endpoint, separating user-facing update handlers from admin operations, and testing every endpoint by sending fields that should be rejected. If your AI built your API endpoints and you have never tested what happens when you send extra fields, test it today.

**PROMPT:** Direct your AI: "Perform a mass assignment vulnerability audit and remediation with three components: (1) Field whitelisting. For every API endpoint that accepts a request body and writes to the database, implement explicit field validation that allows only the fields a user is permitted to change. Create a whitelist of allowed fields for each endpoint. Reject or strip any field not on the whitelist before the data reaches the database. Specifically check that no endpoint allows modification of: role, isAdmin, permissions, accountType, plan, subscription status, email verification status, or any field that controls access or billing. Verify by sending a request with a prohibited field and confirming it is either rejected or ignored. (2) Endpoint separation. Audit every endpoint that handles both user-level and admin-level field updates. Separate each into a user-facing endpoint that accepts only user-modifiable fields and an admin endpoint that requires elevated authorization. The admin endpoint must verify the requesting user has admin privileges before processing. Verify by authenticating as a regular user and attempting to access the admin endpoint, confirming a 403 is returned. (3) Automated attack surface testing. For every endpoint that accepts a request body, write automated tests that attempt to modify sensitive fields: isAdmin, role, permissions, plan, accountType, emailVerified, and any field that controls access or billing. Each test should authenticate as a regular user, send the prohibited field in the request body, and verify the field was not modified in the database. Run these tests on every API endpoint that writes user data."

---

## Video transcript

_deepgram auto-captions (Mighty) · 1m40s_

CodeRabbit reviewed your code and found zero issues. That's a win, perhaps. But your API is accepting every field in a request body and a user sent a is admin true and your server wrote it back. So your AI built your user endpoints, CodeRabbit approved the pull request, but your update handler takes the entire request body and wrote it straight to the database. So that includes every field, ones your front end never even sends.

So your code review passed, but your security review did not. Let's get it fixed. Step one, whitelist allowed fields on every right endpoint. That means name, email, avatar. But it never means role, plan, permissions or account status.

Direct your AI to add field validation that rejects anything that's not on that list. That's a win. Step two, separate user endpoints from admin endpoints. A user updating their profile and an admin changing a role should never crash into each other on the same route. So direct your AI to create dedicated admin endpoints with elevated authorization and strip all admin level fields from user facing handlers.

That's a win. And three, test every endpoint by sending fields it should be rejecting. Is admin account type, whatever it is, DirectoryAI to write tests that submit prohibited fields to every updated endpoint. And then you verify the server rejects or strips them completely. Codebabbit, yeah, it'll review your code, but it does not review your attack surface.

That, still your job. Keep it up.


---
_Source: https://the-faction.mn.co/posts/106765203_
