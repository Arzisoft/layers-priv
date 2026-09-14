---
type: transcript
lesson: "Untested code is a financial decision most builders never run the math on. This"
course: "The Pit"
author: "Matt Murphy"
post_id: 104635926
published: "2026-07-16T16:00:00Z"
source_url: "https://the-faction.mn.co/posts/104635926"
duration: "2m31s"
words: 401
transcribed_by: "deepgram auto-captions (Mighty)"
---

# Transcript — Untested code is a financial decision most builders never run the math on. This

> *Untested code is a financial decision most builders never run the math on. This is the business cost of every flow your AI built but nobody verified.*

Your AI sure does build fast. Your team, they're shipping fast too. And your customers, they're the first ones to test anything. It's costing you more than you think. Step one to solve this problem.

The flow that nobody checked. Your checkout works with credit cards. Your team tested credit cards. That's great. But a customer pays with PayPal, the payment processes but the confirmation email never fires.

The order appears in the database but the customer sees a blank screen. So what do they do? What would you do? Try again. Guess what?

Two charges, zero confirmation. That's not a code bug. That's a business failure on your behalf. The customer contacts their bank, files a dispute, you lose the revenue, you pay the chargeback fee, and you likely lose a customer who's never going to return. And they're going to tell other people not to come either.

So one untested payment flow costs you a customer and maybe more, the revenue, the chargeback penalty. And the AI, well, it built the whole checkout. It worked for the path you tested, but nobody asked it to test or verify the other pass for payment. That's not a win. Step two, the cost of mobile.

Your app works on desktop. Your team uses it on desktop. Your AI built it for desktop. But forty percent of your users, they're on mobile. The sidebar overlaps the content.

The checkout button is below the fold. The upload fails because mobile browsers handle it completely differently. So each mobile user represents acquisition costs that you've already spent. So they've arrived, they've tried, and now they've left. That's not a win either.

And step three, the math. The math. Customer acquisition cost thirty bucks. An untested flow that breaks for twenty percent of your users means twenty percent of the acquisition spend is wasted. So let's say a thousand users at thirty dollars each.

Make up for twenty percent failure equals six thousand dollars gone. A test suite that catches PayPal flow in the mobile layout cost you two hours of time. Two hours versus the six thousand dollars in customers you just lost. Most builders never run this math because they do not think testing is a financial decision. However, it is the most important financial decision your product makes every single day with every single customer.

You've gotta get ahead of these things.

---
_Source: https://the-faction.mn.co/posts/104635926_
