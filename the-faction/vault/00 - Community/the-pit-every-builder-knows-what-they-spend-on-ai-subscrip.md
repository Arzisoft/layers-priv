---
space: "The Pit"
author: "Matt Murphy"
post_id: 105453537
reactions: 2
comments: 2
published: "2026-08-03T14:00:01Z"
source: "https://the-faction.mn.co/posts/105453537"
---

# Every builder knows what they spend on AI subscriptions. None of them know what

Every builder knows what they spend on AI subscriptions. None of them know what it costs to serve a single customer. Today I walk through cost-per-feature instrumentation, revenue-per-user versus cost-per-user modeling, and building a monthly P&L your AI updates automatically. If you are running a product and you do not know your numbers, start here.

**PROMPT:** Direct your AI: "Build a financial visibility system for my AI-powered product with three components: (1) Cost-per-feature instrumentation. Track token consumption and API costs by endpoint and feature. For each user-facing feature, calculate the average cost per invocation and flag any feature where cost per use exceeds $0.10. (2) Per-user profitability model. For each pricing tier, calculate average monthly revenue per user minus average monthly infrastructure cost per user (compute, storage, tokens, third-party APIs). Flag any tier where cost exceeds revenue. (3) A monthly P&L template that auto-populates from my payment processor (Stripe) and hosting dashboard. Track: gross revenue, refunds, net revenue, hosting costs, token/API costs, third-party service costs, and net margin. Output as a dashboard I can review monthly."

---

## Video transcript

_deepgram auto-captions (Mighty) · 2m16s_

Nobody's out there measuring whether their AI build is actually making any money. You can tell me what you're paying for your AI subscription, maybe some of your tools, but you cannot tell me exactly what it costs to serve a single customer. That is the gap between building products and running a business. So here are three things you direct your AI to help you measure before you send your next invoice. Step one, cost per feature.

Not your total monthly bill, but what each feature cost for you to run. Your AI can break down your token consumption by endpoint, by feature, and by user action. Some features cost pennies. Some cost dollars, maybe more. And you have no idea which is which because you've never asked it.

So right now, direct your AI to instrument token tracking per feature so you know where your money is actually going. The feature your customers love the most might be the one eating your margins alive. So figure it out. That's a win. Step two, revenue per user versus cost per user.

Your subscription brings in a fixed amount per customer per month. Your infrastructure costs scale with how much each customer uses your product. If your heaviest user costs you more to serve than they pay you, that's not a customer folks. That's a liability and it's not going to grow. Direct your AI to build a per user cost model so you can see which tier of customer is profitable and which one is burning all your cash.

Step three, a monthly P and L that your AI updates automatically. Not a spreadsheet you fill in once and forget, a living document that tracks revenue in, infrastructure costs out, token consumption by user, and margin by product line. Direct your AI to pull from your payment processor and your hosting dashboard and reconcile them monthly. Your CFO will love it. The builders who know their numbers, they make big decisions and win.

The builders who do not know their numbers make guesses and lose. Your AI can build a product. It cannot tell you if the product is worth running or making you any money. That's a CEO decision. Get out there and make it.


---

## Discussion

**Nicholas Carmona** · 2026-08-03

> Using this today!
> 
> Only question I have for this, the start up I work for the product uses so many different tools/TPA that I think this might be an issues on getting this calculated, will report back later

  ↳ **Matt Murphy** · 2026-08-03

  > Bro, that’s exactly where the real work is. The math is easy once the usage data is trustworthy, the challenge is getting ten different vendors and APIs to speak the same financial language, right. 😂
  > 
  > If it were me I’d start by creating one internal cost ledger rather than trying to calculate everything inside each tool.
  > 
  > Every external call should write a normalized event with the customer or tenant ID, feature, provider, model or service used, units consumed, estimated cost, and a correlation ID tying it back to the original request.
  > 
  > Some providers will give you exact usage and cost through their APIs. Others will only expose tokens, requests, minutes, storage, or monthly invoices, so you’ll need to maintain your own pricing table and reconcile it against the actual bill each month.
  > 
  > The important part is not achieving perfect accounting on day one. Get directional visibility first: which customers, features, and third-party services are consuming the most money? Then tighten the model as the data improves.
  > 
  > Definitely report back. A product using several TPAs is the perfect real-world stress test for this, and I think a lot of builders here are about to discover they have the same problem. 👊😎


---
_Source: https://the-faction.mn.co/posts/105453537_
