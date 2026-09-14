---
space: "The Pit"
author: "Matt Murphy"
post_id: 106762151
reactions: 1
comments: 0
published: "2026-09-04T14:00:01Z"
source: "https://the-faction.mn.co/posts/106762151"
---

# Your AI stored your JWT in localStorage. Any script on your page, every third-pa

Your AI stored your JWT in localStorage. Any script on your page, every third-party widget, every analytics tag, can read that token and send it anywhere. Today I walk through moving tokens into httpOnly cookies that JavaScript cannot access, implementing short-lived tokens with refresh rotation so a stolen token expires in minutes instead of months, and adding token revocation so you can kill every active session when a user's security changes. If your AI built your login system, check where it stored the token.

**PROMPT:** Direct your AI: "Harden my authentication token storage and lifecycle with three components: (1) Token storage migration. Refactor my authentication system to stop storing JWTs in localStorage. Move token storage to secure, httpOnly, SameSite=Strict cookies. The token should never be accessible to client-side JavaScript. Update every API call to work with cookie-based authentication instead of manually attaching the token from localStorage. Verify by checking that no token appears in localStorage, sessionStorage, or any JavaScript-accessible location after login. (2) Token lifecycle. Replace long-lived tokens with short-lived access tokens that expire in 15 minutes. Implement a refresh token rotation system where each refresh request returns a new access token and a new refresh token, and the old refresh token is invalidated. Store refresh tokens server-side and validate on every refresh request. (3) Token revocation. Implement a mechanism to invalidate all active tokens for a user. When a user changes their password, enables MFA, or reports a compromised account, every existing token for that user must be rejected. Implement this with a per-user token version or a server-side revocation list checked on every authenticated request. Verify by changing a password and confirming that all previous tokens are rejected."

---

## Video transcript

_deepgram auto-captions (Mighty) · 1m52s_

Your AI stored your authentication token in local storage. Now any script on your page can steal it and log in as your user. So your AI built your login system, user authenticates, server sends back to a JWT file, front end stores it in local storage. That token is your user's identity and it is sitting in a storage location that every script on your page can read. So that chat widget you added last week can read your users' auth tokens right now.

Here's how we're gonna fix it. Number one, move your tokens out of local storage and into HTTP only cookies. An HTTP only cookie cannot be read by JavaScript. It travels with every request automatically and is invisible to any script running on your page. So direct your AI to refactor authentication flow so it stores the JWT in a secure HTTP only same site cookie instead of local storage.

That's a win. Number two, set token expiration short and implement refresh tokens. A stolen JWT that lasts thirty days is an open door for thirty days. A token that expires in fifteen minutes limits that damage window. So direct your AI to implement short lived access tokens with a secure refresh token rotation that issues a new pair on each refresh.

That's a win. And number three, add token revocation. If a user changes their password or reports a compromised account, every active token for that user should die immediately. So DirectoryAI to implement a token revocation list or a per user token version, right, so that it invalidates all existing tokens when the user's security state changes. Your auth token is your user's key to the building.

Stop leaving it on the counter where anyone can copy it. And that is a win.


---
_Source: https://the-faction.mn.co/posts/106762151_
