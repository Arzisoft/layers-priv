---
space: "The Pit"
author: "Matt Murphy"
post_id: 106719954
reactions: 2
comments: 0
published: "2026-09-01T14:00:07Z"
source: "https://the-faction.mn.co/posts/106719954"
---

# You are using the same AI to build and review your code and here is what each pl

You are using the same AI to build and review your code and here is what each platform actually catches that the others miss. Last week you all shared your workflows in the comments. Claude with Codex. Gemini with Claude. CodeRabbit alongside Cursor. Today I break down the factual strengths. Claude excels at adversarial reasoning and security review. Codex and Gemini are strong at catching implementation errors across code they did not write. Lovable, Bolt, and Cursor surface architecture differences when you hand them the same spec your first platform built from. This is not a comparison. This is knowing which tool to assign to which job. If you are running everything through one platform, this changes how you work.

**PROMPT:** Direct your AI: "Build a cross-platform code audit workflow with three components: (1) Security and adversarial review. Take my authentication module, my payment processing flow, and every endpoint that handles user input. Bring this code to a platform known for adversarial reasoning. Frame the prompt as a penetration test: attempt to find injection points, authentication bypasses, privilege escalation paths, data exposure risks, and rate limiting gaps. Do not frame it as a code review. Frame it as an attack. Document every finding with severity, exploit scenario, and recommended fix. (2) Logic verification on a second platform. Take my three most complex business logic modules. Bring them to a platform that did not generate the code. Instruct it to walk through every conditional branch, identify every edge case, trace every error state, and verify that every state transition leaves data in a consistent condition. Document any branch where behavior is undefined and any input that produces an unexpected result. (3) Architecture comparison build. Take the requirements spec for one critical module. Rebuild it on a different platform without showing it the original implementation. Compare the two implementations line by line. Document every difference in approach: data model, error handling, API structure, validation logic. Where the implementations differ is where your assumptions were made silently. Evaluate which approach is stronger for each difference and incorporate the better pattern into your production build.

---

## Video transcript

_deepgram auto-captions (Mighty) · 2m31s_

This is for you if you're using the same AI to build and review your code. This is a follow-up to last week's cross platform testing reel because every single platform has a training bias and every model out there defaults to a pattern and has a blind spot it cannot see in its own output. So the builders that are getting the best results know exactly which platform to match to which job. Here is what each platform actually catches that the others will miss. Number one is Claude.

It excels at adversarial reasoning, security reviews and deep architectural analysis. So when you need to break your own system, Claude is the one. It thinks like an attacker. It finds injection pass, authentication bypasses, and logic flaws like a pro. That and the AI building platform will always defend itself.

So Claude is the one to stick on it. If you built in cursor, lovable, or Bolt, I'd bring your security review to Claude and frame it as a penetration test. So direct your AI to run security critical reviews on a platform with demonstrated adversarial depth. I think someone on here actually named their adversarial audit the Murphy. That's a win.

Step two is Codecs and Gemini are strongest at catching implementation errors and reviewing code they did not write. So Codex reads your codebase cold and flags what does not belong. Gemini brings a giant context window that lets you hold your entire project in one view. And it'll spot patterns across files that a single file reviewer will miss. So if you built in Claude code, I'd take your logic verification to Codex or Gemini for a second opinion with no attachment to the original implementation.

So DirectoryAI to run a full code based review on a platform that did not generate the code. And number three, lovable Bolt and Cursor. They are super strong at full stack builds and rapid prototyping. So if you built your back end in Claude code, I'd hand the same requirements to Lovable or Bolt and compare how a different platform interprets the same specs. Where the implementations differ is where your assumptions live and where the opportunity lives.

So those differences always surface architecture decisions in your first platform made silently for you. So DirectoryAI to rebuild one critical module on a second platform and document every different approach it took. Same build, different eyes, better product every single time.


---
_Source: https://the-faction.mn.co/posts/106719954_
