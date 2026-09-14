---
space: "The Pit"
author: "Matt Murphy"
post_id: 106720283
reactions: 0
comments: 0
published: "2026-09-01T19:00:01Z"
source: "https://the-faction.mn.co/posts/106720283"
---

# You added Sign in with Google and your AI left the redirect URI wide open. An at

You added Sign in with Google and your AI left the redirect URI wide open. An attacker can craft a login link that looks exactly like yours and redirect the token to their server instead of yours. The user thinks they logged in. The attacker has their access token. Today I walk through locking redirect URIs to exact registered URLs, enforcing a state parameter that ties every login request to the user's session, and scoping token permissions to the minimum your app needs. If you added social login to your app, check this.

**PROMPT:** Direct your AI: "Build an OAuth security hardening system with three components: (1) Redirect URI lockdown. Audit every OAuth integration in my application: Google, GitHub, Apple, any third-party SSO provider. For each, verify that the redirect URI is set to an exact, hardcoded callback URL. No wildcards, no pattern matching, no query parameter that can override the redirect destination. Verify the same restriction on the provider's developer console. Test by attempting to initiate an OAuth flow with a modified redirect URI and confirm the provider rejects it. (2) State parameter enforcement. For every OAuth login request, generate a cryptographically random state value tied to the user's current session. Store the state server-side or in a signed, httpOnly cookie. On the OAuth callback, verify the returned state matches the stored value before processing the token. Reject any callback with a missing or mismatched state parameter. Log rejected callbacks as potential CSRF attempts. (3) Scope minimization audit. For each OAuth integration, list every permission scope currently requested. For each scope, verify that the application actually uses the data it grants access to. Remove every scope that is not required for a current feature. Document the remaining scopes with the feature that requires each. Set up monitoring to alert if a scope is added without a corresponding feature justification."

---

## Video transcript

_deepgram auto-captions (Mighty) · 2m10s_

So your AI, it added sign in with Google to your product, but your AI also left the redirect wide open. So someone just sent your users a login link that delivers their token to a server you've never even seen. So your AI, it built OAuth flow. Right? Log in with Google, get a token, redirect back to your app.

But the redirect, that URL is not locked to your domain. And an attacker crafted a login link that looks exactly like yours. So the token gets redirected to their server instead of yours. And your authentication worked perfectly, but it just worked for the wrong person. Let's get that tightened up.

Step one. Lock your redirect URL to exact registered URLs. No wild cards, no pattern matching, no open redirects. Every OAuth provider gives you a white list. If you redirect can point anywhere, your login can be hijacked from anywhere.

So direct your AI to audit every OAuth integration and restrict redirect URLs to exact hard coded callback URLs registered with each provider. That's a win. Step two, enforce a state parameter on every OAuth request. The state parameter ties the login request to the user session. That's so the callback can verify the flow was initiated by your app and not by an attacker.

Without it, anyone can forge an OAuth callback. So direct your AI to generate a unique cryptographically random state value on every login request and reject any callback where that state does not match. That's also a win. And step three, scope your token request to the minimum permissions your app actually needs. So if you requested full profile access and your app only needs an email address, every stolen token gives the attacker more than it should.

So direct your AI to audit every OAuth scope and reduce each to the minimum required for the feature it supports. Your users, they trust that login button, so make sure it only works for them.


---
_Source: https://the-faction.mn.co/posts/106720283_
