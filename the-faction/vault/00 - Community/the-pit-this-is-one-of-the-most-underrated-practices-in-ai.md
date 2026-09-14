---
space: "The Pit"
author: "Matt Murphy"
post_id: 106569156
reactions: 3
comments: 3
published: "2026-08-29T19:00:00Z"
source: "https://the-faction.mn.co/posts/106569156"
---

# This is one of the most underrated practices in AI-directed engineering. You bui

This is one of the most underrated practices in AI-directed engineering. You built your entire app on one platform. You ask that same platform to review its own work. It says it looks good. Of course it does. Today I walk through using a second AI platform to catch what the first one misses, structuring cross-platform reviews as adversarial red team exercises, and rotating which platform leads each build cycle so blind spots do not accumulate across your entire codebase. If you are building everything on one AI, this changes your quality overnight.

**PROMPT:** Direct your AI: "Set up a cross-platform AI audit process for my application with three components: (1) Cross-platform code review. Export my authentication module, my data access layer, and my API endpoint handlers. Prepare a structured review prompt for a second AI platform that instructs it to identify security vulnerabilities, logic errors, unhandled edge cases, and any pattern where user input could bypass validation or access controls. Format the output as a prioritized findings list with severity, location, and recommended fix for each issue. After receiving the second platform's review, reconcile the findings against this platform's assessment and flag every disagreement for manual review. (2) Adversarial review framework. Create a reusable review prompt template that frames every code review as a red team exercise. The template should instruct the reviewing AI to attempt to break the code by identifying authentication bypass routes, data exposure risks, injection vulnerabilities, race conditions, and missing authorization checks. The prompt should explicitly instruct the reviewer to assume hostile intent and find exploitable weaknesses, not confirm correctness. (3) Platform rotation schedule. Design a build-and-review rotation for my development workflow where critical features are built using one AI platform and reviewed by a different AI platform before deployment. Define which feature categories require cross-platform review, the handoff format between platforms, and a tracking system that logs which platform built and which reviewed each module."

---

## Video transcript

_deepgram auto-captions (Mighty) · 2m25s_

You use the same AI assistant to build your entire app. So you're using the same AI to check its own work. I'll tell you what, it's never gonna tell on itself or find its own mistakes. You asked your AI to build authentication. Then you asked it to review authentication.

It said it looks great. Right? Of course it did. It wrote it. The same blind spots that created the vulnerabilities are the same blind spots that missed review.

Every platform has very specific patterns. It defaults to shortcuts it prefers and edge cases it consistently overlooks. So here's how we're going to optimize it for your audits. Step one, a second platform catches what the first one cannot see. Every AI has a different training set, different default patterns, and different failure modes.

So the code one platform writes confidently, another platform flags immediately. Direct your AI to export your critical modules and run them through a second AI platform. That, it has to have instructions to identify security gaps, logic errors, and missing edge cases. The places where the two platforms disagree are exactly where your real problems are hiding in production. Go find them.

Step two, structure the audit as an adversarial review. Right? Do not ask the platform if the code looks good. Tell it to break it. Tell it to find every way a user could bypass authentication, access data they should not see, or cause the system to fail.

A cooperative review always confirms what works. Right? But an adversarial review finds what does not work. So direct your AI to frame every cross platform review as a red team exercise. This way, where the reviewing platform is trying to break the code and not validate it, that's a win.

And step three, rotate which platform leads each build cycle. If the same AI builds every feature for you, you accumulate the same blind spots across your entire code base. So alternate which platform writes and which platform reviews. Direct your AI to establish a rotation where critical features are built on one platform and reviewed on another before deployment. That's a win.

One AI builds it, different AI looks at it and breaks it. That's how you find what neither one would catch alone or tell on itself. It is what it is.


---

## Discussion

**Peter Lee** · 2026-08-30

> I have built my B2C platform using Claude Code Fable and Opus Class, Fable for the Architect and blind verifier, Opus to build it. My concern/worry is, if I give the deliverables to ChatGPT or Gemini which are considered to be inferior LLMs, wouldn't this be a little like handing a Senior Developers work to a Junior Developer to perform a quality check. I will open up the tin and let ChatGPT in if you think there is value in doing this as an exercise. Please let me know your thoughts.

  ↳ **Matt Murphy** · 2026-08-31

  > Peter, I think the Senior Developer → Junior Developer analogy is the part I’d challenge.
  > 
  > Models don’t really form a clean engineering org chart where one is universally “senior” and another is universally “junior.” They have different training, reasoning patterns, tool use, context handling, and blind spots. A model that is weaker at implementing your architecture can still catch something the builder missed precisely because it approaches the problem differently.
  > 
  > That said, for anything security-, auth-, data-, or money-related, I’d absolutely use the strongest independent reviewer you have available. The point is to avoid asking the same brain that built the thing to grade its own homework. 😂
  > 
  > So your experiment with ChatGPT is worthwhile. Give it the deliverable cold, provide the requirements and threat model, and explicitly tell it not to confirm correctness but to try to break the design. Then take its findings back to Claude/Opus and force the two assessments to reconcile disagreements.
  > 
  > And I wouldn’t stop with AI-on-AI review. Tests, static analysis, dependency scanning, actual security tooling, and eventually human review are still part of the evidence chain. Cross-model review gives you another adversarial lens; it does not magically turn either model into proof.
  > 
  > That distinction is the whole point of the exercise: independence matters almost as much as raw model capability. Run the tin-can test and bring the results back, I’d genuinely like to see what the second system catches. 👊😎

  ↳ **Peter Lee** · 2026-09-01

  > You make a great salesman
  > 
  > SOLD! 🙂
  > 
  > time to purchase ANOTHER AI subscription I guess... Thank you for the sound advice


---
_Source: https://the-faction.mn.co/posts/106569156_
