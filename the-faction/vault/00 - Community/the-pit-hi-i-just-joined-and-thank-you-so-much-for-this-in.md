---
space: "The Pit"
author: "Tracey B"
post_id: 107146239
reactions: 1
comments: 3
published: "2026-09-10T04:25:58Z"
source: "https://the-faction.mn.co/posts/107146239"
---

# Hi, I just joined and thank you so much for this incredible learning tool. I was

Hi, I just joined and thank you so much for this incredible learning tool. I was looking for something like this. (a one stop shop)

My Issue: I'm in Layer 1 (foundation) and I failed 'Organization'. Claude doesn't want to touch it right now because I started my build already.

Here's Claude's response: '**1. Organization — FAIL.** Everything lives in one 1,400-line file, App.jsx. No components split into their own files. Worth knowing this is a deliberate choice you made early on, not an accident — I wouldn't rank fixing this urgently; splitting files adds real complexity for a solo builder without a proportional payoff right now. If you split files now, you'd likely be splitting things apart today only to reshuffle them again once that navigation change lands. Better to let the app's shape settle first.

There's also a subtler point specific to how you're building this: file separation mostly exists to help *multiple humans* avoid stepping on each other's work, and to help one human hold a mental map of a large codebase in their head. You're one person working through Claude Code, which can read a 1,400-line file in full and hold the whole thing in view at once — some of the traditional reasons to split files young apply less here than they would on a team.'

I explained that I have to clear this before moving forward in the curriculum but Claude still HIGHLY recommends I wait because I'm still building. My Question: How risky would it be to move past this if I move to continue to build and come back to this later? P.S. Claude is saying I chose this (what a smarty pants) but I'm new at this so I didn't know what I was getting myself into. But it's my build so I'll take that one on the chin. :)

Matt, you are a Vibe Coder's godsend, if this is too long for you to address, I understand. Your course still rocks! Also, is 'The Pit' just for technically/system questions?

---

## Discussion

**Matt Murphy** · 2026-09-10

> Tracey, first off, welcome to the Faction, and this is exactly the kind of question The Pit is for. Builds, blockers, weird AI arguments, “why the hell did it do that?” moments… are all fair game in here. 😂
> 
> On the 1,400-line file: I would not skip it just because Claude is telling you it’s fine. Claude is giving you a reasonable short-term productivity argument, but the curriculum is trying to teach you a longer-term engineering habit. That is just my take.
> 
> A large file is not automatically bad because of the line count. The real question is whether that file contains multiple responsibilities that should have clear boundaries. UI, state, business logic, API calls, data access, auth, utilities, etc. If all of that is living together, then yes, the FAIL is likely telling you something useful.
> 
> And file separation absolutely is not just for multiple humans. Good boundaries make the application easier to test, debug, change, secure, and reason about, not to mention easing the ongoing support issues because you can give it a smaller blast radius instead of letting it rewrite the mothership every time you ask for a button change. 😎
> 
> I also wouldn’t tell Claude, “rewrite this whole thing into the perfect architecture.” That’s how we turn one problem into twelve. Instead, create a branch, make sure you have a clean backup and working tests, then extract one responsibility at a time. Move a component or service, verify behavior, commit it, then take the next piece. You’re refactoring, not rebuilding.
> 
> If the navigation change you mentioned is truly about to redefine the structure, account for that in the plan, but I still wouldn’t keep piling features into the 1,400-line file indefinitely. There’s a difference between postponing a refactor for a known dependency and allowing technical debt to become permanent because the AI prefers the easier path.
> 
> And don’t take the “you chose this” comment on the chin too hard. We've all been there. You’re new. You didn’t “choose an architecture”; you built until you knew enough to recognize one. That is literally what learning looks like.
> 
> I’d clear the layer incrementally and keep moving. You’re doing exactly what I hoped people would do with the Foundations: take an existing build, let the framework expose the weak spots, fix them while they’re still manageable, and come out the other side understanding *why* the architecture matters. 👊😎

**Tracey B** · 2026-09-11

> ~Sigh~ Thanks you sooo much for this, Matt!

  ↳ **Matt Murphy** · 2026-09-11

  > No problem, glad to have you here!


---
_Source: https://the-faction.mn.co/posts/107146239_
