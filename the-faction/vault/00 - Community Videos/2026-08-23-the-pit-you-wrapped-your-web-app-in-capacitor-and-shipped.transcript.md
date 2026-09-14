---
type: transcript
lesson: "You wrapped your web app in Capacitor and shipped it as a mobile app. Everything"
course: "The Pit"
author: "Matt Murphy"
post_id: 106197098
published: "2026-08-23T19:00:03Z"
source_url: "https://the-faction.mn.co/posts/106197098"
duration: "2m00s"
words: 313
transcribed_by: "deepgram auto-captions (Mighty)"
---

# Transcript — You wrapped your web app in Capacitor and shipped it as a mobile app. Everything

> You wrapped your web app in Capacitor and shipped it as a mobile app. Everything in LocalStorage is now on a device you do not control. Today I walk through moving secrets to native secure storage, implementing certificate pinning so proxies cannot intercept your traffic, and validating deep links s

You just shipped your web app as a mobile app, and every API key is visible in the device's local storage. Capacitor wraps your web app in a native shell, so everything that was in the browser is now on the device. Local storage, session tokens, API keys, and WebView cache. All of it sitting in the app's data directory where any rooted device or forensic tool can read it. So you did not ship a mobile app.

You shipped your entire client side architecture to a device you do not control. So here is how we're gonna fix it. Step one, move secrets out of client side storage, and I mean API keys, tokens, and credentials. They do not belong in local storage on any mobile device. They belong in a platform secure key chain, whether it's key chain on iOS or key store on Android.

Those are a win. Direct your AI to migrate all sensitive credentials from local storage to the platform's native secure storage using a capacitor secure storage plugin. That's a win. Step two, certificate pinning on every API call. Without certificate pinning, any proxy can intercept your apps traffic.

So a user on a compromised network hands their session token to an attacker. So direct your AI to implement certificate pinning on all API endpoints. So the app will reject any connection not signed by your expected certificate. That's a win. And step three, deep link validation.

Your app registers URL schemes. Without validation, a malicious app can register the same scheme and intercept authentication callbacks, password reset links or even payment confirmations. So direct your AI to implement deep link validation that verifies the origin and signature of every incoming deep link before processing it. Your web app had a browser protecting it. Your mobile app doesn't.

So fix the gaps capacitor left open for you.

---
_Source: https://the-faction.mn.co/posts/106197098_
