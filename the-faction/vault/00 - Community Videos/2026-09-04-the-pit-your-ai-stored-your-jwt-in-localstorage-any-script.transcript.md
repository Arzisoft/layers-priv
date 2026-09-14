---
type: transcript
lesson: "Your AI stored your JWT in localStorage. Any script on your page, every third-pa"
course: "The Pit"
author: "Matt Murphy"
post_id: 106762151
published: "2026-09-04T14:00:01Z"
source_url: "https://the-faction.mn.co/posts/106762151"
duration: "1m52s"
words: 300
transcribed_by: "deepgram auto-captions (Mighty)"
---

# Transcript — Your AI stored your JWT in localStorage. Any script on your page, every third-pa

> Your AI stored your JWT in localStorage. Any script on your page, every third-party widget, every analytics tag, can read that token and send it anywhere. Today I walk through moving tokens into httpOnly cookies that JavaScript cannot access, implementing short-lived tokens with refresh rotation so 

Your AI stored your authentication token in local storage. Now any script on your page can steal it and log in as your user. So your AI built your login system, user authenticates, server sends back to a JWT file, front end stores it in local storage. That token is your user's identity and it is sitting in a storage location that every script on your page can read. So that chat widget you added last week can read your users' auth tokens right now.

Here's how we're gonna fix it. Number one, move your tokens out of local storage and into HTTP only cookies. An HTTP only cookie cannot be read by JavaScript. It travels with every request automatically and is invisible to any script running on your page. So direct your AI to refactor authentication flow so it stores the JWT in a secure HTTP only same site cookie instead of local storage.

That's a win. Number two, set token expiration short and implement refresh tokens. A stolen JWT that lasts thirty days is an open door for thirty days. A token that expires in fifteen minutes limits that damage window. So direct your AI to implement short lived access tokens with a secure refresh token rotation that issues a new pair on each refresh.

That's a win. And number three, add token revocation. If a user changes their password or reports a compromised account, every active token for that user should die immediately. So DirectoryAI to implement a token revocation list or a per user token version, right, so that it invalidates all existing tokens when the user's security state changes. Your auth token is your user's key to the building.

Stop leaving it on the counter where anyone can copy it. And that is a win.

---
_Source: https://the-faction.mn.co/posts/106762151_
