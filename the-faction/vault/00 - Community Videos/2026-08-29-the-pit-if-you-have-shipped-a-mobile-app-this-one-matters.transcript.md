---
type: transcript
lesson: "If you have shipped a mobile app, this one matters. Your user opens your app at"
course: "The Pit"
author: "Matt Murphy"
post_id: 106569104
published: "2026-08-29T14:00:03Z"
source_url: "https://the-faction.mn.co/posts/106569104"
duration: "2m03s"
words: 331
transcribed_by: "deepgram auto-captions (Mighty)"
---

# Transcript — If you have shipped a mobile app, this one matters. Your user opens your app at

> If you have shipped a mobile app, this one matters. Your user opens your app at a coffee shop and someone on the same WiFi captures every API call. Login credentials. Session tokens. All of it. Today I walk through certificate pinning so your app only talks to your server, encrypting sensitive field

Your mobile app sends every API call in plain text. So someone on the same coffee shop Wi Fi just watched all of your users log in. So your user opens your app at a coffee shop, Every request between the app and your server crosses the network where anyone on that WiFi can read it. Login credentials, session tokens, personal data. An attacker running a free tool on the same network captures all of it without touching your server or your app at all.

So let's get this thing locked down. Step one, your app is not verifying the server it's talking to. So your AI set up the API connection but never pinned the certificate. An attacker on the same network can sit between your app and your server, intercept every single request, and your app will never know the difference at all. So direct your AI to implement certificate pinning so your app only communicates with your verified server.

That and it rejects any connection where the certificate does not match. That's a win. Step two, sensitive data is traveling in the request body with no additional protection. Even with a secure connection, tokens and credentials sitting in plain text in the request body are one misconfiguration away from full exposure. So DirectoryAI to encrypt sensitive fields in your API payloads independently of the transport layer.

That so the data is protected even if the connection is compromised. And step three, your app stores credentials on the device in plain text. So your AI saved the authentication token in local storage where any other app or anyone with physical access to the device can read it. So direct your ad and move all tokens and credentials into the platform's secure storage so they are encrypted at rest and inaccessible to other applications. And well, your app works.

Your connection is not secure. That's the problem. So fix that transport layer before your users end up paying for it.

---
_Source: https://the-faction.mn.co/posts/106569104_
