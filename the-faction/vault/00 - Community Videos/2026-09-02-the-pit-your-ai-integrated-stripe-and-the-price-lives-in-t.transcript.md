---
type: transcript
lesson: "Your AI integrated Stripe and the price lives in the frontend request body. Chan"
course: "The Pit"
author: "Matt Murphy"
post_id: 106761639
published: "2026-09-02T19:00:00Z"
source_url: "https://the-faction.mn.co/posts/106761639"
duration: "2m05s"
words: 333
transcribed_by: "deepgram auto-captions (Mighty)"
---

# Transcript — Your AI integrated Stripe and the price lives in the frontend request body. Chan

> Your AI integrated Stripe and the price lives in the frontend request body. Change it to a dollar and Stripe processes it because your server trusts whatever the client sends. Today I walk through creating checkout sessions server-side with prices from your database instead of the client request, us

Your AI built your Stripe checkout. The price lives in your front end. So if you change it to one dollar, Stripe will still process it. So your AI integrated Stripe, your user clicks the buy button, your front end sends a checkout request with the price in the body, and Stripe charges whatever amount your code sends. So your server never checks whether that number matches your actual product pricing, and that's the hack.

So now your checkout is just a suggestion. Here's how we're gonna make it a contract. Step one, create checkout sessions on your server with prices from your database. The client sends a product ID, never a dollar amount. So your server looks up the price, creates the Stripe session with the verified amount, and returns the session to the client.

So direct your AI to move all Stripe session creation to a server endpoint that ignores any price the front end sends. That's definitely a win. Step two. Use Stripe price IDs instead of raw dollar amounts. So Stripe will let you create price objects tied to your products in your dashboard.

So when your server references a price ID, the charge amount is locked inside of Stripe's system. So no code on your side can ever override it. So direct your AI to replace every raw amount in your checkout flow with a Stripe price ID. That's a win. And number three, verify payment through webhooks before granting any access.

Your checkout success page is not proof of payment. A user can still navigate to your success URL without paying. So direct your AI to implement a Stripe webhook listener so that it confirms the payment event, validates the amount against your product price, and only then provisions access to the purchase resource. Your checkout folks is not your pricing, your server is. And right now, your server believes whatever the browser is telling it at checkout.

So let's get it cleaned up. That's a win.

---
_Source: https://the-faction.mn.co/posts/106761639_
