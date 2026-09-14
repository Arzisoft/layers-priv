---
space: "The Mentoring Lounge"
author: "K D"
post_id: 106719735
reactions: 1
comments: 3
published: "2026-09-01T01:07:45Z"
source: "https://the-faction.mn.co/posts/106719735"
---

# My app violates stripe's terms of use. Should I switch to a different processor?

My app violates stripe's terms of use. Should I switch to a different processor?

I am currently developing an online chess tournament app that allows users to collect entree fees and distribute prize funds by themselves . I recently found out this falls under stripe's Gambling section in their Prohibited and Restricted Business category only after finishing integrating stripe into my app.

Is it possible to appeal and gain permission to continue using stripe? Would you recommend me switching to a different, high risk payment processor? If I switch processors, is it better to continue to code using the same project or would it be faster to create a new project entirely?

My current app was also prompted without caching, auth, error logging, RLS in mind (I coded it before joining the faction)

---

## Discussion

**Matt Murphy** · 2026-09-01

> KD, good catch finding this before you started moving real money. That’s exactly the kind of discovery that should stop feature work for a minute.
> 
> First: based on Stripe’s current policy, this isn’t just a gray area. Their prohibited-business list specifically includes games of skill with monetary/material prizes and entry fees where the participant can win something of value. That maps pretty closely to the tournament model you described.
> 
> I’d still contact Stripe and describe the exact flow in writing, but I would not process a dollar until you have explicit written approval. I also wouldn’t simply swap in a “high-risk processor” and assume the problem is solved.
> 
> You need a processor that explicitly supports your business model and the jurisdictions where your players operate. The legal classification of skill contests, entry fees, prize pools, and payouts can vary by location, so this is one of those places where qualified counsel is worth the money.
> 
> Technically, though, **d**o not rebuild the whole application just because the processor changes. Refactor the payment layer.
> 
> Think like this:
> 
> App →
> 
> Payment Service →
> 
> Stripe Adapter / Other Processor Adapter
> 
> Your tournament logic, users, brackets, entitlements, prize calculations, etc. should not know or care which processor sits underneath. Then changing providers becomes an adapter problem instead of a rewrite.
> 
> The bigger thing that caught my eye is your last sentence. If this application was originally built without auth, RLS/tenant isolation, error logging, and the other production layers in mind, and now you’re adding entry fees and prize money, I’d pause and harden the architecture before launch.
> 
> For this kind of system I’d consider non-negotiable:
> 
> -proper auth/RBAC and tenant boundaries
> 
> -signed/verified payment webhooks
> 
> -idempotency around charges and payouts
> 
> -an auditable transaction ledger
> 
> -reconciliation between your ledger and the processor
> 
> -explicit tournament/payout state machines
> 
> -logging and alerting
> 
> -protection against duplicate payouts
> 
> -recovery procedures when a payment succeeds but your app fails halfway through
> 
> -Caching is way down the priority list compared with those.
> 
> So my order would be: validate the business model legally → get a processor that explicitly supports it → harden the existing application → abstract the payment provider → then resume feature work.
> 
> I would only start from scratch if an architecture review shows the current codebase is genuinely cheaper to replace than remediate. “I didn’t know about the 13 layers when I built it” does not automatically mean throw it away. It means you’ve got a perfect candidate to run through them now. 👊😎

  ↳ **K D** · 2026-09-02

  > Hi Matt,
  > 
  > Thank you so much for the advice! I did some research into the legality of the app and consulted an attorney. There is just too much legal issues that I could encounter and because I would not have the time to deal with them if one occured, I decided to move on to another project. Thanks again for the help!

  ↳ **Matt Murphy** · 2026-09-02

  > [K D](https://the-faction.mn.co/members/40989451)you likely made the right decision, on to the next! 💪😎


---
_Source: https://the-faction.mn.co/posts/106719735_
