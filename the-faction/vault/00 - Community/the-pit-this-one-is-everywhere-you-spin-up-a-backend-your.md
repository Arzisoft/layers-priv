---
space: "The Pit"
author: "Matt Murphy"
post_id: 106365769
reactions: 1
comments: 0
published: "2026-08-26T14:00:02Z"
source: "https://the-faction.mn.co/posts/106365769"
---

# This one is everywhere. You spin up a backend, your frontend cannot talk to it,

This one is everywhere. You spin up a backend, your frontend cannot talk to it, you Google the error, and the first answer says allow all origins. You move on. Except that just told every browser on Earth that any website can talk to your API. Pair that with credentials and an attacker's page can silently make requests as your logged-in users. Their cookies ride along. The response comes back readable. No exploit. Just a webpage. Today I walk through replacing wildcard origins with a strict allowlist, locking down session cookies so they do not ride along on cross-site requests, and restricting methods and headers per endpoint. If you have never checked your CORS configuration, this is the fix.

**PROMPT:** Direct your AI: "Audit my entire backend for CORS configuration with three components: (1) Origin allowlist. Find every instance where the origin is set to a wildcard or reflects the request origin without validation. Replace all wildcard and reflected origin patterns with a strict allowlist of my exact production and staging domains. Ensure requests from any origin not on the list receive no access headers at all. (2) Cookie and credential controls. Update all session and authentication cookies to restrict cross-site sending. Implement request verification token middleware appropriate for my framework and apply it to all state-changing endpoints. Write integration tests that send cross-origin requests from an unauthorized domain and confirm that credentialed requests are rejected. (3) Method and header restrictions. Configure each endpoint to permit only the HTTP methods and headers that endpoint actually uses. Ensure preflight requests from unknown origins return a denial. Test by sending requests with unauthorized methods and confirming they are blocked."

---

## Video transcript

_deepgram auto-captions (Mighty) · 2m12s_

Your API is accepting requests from any origin. So an attacker's website just made an authenticated request to your back end using your user's session cookies. You see, your user visited a malicious website, and that website made a request to your API. The browser sent your user's session cookie along for the ride because your server said any origin is welcome here. Well, the attacker's site read the response.

All the account data, all the payment history, all the personal information. So your user never clicked anything suspicious. They just visited a web page. Here's how you're gonna fix it. Step one, your server is trusting every website on the Internet.

That is crazy. Somewhere in your setup, your API tells browsers that any origin can make requests and send credentials. That's not a configuration, folks. That is an open invitation for trouble. So direct your AI to replace any wildcard or reflected origin setting with a hard coded list of only your domains.

Every domain not on that list gets nothing. That's the win. Step two, cookies are riding along on requests your users never even made. So your session cookies have no restrictions on which sites can send them. Right?

So an attacker's page triggers a request, the cookie goes with it, And your server cannot tell the difference between your front end and a phishing site. So direct your AI to lock down every authentication cookie so browsers will not send them on cross site requests. Also, add request verification tokens to every endpoint that changes data. That's a win. Step three.

Your API response to methods and headers, it doesn't even need. Every unnecessary method is another way into your platform. So direct your AI to restrict each endpoint to only the specific methods in your headers front end actually is using. Right? And reject anything else at the preflight check.

Your users trust your domain. Your server is handling that trust to anyone who's asking for it. So lock the door before someone walks through it with your user's credentials. That is not a win.


---
_Source: https://the-faction.mn.co/posts/106365769_
