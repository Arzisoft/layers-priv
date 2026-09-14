---
type: transcript
lesson: "Every push goes directly to production."
course: "The Pit"
author: "Matt Murphy"
post_id: 104707757
published: "2026-07-17T18:00:00Z"
source_url: "https://the-faction.mn.co/posts/104707757"
duration: "1m34s"
words: 232
transcribed_by: "deepgram auto-captions (Mighty)"
---

# Transcript — Every push goes directly to production.

> Every push goes directly to production.

So every push goes directly to production. One bad merge and your customers see the bug before you do. Your AI builds on main and ships it live. Here are the three things you direct your AI to set up right now to fix it. Step one, build a staging environment.

So direct your AI to create an environment that mirrors your production environment. Same database schema, same services, same environmental variables. Vercel preview deployments give you this almost for free. But if it doesn't, you gotta build it. Every pull request gets its own preview.

Test there, not in production, that's the win. Step two, nothing ships without passing staging. Direct your AI to build a CI pipeline that runs tests against staging. Tests pass, the pipeline promotes to production automatically. Tests fail, production never sees it.

Your customers never see a broken feature. Your team catches it first. That's also a win. And step three, one click rollback. Something got through, a bug made it past staging, these things happen to the best of us.

Direct your AI to implement rollback to the last known good deploy. Not SSH into the server, just one button, previous version immediately. Every deployment is either a confident push or a quick rollback. It's time to stop shipping to production on a prayer. Start shipping to staging with a full plan.

That's the win.

---
_Source: https://the-faction.mn.co/posts/104707757_
