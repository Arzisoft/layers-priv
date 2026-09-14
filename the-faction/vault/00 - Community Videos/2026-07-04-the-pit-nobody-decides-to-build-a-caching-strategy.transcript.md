---
type: transcript
lesson: "Nobody decides to build a caching strategy."
course: "The Pit"
author: "Matt Murphy"
post_id: 104111579
published: "2026-07-04T20:00:01Z"
source_url: "https://the-faction.mn.co/posts/104111579"
duration: "3m27s"
words: 575
transcribed_by: "deepgram auto-captions (Mighty)"
---

# Transcript — Nobody decides to build a caching strategy.

> Nobody decides to build a caching strategy.

Nobody just wakes up and says, you know what, I'm gonna build a caching strategy. What really happens is an app gets slow. Somebody adds redisks, the app gets faster, everybody moves on. And six months later, your support inbox is lighting up. Because all of a sudden a customer says they changed their plan to enterprise an hour ago, but the dashboard still shows they're in the free tier.

Or another customer says they purchased a product at the price on the page and their receipt shows a different price altogether. Or your sales team who's looking at inventory numbers that do not match what customers are seeing on the website. These are three totally different problems with the exact same root cause. You added speed without deciding what's allowed to be wrong. So here's the first conversation I have with founders when this lands on their desk.

First you say, what data can be stale and for how long? Your company address, cash it forever. Nobody cares if it's five minutes behind. Your blog posts, cash them for an hour. An old headline costs you nothing at all.

Your product pricing, your user permissions, your inventory counts, your account status. Well, these can never be stale. Not for thirty minutes, not for five minutes, not for one minute. Because stale pricing costs you money on every transaction for the duration of the window. Stale permissions mean a user just deactivated and still has access to your system.

Stale inventory means a customer buys something you can't deliver. And none of these show up as errors in your monitoring system. They actually show up as support tickets, refund requests, trust damage, revenue leakage. The second conversation is who clears the cash when the data changes Most founders cannot answer the question. They do not know because nobody decided.

The cache was added to solve a speed problem and nobody asked what happens when the underlying data moves. Event driven invalidation means the moment the data changes, the cache clears immediately and automatically. If your system relies on a timer instead, every piece of data is wrong for as long as the timer runs. And as you set that timer without asking what wrong cost per minute, the third conversation is the one nobody wants to have and here comes the CFO again. So what happens when cache fails itself?

Your cache expires. A thousand users request the same data at the same moment and every request hits the database simultaneously. The system you built to protect the database is attacking it. This is called a stampede and it does not show up in testing because testing cannot simulate a thousand users hitting the exact same expired key at the exact same second. It shows up on your biggest day though.

Those are launch days or Black Friday or the day you finally get featured or the day you get to take a day off. The companies that handle this well are not the ones with the best engineers, trust me. They're the ones whose leadership understood that caching is not just a performance feature to speed up reads and writes. It's a business decision about how wrong your data is allowed to be and for how long. And most founders made that decision by total accident.

Like I said, they didn't wake up thinking about it. But guess what? We did. Hope that helped.

---
_Source: https://the-faction.mn.co/posts/104111579_
