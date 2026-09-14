---
space: "The Pit"
author: "Matt Murphy"
post_id: 106761639
reactions: 0
comments: 0
published: "2026-09-02T19:00:00Z"
source: "https://the-faction.mn.co/posts/106761639"
---

# Your AI integrated Stripe and the price lives in the frontend request body. Chan

Your AI integrated Stripe and the price lives in the frontend request body. Change it to a dollar and Stripe processes it because your server trusts whatever the client sends. Today I walk through creating checkout sessions server-side with prices from your database instead of the client request, using Stripe Price IDs so the amount is locked in Stripe's system and no code can override it, and verifying payment through webhooks before granting access to anything. If your AI set up your Stripe checkout and you have never tested what happens when you change the price in the request, test it today.

**PROMPT:** Direct your AI: "Perform a Stripe checkout security audit and hardening with three components: (1) Server-side price enforcement. Move all Stripe Checkout Session creation to server-side endpoints. The client should send only a product identifier, never a price or amount. The server must look up the product price from the database and pass only the verified amount to the Stripe API. Reject any client request that includes a price field. Verify by intercepting a checkout request, modifying the product price in the request body, and confirming the server ignores the modified value and charges the correct database price. (2) Stripe Price ID migration. Replace all raw dollar amounts in checkout session creation with Stripe Price IDs created in your Stripe dashboard and linked to Product objects. When a checkout session references a Price ID, the charge amount is controlled by Stripe's system and cannot be manipulated by client or server code. Verify that no raw amount or unit_amount appears in any checkout session creation call. (3) Webhook payment verification. Implement a Stripe webhook endpoint that listens for payment_intent.succeeded and checkout.session.completed events. Verify the webhook signature using your Stripe webhook signing secret. Confirm the paid amount matches your product price before provisioning access. Verify by navigating directly to your checkout success URL without completing payment and confirming access is not granted."

---

## Video transcript

_deepgram auto-captions (Mighty) · 2m05s_

Your AI built your Stripe checkout. The price lives in your front end. So if you change it to one dollar, Stripe will still process it. So your AI integrated Stripe, your user clicks the buy button, your front end sends a checkout request with the price in the body, and Stripe charges whatever amount your code sends. So your server never checks whether that number matches your actual product pricing, and that's the hack.

So now your checkout is just a suggestion. Here's how we're gonna make it a contract. Step one, create checkout sessions on your server with prices from your database. The client sends a product ID, never a dollar amount. So your server looks up the price, creates the Stripe session with the verified amount, and returns the session to the client.

So direct your AI to move all Stripe session creation to a server endpoint that ignores any price the front end sends. That's definitely a win. Step two. Use Stripe price IDs instead of raw dollar amounts. So Stripe will let you create price objects tied to your products in your dashboard.

So when your server references a price ID, the charge amount is locked inside of Stripe's system. So no code on your side can ever override it. So direct your AI to replace every raw amount in your checkout flow with a Stripe price ID. That's a win. And number three, verify payment through webhooks before granting any access.

Your checkout success page is not proof of payment. A user can still navigate to your success URL without paying. So direct your AI to implement a Stripe webhook listener so that it confirms the payment event, validates the amount against your product price, and only then provisions access to the purchase resource. Your checkout folks is not your pricing, your server is. And right now, your server believes whatever the browser is telling it at checkout.

So let's get it cleaned up. That's a win.


---
_Source: https://the-faction.mn.co/posts/106761639_
