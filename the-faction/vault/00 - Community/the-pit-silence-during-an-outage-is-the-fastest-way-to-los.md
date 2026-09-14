---
space: "The Pit"
author: "Matt Murphy"
post_id: 105032688
reactions: 2
comments: 0
published: "2026-07-24T19:07:55Z"
source: "https://the-faction.mn.co/posts/105032688"
---

# Silence during an outage is the fastest way to lose every customer you earned.

Silence during an outage is the fastest way to lose every customer you earned.

Your AI built the product but never built the system that tells your customers the product is still alive. Today I walk through three things: a public status page on a separate domain, a scheduled maintenance announcement system, and an incident communication workflow with pre-loaded templates.

-MM

ORCHESTRATION PROMPT

Direct your AI: "Build a complete incident communication system for my SaaS application with three components: (1) A public status page deployed on a separate subdomain and separate hosting provider from my main application, with component-level status indicators (API, web app, database, payments, email). (2) A scheduled maintenance announcement system that sends email notifications to active subscribers 24 hours before planned downtime, posts to the status page, and displays an in-app banner. (3) An incident response workflow template with severity levels, communication intervals (update every 30 min for critical, every 2 hours for degraded), email notification templates, and a post-incident report structure."

---

## Video transcript

_deepgram auto-captions (Mighty) · 2m14s_

Your app went down when you were asleep, and now your customers think you stole their money. Six hours of downtime, no status page, no status updates, no maintenance announcement, no communication to the users of any kind. And this is all because your AI never built you a status system. Here are three things you direct your AI to build before your next outage becomes a trust crisis. Step one, a public status page on a separate domain altogether, not hosted on your main infrastructure because when your app goes down, your status page goes down with it.

So your AI can deploy a standalone status page in twenty minutes on a completely separate host. The difference between the site is down and I have no idea why and we know and we are trying to fix it is the difference between a chargeback and patience. Right? And that's a win if you get it right. Step two, a scheduled maintenance announcement system.

Every application needs downtime. The builders who announce maintenance windows in advance, they look professional. The builders who take their app down at two pm on a Tuesday afternoon with no warning look pretty amateur. So your AI can build an automated notification system that emails active users before scheduled downtime and posts it to your status page so your customers do not mind planned downtime. They don't mind it at all.

They mind surprises and time that they had set aside that you didn't notify them. And step three, an incident communication workflow. When an outage hits, you need a status page update with defined intervals, email notifications to active subscribers, and an estimated restoration time, even if it's just a guess. Silence during an outage is what turns technical problems into a reputation and revenue problem. Your AI can build the entire workflow with templates preloaded and triggers fully automated, but it'll never build it on its own because it does not know that silence is the fastest way to lose every customer you earned.

So your AI built a product and never built the system, it tells your customers the product is still alive even when it isn't. So direct your AI to build it before your next outage costs you more than just a little bit of downtime.


---
_Source: https://the-faction.mn.co/posts/105032688_
