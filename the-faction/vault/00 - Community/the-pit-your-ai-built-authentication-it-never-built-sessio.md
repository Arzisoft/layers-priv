---
space: "The Pit"
author: "Matt Murphy"
post_id: 104924727
reactions: 2
comments: 0
published: "2026-07-22T17:35:58Z"
source: "https://the-faction.mn.co/posts/104924727"
---

# Your AI built authentication. It never built session management. Right now a use

Your AI built authentication. It never built session management. Right now a user who logged in six months ago still has full access on a device they may not even own anymore. Today I walk through session expiration, concurrent session limits, and instant session revocation. Three things your AI will never build unless you direct it to.

-MM

**ORCHESTRATION PROMPT**

Direct your AI: "Audit my authentication system for session management gaps. Then build three features: (1) Session expiration with configurable lifetimes per user role. Admin sessions expire after 2 hours, standard users after 24 hours, with sliding window refresh on activity. (2) Concurrent session limits capped at 3 active sessions per user, with a session registry that shows device type, IP, and last activity. (3) A session revocation endpoint that kills all active sessions for a user instantly when triggered by password change, suspicious activity flag, or manual admin action. Show me the middleware implementation."

---

## Video transcript

_deepgram auto-captions (Mighty) · 2m00s_

A user who logged in six months ago still has full access to your entire application right now. They lost their laptop at a coffee shop three months ago, someone opened it, and your app was still logged in. So your database is wide open on a stranger's screen right now. And your AI, it built authentication, but it never built session management. And sessions that never expire and tokens that live forever are open doors everywhere in your system.

So here are the three things you direct your AI to build before someone walks through a door you forgot to close. Step one, session expiration with a defined timeline. Right now your sessions live forever because most frameworks ship that way and your AI use the default. A banking app and a note taking app do not get the same session window. You decide the lifetime based on what your application touches.

Financial data? Hours or less. Low risk content? Days or less. That is an engineering decision and it's yours to make.

Alright, step two, concurrent session limits. Right now one user can be logged in on fifteen devices and you would just never know. Because when credentials get stolen, the attacker rides an existing session while the real user has no idea someone else is in their account. So your AI can cap active sessions per user. Most builders do not know this is even possible.

And step three is instant session revocation. When a user changes their password, every active session for that user needs to die right then. Not on the next token refresh, not eventually, right now. Without it, a user who changes their password still has an attacker sitting inside an active session on another device. The password change was a false sense of security.

Your AI built the lock on the front door. It left every window in the house wide open. So you need to direct your AI to close them tonight.


---
_Source: https://the-faction.mn.co/posts/104924727_
