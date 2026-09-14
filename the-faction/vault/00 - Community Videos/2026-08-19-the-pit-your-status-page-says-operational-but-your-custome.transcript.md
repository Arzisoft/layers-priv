---
type: transcript
lesson: "Your status page says operational but your customers are screenshotting error me"
course: "The Pit"
author: "Matt Murphy"
post_id: 106084561
published: "2026-08-19T19:00:25Z"
source_url: "https://the-faction.mn.co/posts/106084561"
duration: "2m13s"
words: 353
transcribed_by: "deepgram auto-captions (Mighty)"
---

# Transcript — Your status page says operational but your customers are screenshotting error me

> Your status page says operational but your customers are screenshotting error messages in your support channel. Today I walk through defining error budgets per critical endpoint so you know how much failure your business can afford, burn rate alerting that catches dangerous trends before they become

Your status page is saying fully operational, but your customers are screenshotting error messages in your support channel right now. So you have no idea which endpoints are failing, which customers are affected, and how much revenue those failures are costing you because your monitoring is telling you the system is up when it's down. And it never tells you how much failure your business can actually afford. So here's what tier three reliability engineering looks like for your platform. Step one, a defined error budget per critical endpoint.

Not a global uptime number, a budget. Your payment endpoints get a point one percent error budget per rolling thirty day window. Out of a hundred thousand requests, a hundred can fail before you're in violation. When you're within budget, ship features. When you're burning budget, freeze deploys and fix your reliability.

So direct your AI to define error budgets for your three highest revenue endpoints based on business impact, not infrastructure defaults. That's a win. Step two, burn rate alerting that catches trends before they become outages. If your thirty day error budget is fifty percent consumed in forty eight hours, something changed and you are on track for a breach. Burn rate alerts measure the speed at which your budget is being consumed and fire when the trajectory is unsustainable.

So direct your AI to calculate burn rate on each error budget. An alert when projected consumption will exhaust the budget before the window resets. That's a win. Step three business cost attribution on every single incident. Not the API return five hundred for errors in twelve minutes, but how many users were affected, how many transactions failed, and what the revenue impact was.

An incident on your documentation page and your incident on your checkout page are not the same severity levels. You have to prioritize them. So direct your AI to instrument business metric correlation so incidents are measured in dollars lost, not status codes logged. Ninety nine point nine percent uptime is not a badge, it's a budget. Direct your AI to start spending it like it is one.

---
_Source: https://the-faction.mn.co/posts/106084561_
