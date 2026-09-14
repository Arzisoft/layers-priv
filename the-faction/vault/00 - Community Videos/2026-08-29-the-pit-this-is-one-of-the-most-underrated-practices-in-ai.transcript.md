---
type: transcript
lesson: "This is one of the most underrated practices in AI-directed engineering. You bui"
course: "The Pit"
author: "Matt Murphy"
post_id: 106569156
published: "2026-08-29T19:00:00Z"
source_url: "https://the-faction.mn.co/posts/106569156"
duration: "2m25s"
words: 391
transcribed_by: "deepgram auto-captions (Mighty)"
---

# Transcript — This is one of the most underrated practices in AI-directed engineering. You bui

> This is one of the most underrated practices in AI-directed engineering. You built your entire app on one platform. You ask that same platform to review its own work. It says it looks good. Of course it does. Today I walk through using a second AI platform to catch what the first one misses, structu

You use the same AI assistant to build your entire app. So you're using the same AI to check its own work. I'll tell you what, it's never gonna tell on itself or find its own mistakes. You asked your AI to build authentication. Then you asked it to review authentication.

It said it looks great. Right? Of course it did. It wrote it. The same blind spots that created the vulnerabilities are the same blind spots that missed review.

Every platform has very specific patterns. It defaults to shortcuts it prefers and edge cases it consistently overlooks. So here's how we're going to optimize it for your audits. Step one, a second platform catches what the first one cannot see. Every AI has a different training set, different default patterns, and different failure modes.

So the code one platform writes confidently, another platform flags immediately. Direct your AI to export your critical modules and run them through a second AI platform. That, it has to have instructions to identify security gaps, logic errors, and missing edge cases. The places where the two platforms disagree are exactly where your real problems are hiding in production. Go find them.

Step two, structure the audit as an adversarial review. Right? Do not ask the platform if the code looks good. Tell it to break it. Tell it to find every way a user could bypass authentication, access data they should not see, or cause the system to fail.

A cooperative review always confirms what works. Right? But an adversarial review finds what does not work. So direct your AI to frame every cross platform review as a red team exercise. This way, where the reviewing platform is trying to break the code and not validate it, that's a win.

And step three, rotate which platform leads each build cycle. If the same AI builds every feature for you, you accumulate the same blind spots across your entire code base. So alternate which platform writes and which platform reviews. Direct your AI to establish a rotation where critical features are built on one platform and reviewed on another before deployment. That's a win.

One AI builds it, different AI looks at it and breaks it. That's how you find what neither one would catch alone or tell on itself. It is what it is.

---
_Source: https://the-faction.mn.co/posts/106569156_
