---
type: transcript
lesson: "An attacker just grabbed your Google Login authorization code on a mobile networ"
course: "The Pit"
author: "Matt Murphy"
post_id: 106982455
published: "2026-09-08T14:00:00Z"
source_url: "https://the-faction.mn.co/posts/106982455"
duration: "2m06s"
words: 334
transcribed_by: "deepgram auto-captions (Mighty)"
---

# Transcript — An attacker just grabbed your Google Login authorization code on a mobile networ

> An attacker just grabbed your Google Login authorization code on a mobile network and logged in as your user before your app does. Your AI locked the redirect URI and added the state parameter. That stops forgery, not interception. The code travels in a URL anyone on the network can read. Generate a

An attacker just grabbed your Google login authorization code on a mobile network you're on and logged in as a user before you're apt in. So your AI locked the redirect URL and added the state parameter. That stops forgery, sure, but it does not stop a mobile interception. The authorization code still travels in a URL that anyone on that network can read. PKCE closes this gap.

So you're gonna direct your AI to add these three steps. Number one, generate a code verifier before the login redirect. A random string your app store server side that never appears in a URL and never leaves your server. This is the proof that the app requesting the token is the same app that started the login. Without it, anyone who grabs the authorization code off of a mobile network or a compromised browser can exchange it for a full session token.

So they're now logged in as your user. That is not a win. Step two, hash the verifier and send the hash as the code challenge. You see, Google receives the hash. An attacker who intercepts the authorization code does not have the original verifier.

So they cannot complete the token exchange. The code they just stole is useless without the proof your server holds. So one hash turns an intercepted code from a master key into a total dead end. That is a win. And three, send the original verifier with the token request.

Google compares it against the hash. Match means your app started the login. No match means someone grabbed the code in transit. So now you know what to look for. The exchange fails and your user's account stays locked to them.

That's a win. So your AI implemented one layer of protection and skipped the one that matters the most on every mobile device and every shared network your users are connecting from. So state stops forgery. PKCE stops interceptions. So DirectoryAI to implement both for the win.

---
_Source: https://the-faction.mn.co/posts/106982455_
