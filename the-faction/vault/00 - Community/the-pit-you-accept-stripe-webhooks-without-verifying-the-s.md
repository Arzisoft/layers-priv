---
space: "The Pit"
author: "Matt Murphy"
post_id: 106365604
reactions: 2
comments: 0
published: "2026-08-24T19:00:00Z"
source: "https://the-faction.mn.co/posts/106365604"
---

# You accept Stripe webhooks without verifying the signature. Anyone who knows you

You accept Stripe webhooks without verifying the signature. Anyone who knows your endpoint URL can send a fake payment event and your server will process it. Free products. Fake revenue. Today I walk through signature verification using Stripe's signing secret, idempotency tracking to prevent replay attacks, and endpoint URL protection so your webhook path is not guessable. If you use Stripe and have not verified webhook signatures, fix this today.

**PROMPT:** Direct your AI: "Secure my Stripe webhook integration with three components: (1) Signature verification. Implement webhook signature verification on my Stripe webhook endpoint. Use the official Stripe SDK method to validate the Stripe-Signature header against my endpoint's signing secret. Reject any request where the signature does not match or where the timestamp tolerance is exceeded. Return a 400 status for invalid signatures. Test by sending a request with a modified body and confirming it is rejected. (2) Idempotency. Implement event deduplication on my webhook handler. Log every successfully processed event ID in a persistent store. Before processing any incoming event, check whether the event ID has already been handled. If it has, return a 200 without reprocessing. This prevents replay attacks and duplicate fulfillment from Stripe's built-in retry mechanism. (3) Endpoint hardening. Change my webhook URL from a predictable path to one that includes a random token or hash that is not guessable. Configure my server or firewall to restrict incoming requests on the webhook endpoint to Stripe's published IP ranges. Log all rejected requests for monitoring. Verify by attempting to send a webhook from an IP outside the allowed range and confirming it is blocked."

---

## Video transcript

_deepgram auto-captions (Mighty) · 2m20s_

You accept webhooks from Stripe without verifying the signature. Now anyone can send your server a fake payment confirmation. That's a payment post request that hits your webhook endpoint. The body says payment succeeded. So your server reads that event, marks the order as paid, triggers fulfillment, ships out a product.

However, you never checked whether Stripe actually sent you that request. You see, an attacker who knows your endpoint URL can send the same payload and your server will process it the exact same way. What does that mean? Free products, free subscriptions, fake revenue You see Stripe signs every webhook. It's your server that's ignoring the signature.

Here's how we're gonna fix it. Step one, signature verification on every incoming webhook. Stripe includes a signature header on every event. Your server must validate that signature against your webhook signing secret before processing any event. If the signature doesn't match, reject the request immediately.

So direct your AI to implement Stripe web webhook signature verification using the official SDK method. That will compare the signature headers against your endpoint signing secret, and that's a win. Step two, event item potency to prevent replay attack. An attacker can capture a legitimate webhook and replay it. Your server processes that same payment event twice.

Duplicate fulfillment, duplicate credits, duplicate access. So DirectoryAI to implement item potency tracking. That way, it logs every processed event ID and rejects any event that has already been handled. And step three, endpoint URL protection and IP allow listing. Your webhook URL should not be guessable.

A predictable path like webhooks backslash Stripe is an open invitation. Use a randomized path or token in the URL. Where possible, restrict incoming requests to Stripe's published IP ranges. So DirectoryAI to configure webhook endpoints security with a non guessable URL and IP allow listing based on Stripe's current IP list. Stripe already secured their side.

It's time to secure yours.


---
_Source: https://the-faction.mn.co/posts/106365604_
