---
space: "The Pit"
author: "Matt Murphy"
post_id: 106720306
reactions: 2
comments: 0
published: "2026-09-02T14:00:00Z"
source: "https://the-faction.mn.co/posts/106720306"
---

# Your app just showed a user your database name, your server file path, and the q

Your app just showed a user your database name, your server file path, and the query that failed. They were not trying to hack you. They clicked a broken link. Your AI built error handling for development and you shipped it to production. Every unhandled error hands your users a map of your infrastructure. Today I walk through separating error responses by environment so production never shows a stack trace, routing every error to centralized logging instead of the user's screen, and building custom error pages that are branded, helpful, and architecturally silent. If you have not checked what your error pages reveal, do it today.

**PROMPT:** Direct your AI: "Build a production error handling and information leakage prevention system with three components: (1) Environment-aware error responses. Audit every error handler, catch block, and exception response in my application. Verify that detailed error information including stack traces, file paths, database names, query strings, package versions, and internal configuration is returned ONLY in development environments. In production, every error response must return a generic, user-friendly message with no internal detail. Implement a global error handler that enforces this separation regardless of whether individual routes handle their own errors. Test by triggering errors in production mode and verifying no internal information is exposed in the response body, headers, or HTML source. (2) Centralized error logging. Implement structured error logging that captures: full stack trace, request URL, request method, request headers, authenticated user ID, session ID, timestamp, and environment. Route all error logs to a centralized monitoring system. Verify that error detail is searchable and filterable by severity, endpoint, user, and time range. Confirm that no error detail is written to client-accessible locations including response bodies, browser console output, or client-side error tracking scripts that expose raw data. (3) Custom error pages. Build branded error pages for every common HTTP error code: 400, 401, 403, 404, 408, 429, 500, 502, 503. Each page must display a clear user-facing message, suggest a next step, and reveal zero information about the server, framework, database, or file structure. Verify by inspecting the HTML source of each error page and confirming no server-side detail appears in comments, meta tags, hidden fields, or data attributes."

---

## Video transcript

_deepgram auto-captions (Mighty) · 2m15s_

Your AI built app just showed a user your database name, your server file path, and their query that failed. And they were not trying to hack you, they accidentally clicked on a broken link. Your AI built error handling. Great. Detailed stack traces, full database queries, and internal file pass.

However, you shipped it to production and now your users are seeing the same data. So an attacker does not need to probe your system. Your error pages are doing the reconnaissance for them. So let's get it cleaned up. Step one, separate your error responses by environment.

Development shows the full stack trace. Production shows a generic message. Your users should never see an error that contains a file path, a query string or a database name or even a package version. So direct your AI to implement environment aware error handling so that it returns detailed errors only in development and returns generic user friendly responses in production. That's definitely a win.

Step two. Route every error to centralized logging, not to the user's screen. Every error your app throws should be captured, time stamped, and searchable in your monitoring system. No doubt about it. The user sees a clean error page.

You see the full detail in your logs. So direct your AI to implement structured error logging that captures the full stack trace request context and the user session data in your monitoring tool without exposing any of it to the client. That's also a win. And step three, build custom error pages that reveal nothing. So your four zero four or your five hundred or your time out page, every one of them should be branded, helpful and architecturally silent.

So direct your AI to build custom error pages for every common error code. So that it gives the user a clear next step without revealing any server side details. Those users who found a bug, do not let the bug write itself or the report. That's not a win.


---
_Source: https://the-faction.mn.co/posts/106720306_
