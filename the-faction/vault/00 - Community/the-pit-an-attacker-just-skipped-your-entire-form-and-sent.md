---
space: "The Pit"
author: "Matt Murphy"
post_id: 107201665
reactions: 0
comments: 0
published: "2026-09-13T14:00:04Z"
source: "https://the-faction.mn.co/posts/107201665"
---

# An attacker just skipped your entire form and sent raw data straight to your API

An attacker just skipped your entire form and sent raw data straight to your API. Empty strings, negative prices, garbage in every field. Your AI validated everything in the browser with Zod. None of it runs on the server. Direct your AI to run the same Zod schema on the server. Without it, an attacker sends whatever they want to your API endpoint. Your form never sees it. Your database stores whatever arrived. Reject unexpected fields. An attacker adds isAdmin or priceOverride. If your server passes the full body without stripping, those land in your records. Test every API route by sending requests without the form. If the server accepts what the form would reject, the validation is cosmetic. The form catches mistakes. The server catches attacks.

**PROMPT:** You are a full-stack input validation auditor. Review the following application for client-only validation gaps. Check: (1) Identify all Zod schemas used in client-side form components. (2) For each schema, find the corresponding API route. (3) Does the API route validate the request body with Zod BEFORE processing? Flag unvalidated routes as CRITICAL. (4) Does the server schema use .strict() or .strip() for unexpected fields? (5) Are there field mismatches between client and server schemas? (6) Check type coercion mismatches. (7) Are file uploads validated server-side? For each finding, provide the exact server-side Zod validation.

---

## Video transcript

_deepgram auto-captions (Mighty) · 2m05s_

Your AI just let an attacker skip your entire form and send raw data straight to your API. Empty strings, negative prices, garbage in every single field. Your AI validated everything in the browser, but none of it runs on the server. So your AI added Zod validation to your forms, required fields, email format, password length. Right?

Well, it catches everything in the browser, but the server accepts the raw request body without checking it at all. So client validation is a user experience feature. Server validation is a security control. Your AI built one and skip the other. Let's get it fixed.

Number one, your form validates on the client. Your server does not. An attacker sends a request directly to your endpoint. Your form never sees it. Your server processes it without a question, and your database stores whatever arrived.

So Zod runs anywhere JavaScript runs. So your AI treated it as a front end tool. You need to direct your AI to run the same schema on the server. That's the win. Step two, an attacker adds fields your form does not have and is admin flag or a roll override or a price override.

Your server passes the full request body to your database without stripping anything unexpected. So if your schema defines ten fields and the request contains eleven, the eleventh should not exist in your system at all. So DirectoryAI to reject unknown fields from every single request. And number three, every API endpoint is accessible without your front end. Invalid values, extra fields, if the server accepts them, the validation is cosmetic.

Your server must enforce the same rules your form does independently. So direct your AI to test every route by sending a request without the form. The form catches the mistakes. The server catches attacks. That's something you wanna get your hands around for the win.


---
_Source: https://the-faction.mn.co/posts/107201665_
