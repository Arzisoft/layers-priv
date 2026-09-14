---
space: "The Pit"
author: "Matt Murphy"
post_id: 104635926
reactions: 1
comments: 3
published: "2026-07-16T16:00:00Z"
source: "https://the-faction.mn.co/posts/104635926"
---

# Untested code is a financial decision most builders never run the math on. This

*Untested code is a financial decision most builders never run the math on. This is the business cost of every flow your AI built but nobody verified.*

*-MM*

**ORCHESTRATION PROMPT: **

*Audit my application for untested critical paths. List every payment method, authentication flow, and core user journey. For each path, generate end-to-end tests including edge cases like failed payments, duplicate submissions, mobile viewport rendering, and browser-specific handling. Generate a report showing which critical paths have zero test coverage.*

---

## Video transcript

_deepgram auto-captions (Mighty) · 2m31s_

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

## Discussion

**Alan Joyce** · 2026-07-17

> 🫡 word of mouth can make or break a business, in Ireland we had this paper company I wont name it but the ran a wedding fair every year, one year a cake company decided they would have gay cake toppers (the little things they add to the top of the cake like bride and groom) anyway this year they had two grooms and a variety of other delights. the owner of the paper company gave out and said that to be taken off the cake you cant have that, owner of the cake shop said well I paid to be here, il display what I want and if you dont like it it wont end well for you. three months later people boycotted the shop in communion with the gays and their rights I know its off topic but I wanted to express that word of mouth about bad transactions and not looking after people can ruin you. He closed his business down got a shed load of bad press and nasty calls and lets just say like it was suggested it didnt end well for him. some people wont complain but bad mouth you, some people will make a fuss about small things and become a Karen, others wont even know there is issues, but they are all unique and all have power in some for. so I get it, test, test and then break and test and test again, and have some system that aren't all running not he same server to test? workflow and playbook is it to be bespoke for each app / platform or is there a golden rule book. :) asking for a friend , my alter Ego.

  ↳ **Matt Murphy** · 2026-07-17

  > Alan, that's actually a great example. Most software failures don't happen because the code crashes, they happen because the customer loses confidence. One bad experience at the wrong moment can undo months or years of good work.
  > 
  > As for your question, there isn't a universal playbook because every application has different business risks. A banking app, a CRM, a healthcare platform, and an e-commerce site all have different critical paths. The framework stays the same, though: identify the revenue paths, security paths, and trust paths first, then test those relentlessly before worrying about edge features.👊😎

**Alan Joyce** · 2026-07-18

> It will all eventually click in to place in my brain. The more I immerse myself in to the actually doing part, I have added antigravity and codex in my projects to update in to "Obsidian" with what i've been doing, so I get more of a nice insight in readable text. Im loving the little things like that. Keeps me going. Security and trust paths have led me down wonderful learning paths, the real world revenue path is something that I can wok on too.


---
_Source: https://the-faction.mn.co/posts/104635926_
