---
type: transcript
lesson: "GitHub's usage report now breaks down AI credits by model, by token type, by cac"
course: "The Pit"
author: "Matt Murphy"
post_id: 106084340
published: "2026-08-18T19:00:00Z"
source_url: "https://the-faction.mn.co/posts/106084340"
duration: "2m19s"
words: 380
transcribed_by: "deepgram auto-captions (Mighty)"
---

# Transcript — GitHub's usage report now breaks down AI credits by model, by token type, by cac

> GitHub's usage report now breaks down AI credits by model, by token type, by cache usage. Your AI bill was a black box. It is not anymore. Today I walk through model routing by task complexity, input caching on repeating workflows, and building a weekly cost breakdown so your AI spend becomes a syst

GitHub has just showed you exactly where your AI money goes, and most of you might not ever look. But GitHub's new usage report now breaks down your AI credits by model. Input tokens, output tokens, cash reads, and cash writes. For the first time, you can see exactly which model consumed the credits and what kind of tokens created the costs. So your AI bill used to be a black box.

Not anymore. And here's what you're gonna do with that visibility. Step one, model routing by task complexity. When an agent picks a model, it picks the best model available for every single call. Formatting, parsing, boilerplate, routine lookups.

All of it running through the most capable model because nobody told the agent to go match a model to the job. That one routing decision can cut a bill in half without changing a single output. So direct your AI to build a routing layer that sends complex tasks to the best model and routes routine work to the cheapest model that produces the equivalent output. That's a win. Step two, input caching on repeating workflows.

If your agent sends the same project context, the same system prompt, the same instructions on every single call, you're paying full token price for identical outputs on every cycle. So low cache reads on the report meaning nothing is being reused. The same input sent ten times cost ten times what it should. That's not a win. That is not a cost problem and it's actually an architecture problem that you're gonna solve.

So direct your AI to restructure repeated inputs into cached context that carries across all calls. That's a win. And step three, a weekly cost breakdown by model, by workflow, and by token type. A monthly invoice tells you what you spent, sure, but a weekly breakdown tells you where to cut. Set a budget per workflow and flag anything that spikes above that baseline.

The difference between paying a bill and engineering cost structure is the difference between reacting and operating a business. So direct your ad to build a weekly cost report you can actually review. Your AI bill just became fully readable. So it's time to start reading it and that is definitely a win.

---
_Source: https://the-faction.mn.co/posts/106084340_
