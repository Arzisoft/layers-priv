---
space: "The Pit"
author: "Matt Murphy"
post_id: 104007231
reactions: 2
comments: 0
published: "2026-07-01T13:38:46Z"
source: "https://the-faction.mn.co/posts/104007231"
---

# Your error tracker catches errors your code throws.

Your error tracker catches errors your code throws.

It cannot catch the ones your code swallows.

Business metric alerting.

Synthetic transactions.

Dead letter queues.

Monitor what your tools were never built to see.

-MM

[#observability](https://the-faction.mn.co/spaces/23777071/search?term=%23observability) [#businessmetrics](https://the-faction.mn.co/spaces/23777071/search?term=%23businessmetrics) [#monitoring](https://the-faction.mn.co/spaces/23777071/search?term=%23monitoring) [#webhooks](https://the-faction.mn.co/spaces/23777071/search?term=%23webhooks) [#production](https://the-faction.mn.co/spaces/23777071/search?term=%23production)

---

## Video transcript

_deepgram auto-captions (Mighty) · 1m41s_

Your payment webhook failed silently for six hours today. No errors thrown. No alerts fired. No dashboards changed. Here are the three things you want to add right now to fix it.

Step one, business metric alerting. Your infrastructure metrics say the server is healthy. That's not a win because your business metrics say the revenue has stopped. These are different conversations in different systems. You need to track payments per hour, sign ups per hour, and checkout completions per hour.

When sign ups are normal but payments drop to zero, your server is fine but your business is bleeding. You need to alert on your business metrics, not just your server metrics. And that's a win. Step two, synthetic transactions. Run your critical path automatically every five minutes.

Sign up, add to cart, check out, pay and confirm. When step four fails, you know before the customers know. And that's a win. Synthetic monitoring catches failures the error tracking misses because the code did not know it failed. Step three: dead letter queues for webhooks.

When a webhook processes but the business logic fails, the event disappears into a success response. A dead letter queue catches every event where the response was two hundred but the outcome was wrong. So the payment that failed silently sits in the queue waiting for you instead of vanishing. So the lesson is you must monitor the failures your code does not know about because that is where the real money starts leaking out the side door.


---
_Source: https://the-faction.mn.co/posts/104007231_
