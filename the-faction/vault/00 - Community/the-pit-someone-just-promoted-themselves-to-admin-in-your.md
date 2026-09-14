---
space: "The Pit"
author: "Matt Murphy"
post_id: 107025535
reactions: 0
comments: 0
published: "2026-09-09T14:00:05Z"
source: "https://the-faction.mn.co/posts/107025535"
---

# Someone just promoted themselves to admin in your app by editing one field in a

Someone just promoted themselves to admin in your app by editing one field in a JWT. Your AI integrated Clerk and reads the JWT to check roles. It never verifies the signature. A user decodes their JWT, changes "member" to "admin," and sends it back. Full access. Verify the signature on every request using Clerk's public key. A modified token without a valid signature gets rejected immediately. Validate expiration and issuer. An expired token or one from a different Clerk instance should never pass. Use Clerk's server-side SDK instead of manual parsing. It handles verification, validation, and key rotation. Every manual implementation makes this exact mistake. Your auth provider did its job. Your AI never verified its work.

**PROMPT:** You are a Clerk authentication auditor. Review the following application for JWT verification gaps. Check: (1) Is the JWT signature being verified against Clerk's JWKS endpoint on every API request? Flag any route that reads JWT claims without signature verification as CRITICAL. (2) Is the issuer (iss) claim validated against the expected Clerk instance URL? (3) Is the expiration (exp) claim checked? (4) Is the audience (aud) claim validated if set? (5) Is the application using Clerk's server-side SDK (@clerk/nextjs, @clerk/express) or manually parsing JWTs? Flag manual parsing as HIGH risk. (6) Are any routes using client-side session data for authorization decisions? (7) Is JWKS key rotation handled (caching with refresh)? For each finding, provide the exact fix using Clerk's recommended server-side verification approach.

---

## Video transcript

_deepgram auto-captions (Mighty) · 2m26s_

Someone just promoted themselves to admin in your AI app by editing one field in a JWT. Your server granted access because your AI never verified the signature, So your AI integrated clerk and reads the JWT file to check the roles, but it never verifies the signature and it never checks the expiration. So a modified token passes your middleware without any challenge at all. Here's how you're gonna direct your AI to verify every token before it trusts a single claim. Number one, verify the signature on every request.

Clerk signs every token with a key pair. Your server must validate that signature before reading any claim. Without verification, a user decodes their own JWT, changes the role from member to admin, re encodes it, and sends it right back. So your server reads admin and grants access to every protected route in your app to that attacker. No alert, no log entry, full admin access to anyone who knows how a JWT works.

So your AI read the claims without checking whether the envelope was sealed. That's not a win. Step two, validate expiration and the issuer. An expired token should never grant any access. A token from a different clerk instance should never be trusted.

Without these two checks, a stolen token works forever and a token from a completely different application passes your middleware without any challenge. So direct your AI to reject anything that's expired or issued by the wrong source. That is a win. And step three, use Clerk's server side SDK instead of parsing manually. The SDK can handle signature verification, claim validation, and key rotation automatically.

So every manual JWT implementation makes this exact same mistake because the shortcut always looks like it works to the AI. Right? Well, it does work for honest users. But the moment someone modifies a token intentionally, your entire authorization layer disappears to an attacker. The SDK literally exists because this mistake happens in every manual implementation.

So your auth provider did its job. Your AI never verified the work. That's not a win. Get it fixed.


---
_Source: https://the-faction.mn.co/posts/107025535_
