---
space: "The Pit"
author: "Matt Murphy"
post_id: 106084340
reactions: 2
comments: 2
published: "2026-08-18T19:00:00Z"
source: "https://the-faction.mn.co/posts/106084340"
---

# GitHub's usage report now breaks down AI credits by model, by token type, by cac

GitHub's usage report now breaks down AI credits by model, by token type, by cache usage. Your AI bill was a black box. It is not anymore. Today I walk through model routing by task complexity, input caching on repeating workflows, and building a weekly cost breakdown so your AI spend becomes a system you engineer, not a surprise you react to.

**PROMPT:** Direct your AI: "Build an AI cost engineering system with three components: (1) Model routing audit. Review all AI API calls in my application. For each call, identify which model is being used and classify the task complexity as routine, moderate, or complex. Flag every routine task running on the most expensive model. Build a routing configuration that sends complex tasks to the best model and routes routine tasks to the cheapest model that produces equivalent output. Estimate monthly savings. (2) Input compression audit. Identify every system prompt, project context block, and instruction set that is sent on multiple API calls. Measure the token count of each repeated input. For each, determine whether it can be cached, compressed, or restructured into a reusable instruction that reduces token consumption. Calculate current waste from repeated inputs per month. (3) Weekly cost dashboard. Build a report template that tracks: total spend by model, spend by workflow or feature, token breakdown (input, output, cache read, cache write), week-over-week trend, and per-call average cost. Set threshold alerts for any workflow that exceeds its budget by 20%. Export as a reviewable document weekly."

---

## Video transcript

_deepgram auto-captions (Mighty) · 2m19s_

GitHub has just showed you exactly where your AI money goes, and most of you might not ever look. But GitHub's new usage report now breaks down your AI credits by model. Input tokens, output tokens, cash reads, and cash writes. For the first time, you can see exactly which model consumed the credits and what kind of tokens created the costs. So your AI bill used to be a black box.

Not anymore. And here's what you're gonna do with that visibility. Step one, model routing by task complexity. When an agent picks a model, it picks the best model available for every single call. Formatting, parsing, boilerplate, routine lookups.

All of it running through the most capable model because nobody told the agent to go match a model to the job. That one routing decision can cut a bill in half without changing a single output. So direct your AI to build a routing layer that sends complex tasks to the best model and routes routine work to the cheapest model that produces the equivalent output. That's a win. Step two, input caching on repeating workflows.

If your agent sends the same project context, the same system prompt, the same instructions on every single call, you're paying full token price for identical outputs on every cycle. So low cache reads on the report meaning nothing is being reused. The same input sent ten times cost ten times what it should. That's not a win. That is not a cost problem and it's actually an architecture problem that you're gonna solve.

So direct your AI to restructure repeated inputs into cached context that carries across all calls. That's a win. And step three, a weekly cost breakdown by model, by workflow, and by token type. A monthly invoice tells you what you spent, sure, but a weekly breakdown tells you where to cut. Set a budget per workflow and flag anything that spikes above that baseline.

The difference between paying a bill and engineering cost structure is the difference between reacting and operating a business. So direct your ad to build a weekly cost report you can actually review. Your AI bill just became fully readable. So it's time to start reading it and that is definitely a win.


---

## Discussion

**Lara S** · 2026-08-18

> So important. I had a similar thought process today and was creating hooks to track my usage per session and project … cos it’s useful to understand the true cost of building with AI … and oh my … I did not ever conceive the true cost before today.
> 
> What I’ve just done for less than a dollar today, could actually have cost over 500 at an API rate even with caching.
> 
> The prompt you suggest is way more important than ppl realise until they see the data

  ↳ **Matt Murphy** · 2026-08-18

  > I appreciate the validation and I am happy that you found it so useful.


---
_Source: https://the-faction.mn.co/posts/106084340_
