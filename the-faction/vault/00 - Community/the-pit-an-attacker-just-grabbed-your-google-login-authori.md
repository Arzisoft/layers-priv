---
space: "The Pit"
author: "Matt Murphy"
post_id: 106982455
reactions: 0
comments: 0
published: "2026-09-08T14:00:00Z"
source: "https://the-faction.mn.co/posts/106982455"
---

# An attacker just grabbed your Google Login authorization code on a mobile networ

An attacker just grabbed your Google Login authorization code on a mobile network and logged in as your user before your app does. Your AI locked the redirect URI and added the state parameter. That stops forgery, not interception. The code travels in a URL anyone on the network can read. Generate a code verifier before the redirect. Store it server-side. Hash it and send the hash as the code challenge. Google gets the hash. An attacker intercepts the code but not the verifier. They cannot complete the exchange. Send the original verifier with the token request. Match means your app. No match means someone grabbed the code. State stops forgery. PKCE stops interception. Direct your AI to implement both.

**PROMPT:** You are an OAuth security auditor. Review the following Google authentication implementation for PKCE compliance. Check: (1) Is a code_verifier being generated before the authorization redirect? It should be a cryptographically random string, 43-128 characters. (2) Is the code_verifier stored server-side in a session, not in localStorage or a cookie? (3) Is a code_challenge being sent in the authorization request as a SHA-256 hash of the verifier? (4) Is the code_challenge_method set to S256, not plain? (5) Is the original code_verifier being sent in the token exchange request? (6) Is the state parameter also present and validated? For each missing element, provide the exact implementation code. Flag any implementation using the implicit flow (response_type=token) as CRITICAL.

---

## Video transcript

_deepgram auto-captions (Mighty) · 2m06s_

An attacker just grabbed your Google login authorization code on a mobile network you're on and logged in as a user before you're apt in. So your AI locked the redirect URL and added the state parameter. That stops forgery, sure, but it does not stop a mobile interception. The authorization code still travels in a URL that anyone on that network can read. PKCE closes this gap.

So you're gonna direct your AI to add these three steps. Number one, generate a code verifier before the login redirect. A random string your app store server side that never appears in a URL and never leaves your server. This is the proof that the app requesting the token is the same app that started the login. Without it, anyone who grabs the authorization code off of a mobile network or a compromised browser can exchange it for a full session token.

So they're now logged in as your user. That is not a win. Step two, hash the verifier and send the hash as the code challenge. You see, Google receives the hash. An attacker who intercepts the authorization code does not have the original verifier.

So they cannot complete the token exchange. The code they just stole is useless without the proof your server holds. So one hash turns an intercepted code from a master key into a total dead end. That is a win. And three, send the original verifier with the token request.

Google compares it against the hash. Match means your app started the login. No match means someone grabbed the code in transit. So now you know what to look for. The exchange fails and your user's account stays locked to them.

That's a win. So your AI implemented one layer of protection and skipped the one that matters the most on every mobile device and every shared network your users are connecting from. So state stops forgery. PKCE stops interceptions. So DirectoryAI to implement both for the win.


---
_Source: https://the-faction.mn.co/posts/106982455_
