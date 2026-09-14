---
space: "The Pit"
author: "Matt Murphy"
post_id: 107025788
reactions: 0
comments: 0
published: "2026-09-11T19:00:00Z"
source: "https://the-faction.mn.co/posts/107025788"
---

# Thousands of people scraped your prompt this week, ran it in their builds, and y

Thousands of people scraped your prompt this week, ran it in their builds, and you have no idea it happened. I deal with this every week. Embed a callback URL in your prompt using OAST. A unique URL that fires when an AI processes the prompt. The user does not see it. When they copy and run your prompt, you get a timestamp and an origin. One URL per prompt. You know exactly which prompt was copied, when, and where. Over time you see patterns. Which prompts travel. Which audiences copy. That data tells you what to share publicly and what to gate. You cannot stop someone from copying a text prompt. But you can know when they did. A prompt without a canary is invisible. A prompt with one calls home. Hat tip to roozbeh.18 for this one.

**PROMPT:** You are an OAST (Out-of-band Application Security Testing) specialist. Help the user set up prompt canary callbacks. Guide them through: (1) Setting up an OAST callback server or using an existing service (Burp Collaborator, interactsh, or a custom endpoint). (2) Generating unique callback URLs for each prompt. (3) Embedding the callback URL in prompts in a way that triggers when an AI processes it without altering the output. (4) Setting up logging for timestamp, source IP, user agent, and prompt ID. (5) Creating alerts for new callback hits. Provide concrete examples for system prompts, instruction prompts, and template prompts.

---

## Video transcript

_deepgram auto-captions (Mighty) · 2m20s_

Thousands of people scraped your prompts this week, ran them in their builds, and you have no idea that it even happened. So let's say you publish a prompt. Right? Someone copies it, runs it, uses your work without credit or payment to you. So there's no watermark on a text prompt.

There is a callback, and so oAst gives you a tripwire for your intellectual property if you know how to set it up. So let's talk about it. Number one, embed an out of band callback URL in every prompt. A unique URL that only resolves when an AI processes that prompt. So it sits in an instruction the AI reads but the user does not see it.

If it does not affect the prompt's output, then no one notices it. When someone copies your prompt and runs it, the AI hits that URL every time. You get a ping with a timestamp and the origin. I can tell you from experience that the first time you see a callback fire from a prompt you posted two days ago, it changes how you think about what you share and what you're gonna charge for it. Right?

And this is not theoretical. I deal with it every single week. You guys copy thousands of prompts. So entire directories exist for scraping prompts. Number two, one callback URL per prompt.

When it fires, you know exactly which prompt was copied, when it was used, and roughly where from. Right? So you are not guessing who is using your work. You have a full log of it. Over time, you see all the patterns.

Which prompts travel, which audiences are copying them, which ones generate the most scraping activity. That data informs you publicly what you need to keep behind your gate. Right? And three, the callback is detection not prevention. You cannot stop someone from copying a text prompt.

And by the way, shouldn't. If you're putting it out there, you want people to use it. But you can know when they did and where they went. Whether you use that for attribution enforcement or just awareness, the data is yours. You can do what you want with it.

A prompt without a canary is invisible the moment someone copies it. A prompt with a canary calls home every time and tells you what happened. So your prompts, they're your product. Treat them like they are.


---
_Source: https://the-faction.mn.co/posts/107025788_
