---
space: "The Forge"
author: "Matt Murphy"
post_id: 103132314
reactions: 3
comments: 5
published: "2026-06-10T21:05:25Z"
source: "https://the-faction.mn.co/posts/103132314"
---

# 19 — The Ten-Decisions Gate

19 — The Ten-Decisions Gate

Ten questions to ask any AI vendor before signing. If they can't answer question four — what happens to your data if they go out of business — walk. The gate protects you from contracts that look great in month one and trap you by month twelve.

---

## Discussion

**Anurag Kapse** · 2026-07-15

> Hello [Matt Murphy](https://the-faction.mn.co/members/39706849): New to this platform here. This post stuck me, because agaian security/data are always important to cover. What is your advice on what should happen for #4? My honest take without googling it, says the data should be actioned as per data retention policy of the region the product is serving.

  ↳ **Matt Murphy** · 2026-07-15

  > First off, Anurag, welcome to the Faction, honored to have you here! Secondly great question. #4 isn’t about retention, it’s about business continuity. If you disappear tomorrow, how do I get my data back, in what format, how long do I have, and who pays for the extraction? If those answers aren’t already in the contract, keep asking. That’s the risk.💯👊😎

**Anurag Kapse** · 2026-07-17

> Honoured to be part of this group :)
> And yep that makes sense, thank you for sharing.

**Tom Boudreau** · 2026-08-21

> Along with number 6 (SLA Uptime), I find myself asking the question what happens to my application/system if the API is not available. Does it shut me down too? What's my work-around to keep my business running.

  ↳ **Matt Murphy** · 2026-08-22

  > [Tom Boudreau](https://the-faction.mn.co/members/40482827) That’s really the second half of the uptime question. A vendor can promise 99.9% availability, but what does my system do during the other 0.1%?
  > 
  > I never want a third-party API outage to automatically become my application outage.
  > 
  > For anything business-critical, I’d design for graceful degradation.
  > 
  > That usually means some combination of timeouts and retries, circuit breakers so you stop hammering a dead service, queues for work that can complete later, cached or last-known-good data where appropriate, and a fallback path for anything the user still needs to accomplish manually.
  > 
  > For AI specifically, I also like a provider abstraction layer.
  > 
  > Your application talks to your interface, not directly to one vendor everywhere in the codebase. That gives you the option to route to another model/provider or even a local model if the primary service is unavailable, assuming the use case allows it.
  > 
  > And then categorize the dependency: Does this API enhance the product, or does the business literally stop without it? If the answer is “the business stops,” redundancy and a documented outage procedure are table stakes.
  > 
  > That’s the mindset I’d add to #6: don’t just ask for their SLA. Ask yourself what’s my SLA when theirs fails, Murphy’s Law! 👊😎


---
_Source: https://the-faction.mn.co/posts/103132314_
