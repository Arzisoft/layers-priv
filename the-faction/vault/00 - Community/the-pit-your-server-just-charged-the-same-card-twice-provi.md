---
space: "The Pit"
author: "Matt Murphy"
post_id: 107025735
reactions: 0
comments: 0
published: "2026-09-12T19:00:06Z"
source: "https://the-faction.mn.co/posts/107025735"
---

# Your server just charged the same card twice, provisioned the same user twice, s

Your server just charged the same card twice, provisioned the same user twice, sent the same email twice. Every webhook signature was valid. Clerk, Resend, and GitHub all retry failed webhooks. Your AI verified the signature but never handled duplicates. Direct your AI to store every event ID before processing. If it exists, return success and skip. Store first, process second. Set a 24-hour replay window. Without it, an attacker replays a three-month-old webhook with a valid signature. Return success for duplicates. An error triggers another retry. The signature proves the sender. Idempotency proves you only acted once.

**PROMPT:** You are a webhook security auditor. Review the following webhook handler implementations for idempotency gaps. Check: (1) Is the handler extracting and storing the event ID / idempotency key from each webhook payload before processing? (2) Is there a duplicate check before executing business logic? (3) Is the order correct: store ID first, then process? (4) Is there a replay window that rejects events older than a defined threshold? (5) Does the handler return HTTP 200 for duplicate events? (6) Is the idempotency store using an appropriate backend (Redis with TTL, database with unique constraint)? (7) Are webhook retries handled without duplicate side effects? For each finding, provide the exact implementation.

---

## Video transcript

_deepgram auto-captions (Mighty) · 2m38s_

Uh-oh. Your server just charged the same credit card twice, provisioned the same user twice, and sent the exact same email to them twice, but every webhook signature was totally valid, and that, quite frankly, is the problem. So your AI verified the webhook signature, Clerk, resend, and GitHub all retry failed webhooks. Right? But your server processes the same valid event two times.

So signature verification is step one. Item potency is step two, but your AI stopped at step one. So let's get it fixed. Number one, direct your AI to store every event ID before it processes the handler logic. Check the ID against your database.

If it already exists, return a success response and do nothing at all. If it does not, store it, then process it. The order definitely matters. Store first, process second. If the handler crashes mid process, the retry sees the stored ID and skips the duplicate process.

Without this, every network timeout, every slow response, every infrastructure hiccup triggers a retry with a valid signature that your server treats as a brand new event. So a user provisioned twice, a payment recorded twice, and an email sent twice, that webhook wasn't forged folks. It was just delivered more than once and that is not a win. Number two, set a replay window. Reject event IDs older than twenty four hours.

Without a window, your storage grows indefinitely and an attacker can replay a captured webhook from three months ago with a valid signature. So a timestamp checks close that gap permanently. Direct your AI to compare the event's creation time against a twenty four hour threshold and reject anything outside of it. That's a win. And number three, return a success response for all duplicates.

Right? If your server returns an error on a duplicate event, the provider will retry it again. So more duplicates equals more duplicate processing, which equals more duplicate emails. That's not a win. So a success response tells the provider the event was received even if your server already handled it, especially if your server already handled it.

Right? So the signature proves the sender. Item potency proves you only acted once. And that, that's the double check system that works.


---
_Source: https://the-faction.mn.co/posts/107025735_
