---
type: transcript
lesson: "Most builders have never heard the word dunning while it quietly kills their rev"
course: "The Pit"
author: "Matt Murphy"
post_id: 104876614
published: "2026-07-21T19:49:55Z"
source_url: "https://the-faction.mn.co/posts/104876614"
duration: "2m11s"
words: 352
transcribed_by: "deepgram auto-captions (Mighty)"
---

# Transcript — Most builders have never heard the word dunning while it quietly kills their rev

> Most builders have never heard the word dunning while it quietly kills their revenue every month. A credit card expires, the charge fails, your app does nothing, and a paying customer just disappeared. Today I walk through three things: a retry schedule, a failed payment email sequence, and a grace 

Your revenue is disappearing before your eyes every month and you can't even see it. Right now, a customer's credit card just expired. The charge failed. Your app did nothing. No retry.

No notification. No email at all. That subscription just silently died and that customer is gone forever. They do not even know what happened. It's called dunning.

And most builders, they don't even know the word dunning exists while it quietly is bleeding them dry. Here are three things you direct your AI to build before your MRR becomes a ghost town. Step one, a retry schedule that fights for the payment before it dies. When a charge fails, your system should be trying on a staggered sequence over the next seven to fourteen days, not one and done. The strategic cadence that catches cards that were temporarily declined or expired and got reissued in that window of time.

Stripe supports this natively, but your AI will never configure it because it thinks a failed charge is the final answer. It's not. It's a recoverable event. Step two, a failed payment needs an email sequence. Your customer is not ignoring you.

They have no idea their card has failed. A three email sequence that says your payment failed, here's how to update your card recovers up to thirty to forty percent of failed charges. That is a revenue you already earned walking out the back door. All because nobody told the customer what just happened. And step three, a grace period before cancellation.

When retries fail and emails go unanswered, your system needs a defined window before it kills the subscription altogether, not instant cancellation or first failure. A seven to fourteen day buffer where the account stays active. The difference between a hard cutoff and a grace period is thousands of dollars per month walking out versus walking back in. Your AI built the front door to your revenue, but it never noticed your customers were walking out the back door. So you need to direct your AI to lock the back door before your next payment cycle runs.

---
_Source: https://the-faction.mn.co/posts/104876614_
