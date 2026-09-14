---
space: "The Pit"
author: "Matt Murphy"
post_id: 106665821
reactions: 1
comments: 0
published: "2026-08-31T14:00:04Z"
source: "https://the-faction.mn.co/posts/106665821"
---

# You have 47 skills loaded into your AI right now and half of them were written f

You have 47 skills loaded into your AI right now and half of them were written for a model that no longer exists. That skill from four months ago references syntax, capabilities, and workarounds that have already changed. Every stale skill sitting in your context window is competing with the instruction you are giving it right now. Today I walk through auditing every skill against the current model version, treating skills as prescriptions you apply and dispose of instead of assets you hoard, and benchmarking the performance difference between a full context load and a scoped one. If you have been saving skills for months, this one is going to change how you think about them.

**PROMPT:** Direct your AI: "Build a skill hygiene and lifecycle system with three components: (1) Skill audit against current model version. Inventory every skill, custom instruction, and system prompt currently loaded in my development environment. For each, identify the date it was created or last modified, the model version it was written for, and whether it references deprecated syntax, outdated capabilities, removed guardrails, or workarounds that no longer apply. Flag every skill that has not been updated in 90 days or references a model version more than two releases behind. Recommend remove, update, or keep for each. (2) Disposable skill lifecycle. Design a workflow where skills are scoped to a specific build task: loaded when the task begins, verified when the fix is applied, and removed from the context when the task is complete. No skill persists in the active context beyond its task scope. Implement tagging that tracks which skills are active, which are pending verification, and which are queued for disposal. (3) Performance benchmarking. Run a controlled comparison: execute the same build task with the full skill library loaded versus only the task-relevant skills loaded. Measure response quality, response time, accuracy of output, and token consumption. Report the delta. Repeat across three different task types to establish a baseline for optimal context load."

---

## Video transcript

_deepgram auto-captions (Mighty) · 2m03s_

You have forty seven stale skills loaded in your AI assistant right now, and more than half of them were written for a model that no longer exists. I'm referring to a skill that you saved four months ago. It was written for a model that has been updated dozens of times since then. So the syntax it references has all changed. And the capabilities it accounts for just totally outdated.

Not to mention the guardrails it works around have been removed or even replaced. So your AI is not leveraging the model it's running on today. It's anchored to where the model was when you wrote that school skill four months ago. So that's no longer optimization. That's a drag.

And here's how we're going to address it. Step one, audit every skill in your system against the current model version. If the skill references capabilities, syntax, or workarounds that no longer apply, it's dead weight, it's time to remove it. So direct your AI to inventory every loaded skill and flag any that reference, be it deprecated patterns or outdated model behaviors. That that's a win.

Step two, treat skills as prescriptions, not assets. A skill should solve one problem in one moment for your build and move on. So you apply it, verify the fix, completely dispose of it. So direct your AI to implement a skill lifecycle that loads only what your current build needs right then, and removes it after that fix is verified. And step three, measure the performance differences.

Sure. Run your build with every skill loaded. Then run it only with the skills that apply to your current task. Direct your AI to benchmark it, response quality, speed, and accuracy, and run it between a full context load and a scoped context load. It's gonna blow you away.

So your AI gets smarter every month, but your skills don't. So stop anchoring your best tool to your oldest instructions and let it rock.


---
_Source: https://the-faction.mn.co/posts/106665821_
