---
space: "The Pit"
author: "Matt Murphy"
post_id: 106761987
reactions: 1
comments: 0
published: "2026-09-03T19:00:02Z"
source: "https://the-faction.mn.co/posts/106761987"
---

# Your API endpoint is /api/users/15/orders. Change 15 to 16 and you get someone e

Your API endpoint is /api/users/15/orders. Change 15 to 16 and you get someone else's orders. Your AI built the endpoint but never added ownership verification. The API trusts whatever ID is in the URL. Today I walk through adding ownership checks that compare the session user against the requested resource, replacing sequential integer IDs with UUIDs so attackers cannot enumerate your users, and auditing every endpoint that accepts an ID parameter. If your AI built your API and you have never tested what happens when you change the ID in the URL, try it right now.

**PROMPT:** Direct your AI: "Perform an insecure direct object reference (IDOR) audit and remediation with three components: (1) Ownership verification. For every API endpoint that accepts a user ID, resource ID, or any identifier as a URL parameter, query parameter, or request body field, verify that the server checks the authenticated user's session against the resource owner before returning data or processing the request. If user A requests user B's resources, the server must return 403 Forbidden. Implement ownership verification middleware that applies to all protected endpoints. Test every endpoint by authenticating as one user and requesting another user's resources. (2) ID obfuscation. Replace all sequential integer IDs in API endpoints and database primary keys with UUIDs or other non-enumerable identifiers. Update all foreign key relationships, API responses, and frontend references to use the new identifiers. Verify that no sequential ID is exposed in any API response or URL. (3) Comprehensive endpoint audit. List every API endpoint in the application. For each endpoint that accepts any resource identifier, document: the identifier type, whether ownership is verified, and what data is returned. Flag every endpoint where a user can access resources belonging to another user. Provide a remediation priority list sorted by data sensitivity."

---

## Video transcript

_deepgram auto-captions (Mighty) · 2m03s_

Your API is using the user ID and the URL to load the data. So you change the number and you see someone else's account altogether. So your AI, yeah, built your API endpoints. Your front end sends the logged in user's ID and gets their data right back. But your API never checks whether the person making the request is actually the right user.

So your authorization is in the URL and your URL is one guess away from every other user's data. Let's get this handled. Step one, verify ownership on every API request. Every endpoint that returns user specific data must check the authenticated user's identity against the resource they are requesting. So if user twelve requests user fifteen's data, the server returns a four zero three.

So direct your AI to add ownership verification middleware so that it compares the authenticated session user against the resource owner on every protected endpoint. That's a win. Step two, stop using sequential IDs in your URLs. User one, user two, user three, or order one thousand and one, one thousand and two, one thousand and three. Sequential IDs make enumeration trivial.

An attacker writes a loop and downloads every user's data in minutes. So direct your AI to replace sequential integer IDs with UUIDs and all API endpoints and database references. That's a win. And step three, audit every endpoint that takes an ID as a parameter. Your AI built dozens of endpoints.

Every one of them accepts an ID in the URL, query string or a request body in a potential access control failure. So DirectoryAI to list every endpoint so that it accepts a resource identifier, verify ownership checks exist on each one, and flag any endpoint where a user can access resources that do not belong to them. Your API should not trust the URL. It should trust the user session. That's your win.


---
_Source: https://the-faction.mn.co/posts/106761987_
