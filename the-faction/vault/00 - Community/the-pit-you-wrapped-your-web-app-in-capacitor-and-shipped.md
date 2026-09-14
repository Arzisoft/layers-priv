---
space: "The Pit"
author: "Matt Murphy"
post_id: 106197098
reactions: 1
comments: 0
published: "2026-08-23T19:00:03Z"
source: "https://the-faction.mn.co/posts/106197098"
---

# You wrapped your web app in Capacitor and shipped it as a mobile app. Everything

You wrapped your web app in Capacitor and shipped it as a mobile app. Everything in LocalStorage is now on a device you do not control. Today I walk through moving secrets to native secure storage, implementing certificate pinning so proxies cannot intercept your traffic, and validating deep links so malicious apps cannot hijack your authentication callbacks.

**PROMPT:** Direct your AI: "Secure my Capacitor mobile application with three components: (1) Secure credential storage. Identify all sensitive data currently stored in LocalStorage or SessionStorage: API keys, auth tokens, session identifiers. Migrate each to the platform's native secure storage: iOS Keychain or Android Keystore via a Capacitor secure storage plugin. Remove all sensitive data from LocalStorage. (2) Certificate pinning. Implement SSL certificate pinning on all API calls. Pin the expected certificate or public key hash for every API endpoint. The app should reject connections to any endpoint presenting an unexpected certificate. Test by attempting a connection through a proxy and confirming the app rejects it. (3) Deep link security. Audit all registered URL schemes and universal links. Implement validation on every incoming deep link: verify the origin domain, validate any tokens or parameters, and reject links that do not match expected patterns. Test by sending a crafted deep link from an external source and confirming the app rejects it."

---

## Video transcript

_deepgram auto-captions (Mighty) · 2m00s_

You just shipped your web app as a mobile app, and every API key is visible in the device's local storage. Capacitor wraps your web app in a native shell, so everything that was in the browser is now on the device. Local storage, session tokens, API keys, and WebView cache. All of it sitting in the app's data directory where any rooted device or forensic tool can read it. So you did not ship a mobile app.

You shipped your entire client side architecture to a device you do not control. So here is how we're gonna fix it. Step one, move secrets out of client side storage, and I mean API keys, tokens, and credentials. They do not belong in local storage on any mobile device. They belong in a platform secure key chain, whether it's key chain on iOS or key store on Android.

Those are a win. Direct your AI to migrate all sensitive credentials from local storage to the platform's native secure storage using a capacitor secure storage plugin. That's a win. Step two, certificate pinning on every API call. Without certificate pinning, any proxy can intercept your apps traffic.

So a user on a compromised network hands their session token to an attacker. So direct your AI to implement certificate pinning on all API endpoints. So the app will reject any connection not signed by your expected certificate. That's a win. And step three, deep link validation.

Your app registers URL schemes. Without validation, a malicious app can register the same scheme and intercept authentication callbacks, password reset links or even payment confirmations. So direct your AI to implement deep link validation that verifies the origin and signature of every incoming deep link before processing it. Your web app had a browser protecting it. Your mobile app doesn't.

So fix the gaps capacitor left open for you.


---
_Source: https://the-faction.mn.co/posts/106197098_
