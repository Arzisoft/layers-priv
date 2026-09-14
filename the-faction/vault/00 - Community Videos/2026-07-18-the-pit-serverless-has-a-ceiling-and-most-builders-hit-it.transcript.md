---
type: transcript
lesson: "Serverless has a ceiling and most builders hit it without knowing it existed. Th"
course: "The Pit"
author: "Matt Murphy"
post_id: 104751211
published: "2026-07-18T18:00:03Z"
source_url: "https://the-faction.mn.co/posts/104751211"
duration: "1m36s"
words: 237
transcribed_by: "deepgram auto-captions (Mighty)"
---

# Transcript — Serverless has a ceiling and most builders hit it without knowing it existed. Th

> *Serverless has a ceiling and most builders hit it without knowing it existed. This is how to identify which workloads belong on serverless, which need containers, and how to run both.*

Your serverless function times out after sixty seconds, but the job AI built takes three minutes. So your AI built everything on serverless because the platform made it super easy. But here are the three things you're going to direct your AI to evaluate right now to fix it. Step one: Identify what does not fit. Short lived request response stays serverless.

User hits an endpoint, function responds, done and done. But long running processes, queue workers, WebSocket connections, file processing that takes minutes on end, these cannot live on serverless. It will not work. So direct your AI to list every function that runs longer than thirty seconds or holds a persistent connection. Figure that out, that's a win.

Step two, containerize the heavy workload. Direct your AI to move your longest running process into a container. A queue process or a scheduled job runner, a WebSocket server. Serverless dispatches work to the container. The container processes it.

Both report to the same monitoring. And step three, add a lane, not a migration. You're not leaving serverless. You're adding more capacity. Serverless handles the fast work, and it's really good at it.

But containers, they handle the heavy work. So you direct your AI to route by workload type. Knowing when your platform ceiling is forcing an architecture change is an orchestration decision. And this is a classic. It's not a technical one.

You got Yes.

---
_Source: https://the-faction.mn.co/posts/104751211_
