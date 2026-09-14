---
space: "The Mentoring Lounge"
author: "Osman Medina"
post_id: 106199572
reactions: 1
comments: 1
published: "2026-08-19T20:32:33Z"
source: "https://the-faction.mn.co/posts/106199572"
---

# Shipping a solo-built app soon. Where does AI-assisted QA actually fail?

**Shipping a solo-built app soon. Where does AI-assisted QA actually fail?**

I'm about to close beta on a desktop app I've built solo, with AI doing most of the code and most of the review. Before I release, I want to pressure-test my process rather than just my code, and I'd value input from people who have shipped this way.

**What it is:** a project and business management app for Mac with an iPhone companion. Tasks, Gantt, calendar, costing and estimating, invoicing, a small CRM, and an AI assistant that can drive the app through about 380 tools. Swift and SwiftUI, SQLite via GRDB, CloudKit for multi-device sync. Roughly 3,200 automated tests.

**How I work now:** every non-trivial change goes through two agents. One builds to a written brief and stops without committing. A second audits it independently, deriving what the code *should* do from the plan and the design before it reads what the builder claims it did, then reruns every gate itself. It catches a lot. Genuinely a lot.

**Where I think it's blind, and my actual question.**

Yesterday I found a class of bug that had shipped past all of it. Date handling assumed every day is 24 hours. On the two days a year the clocks change, a day is 23 or 25 hours, so a query for "today" reached into tomorrow. Ticking off a repeating task on that day deleted the *next* day's record, and then synced that deletion to the user's other devices.

Three thousand green tests. Multiple clean audits. Nobody saw it, because the tests were written by the same reasoning that wrote the bug, and they agreed with each other.

Worse, when I did write a test for it, my first version passed while the bug was still live. It asserted the task landed on the right *day*, and the broken code landed on the right day at 1am. The test looked correct and proved nothing.

So my questions for anyone who has been here:

1) What do you use to catch defects that your AI and your tests are jointly wrong about? Property-based testing, mutation testing, fuzzing, adversarial review by a different model, something else?

2) How do you validate the things automation can't reach at all? Multi-device sync, real money calculations, anything requiring two machines and two accounts.

3) For those who ship solo: how much of your pre-release checklist is deliberately manual, and what's on it?

4) Is there anything you consider genuinely non-negotiable before a paid 1.0 that I'd only learn by getting it wrong?

5) The app has a basic and Pro features options via toggle buttons, how would you link the conversion from one to another inside the app if the user purchase any of those two options?

For context, I'm starting with the Apple Store first. In the future I'll look to expand to other systems as gaining more experience.

Happy to go into detail on any of it. I'd rather find the gap now than after someone's data is on the line.

---

## Discussion

**Matt Murphy** · 2026-08-19

> Osman, this is a great question, one we have seen before, and the daylight-saving bug is actually the perfect example of where AI-assisted QA can fool you.
> 
> Three thousand green tests do not prove correctness if the implementation and the tests inherited the same bad assumption. You had two systems agreeing that “a day = 24 hours,” when the real-world domain was telling both of them they were wrong.
> 
> Here’s how I’d approach your five questions:
> 
> 1. How do you catch defects where the code and tests share the same assumption?
> 
> I’d use multiple forms of disagreement.
> 
> Property-based testing is excellent for things like dates, money, synchronization and recurrence because you specify invariants rather than examples: “completing today’s repeating task can never delete tomorrow’s instance,” regardless of timezone, DST transition, locale or date.
> 
> Mutation testing answers a different question: *would my test suite notice if the implementation were subtly wrong?* If I change <= to <, invert a condition, remove a guard or alter a date calculation and everything stays green, I’ve learned something important about the tests.
> 
> Fuzzing is valuable around parsers, imports, malformed data, tool arguments and anything with a huge input space. And I absolutely like adversarial review by a second model, but give it the **s**pecification and observed behavior firs**t**, not the first agent’s reasoning. Otherwise you risk two models inheriting the same story. That's not a win.
> 
> The principle is: create independent ways for the system to disagree with itself.
> 
> 2. What about things automation genuinely cannot reach?
> 
> I don’t pretend those are automated.
> 
> Maintain a physical-device matrix and manually test the critical cross-boundary journeys: two devices, two accounts, CloudKit synchronization, offline → online transitions, clock changes, account changes, interrupted purchases, real notification timing, migration from an older build, and anything involving actual money.
> 
> For your application I’d especially test:
> 
> Mac creates →
> 
> iPhone edits →
> 
> Mac resolves
> offline edits on both devices →
> 
> reconnect
> DST transition
> timezone change while records are pending
> account sign-out/sign-in
> sync conflict on invoice/task/customer
> purchase →
> 
> entitlement →
> 
> second device
> refund/cancel/upgrade/downgrade →
> 
> entitlement change
> 
> Those are system tests, not unit tests.
> 
> 3. How much of a solo pre-release checklist should stay manual?
> 
> I’d deliberately keep the highest-consequence user journeys manual.
> 
> Not because humans are inherently better testers, but because you want one final observer who is not executing the same assumptions as the machinery that built the product.
> 
> My manual release pass would include fresh install, upgrade from previous version, first-run onboarding, auth/account flows, destructive operations, import/export, backup/restore, synchronization, billing, entitlement changes, permissions, offline recovery, and the top five customer journeys.
> 
> Automation gives you breadth and repetition. Manual testing gives you a different point of view.
> 
> 4. My non-negotiables before a paid 1.0?
> 
> No known data-loss bug.
> 
> Verified backup and restore.
> 
> Destructive actions either reversible or extremely deliberate.
> 
> Idempotency around payments and important writes.
> 
> Migration testing from every supported previous database version.
> 
> Logs good enough to reconstruct a failure.
> 
> Crash/error reporting.
> 
> Rate limits and sane failure behavior around the AI assistant and its 380 tools.
> 
> A kill switch for anything capable of changing customer data.
> 
> And test the ugly conditions: no network, slow network, full disk, clock changes, duplicate requests, process killed halfway through a write, CloudKit delay, API unavailable.
> 
> I would rather ship without three features than ship with one path capable of silently corrupting customer data.
> 
> 5. Basic → Pro inside the Apple app
> 
> Don’t let the toggle itself grant anything.
> 
> The UI initiates the StoreKit purchase. A verified StoreKit transaction becomes the entitlement, and your application derives its feature state from that entitlement. StoreKit 2 exposes current entitlements specifically so the app can determine which purchases or subscriptions currently grant access.
> 
> Conceptually:
> 
> User chooses Pro →
> 
> StoreKit purchase →
> 
> verified transaction →
> 
> entitlement state becomes Pro →
> 
> feature gates react to entitlement
> 
> If Basic and Pro are recurring subscription levels, Apple supports multiple service levels in a subscription group so customers can upgrade or downgrade between them.
> 
> And test the hell out of that flow with StoreKit’s Xcode testing before App Store release; Apple specifically provides StoreKit testing support for purchases and subscriptions.
> 
> The larger lesson from the DST bug is the one I’d keep.
> 
> Don’t measure QA by test count. Measure how many independent assumptions you’ve challenged.
> 
> 3,200 tests generated from one worldview can still have one enormous blind spot. Ten deliberately adversarial tests built around the physics of the real world can sometimes teach you more.
> 
> And the fact that you found this *before* 1.0 means the process is doing what it’s supposed to do: every escape becomes another permanent guardrail. That’s exactly how production engineering muscle gets built. Feed this reply to your AI assistant and allow it to begin to assist in your testing efforts. 👊😎


---
_Source: https://the-faction.mn.co/posts/106199572_
