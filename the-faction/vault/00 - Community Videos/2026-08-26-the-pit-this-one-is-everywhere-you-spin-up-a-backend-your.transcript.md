---
type: transcript
lesson: "This one is everywhere. You spin up a backend, your frontend cannot talk to it,"
course: "The Pit"
author: "Matt Murphy"
post_id: 106365769
published: "2026-08-26T14:00:02Z"
source_url: "https://the-faction.mn.co/posts/106365769"
duration: "2m12s"
words: 351
transcribed_by: "deepgram auto-captions (Mighty)"
---

# Transcript — This one is everywhere. You spin up a backend, your frontend cannot talk to it,

> This one is everywhere. You spin up a backend, your frontend cannot talk to it, you Google the error, and the first answer says allow all origins. You move on. Except that just told every browser on Earth that any website can talk to your API. Pair that with credentials and an attacker's page can si

Your API is accepting requests from any origin. So an attacker's website just made an authenticated request to your back end using your user's session cookies. You see, your user visited a malicious website, and that website made a request to your API. The browser sent your user's session cookie along for the ride because your server said any origin is welcome here. Well, the attacker's site read the response.

All the account data, all the payment history, all the personal information. So your user never clicked anything suspicious. They just visited a web page. Here's how you're gonna fix it. Step one, your server is trusting every website on the Internet.

That is crazy. Somewhere in your setup, your API tells browsers that any origin can make requests and send credentials. That's not a configuration, folks. That is an open invitation for trouble. So direct your AI to replace any wildcard or reflected origin setting with a hard coded list of only your domains.

Every domain not on that list gets nothing. That's the win. Step two, cookies are riding along on requests your users never even made. So your session cookies have no restrictions on which sites can send them. Right?

So an attacker's page triggers a request, the cookie goes with it, And your server cannot tell the difference between your front end and a phishing site. So direct your AI to lock down every authentication cookie so browsers will not send them on cross site requests. Also, add request verification tokens to every endpoint that changes data. That's a win. Step three.

Your API response to methods and headers, it doesn't even need. Every unnecessary method is another way into your platform. So direct your AI to restrict each endpoint to only the specific methods in your headers front end actually is using. Right? And reject anything else at the preflight check.

Your users trust your domain. Your server is handling that trust to anyone who's asking for it. So lock the door before someone walks through it with your user's credentials. That is not a win.

---
_Source: https://the-faction.mn.co/posts/106365769_
