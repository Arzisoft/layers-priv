---
type: transcript
lesson: "Your app just showed a user your database name, your server file path, and the q"
course: "The Pit"
author: "Matt Murphy"
post_id: 106720306
published: "2026-09-02T14:00:00Z"
source_url: "https://the-faction.mn.co/posts/106720306"
duration: "2m15s"
words: 336
transcribed_by: "deepgram auto-captions (Mighty)"
---

# Transcript — Your app just showed a user your database name, your server file path, and the q

> Your app just showed a user your database name, your server file path, and the query that failed. They were not trying to hack you. They clicked a broken link. Your AI built error handling for development and you shipped it to production. Every unhandled error hands your users a map of your infrastr

Your AI built app just showed a user your database name, your server file path, and their query that failed. And they were not trying to hack you, they accidentally clicked on a broken link. Your AI built error handling. Great. Detailed stack traces, full database queries, and internal file pass.

However, you shipped it to production and now your users are seeing the same data. So an attacker does not need to probe your system. Your error pages are doing the reconnaissance for them. So let's get it cleaned up. Step one, separate your error responses by environment.

Development shows the full stack trace. Production shows a generic message. Your users should never see an error that contains a file path, a query string or a database name or even a package version. So direct your AI to implement environment aware error handling so that it returns detailed errors only in development and returns generic user friendly responses in production. That's definitely a win.

Step two. Route every error to centralized logging, not to the user's screen. Every error your app throws should be captured, time stamped, and searchable in your monitoring system. No doubt about it. The user sees a clean error page.

You see the full detail in your logs. So direct your AI to implement structured error logging that captures the full stack trace request context and the user session data in your monitoring tool without exposing any of it to the client. That's also a win. And step three, build custom error pages that reveal nothing. So your four zero four or your five hundred or your time out page, every one of them should be branded, helpful and architecturally silent.

So direct your AI to build custom error pages for every common error code. So that it gives the user a clear next step without revealing any server side details. Those users who found a bug, do not let the bug write itself or the report. That's not a win.

---
_Source: https://the-faction.mn.co/posts/106720306_
