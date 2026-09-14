---
space: "Welcome To The Faction"
author: "Gerald Besson"
post_id: 104823272
reactions: 1
comments: 5
published: "2026-07-20T20:15:35Z"
source: "https://the-faction.mn.co/posts/104823272"
---

# Everytime I start a session with Claude/VS, I have to define the role, context,

Everytime I start a session with Claude/VS, I have to define the role, context, and objective … I created /prompt that return a prompt preconfiguration. Does it make any sense or am I just pontificating?

---

## Discussion

**Matt Murphy** · 2026-07-21

> Gerald, I don't think you're pontificating at all, I think you've probably found a bug.
> 
> The /prompt command should be presenting the category picker, but it looks like it's getting stuck after reading the [README.md](http://README.md) and never advancing past the AskUserQuestion step.
> 
> Try closing the session and launching a brand new one first. If it still hangs there, I'd grab that screenshot and post it in the Claude Code GitHub issues because that doesn't look like expected behavior.
> 
> Curious if anyone else here is seeing the same thing with /prompt, or if it's isolated to this install.
> 
> If others can reproduce it, that's probably something Anthropic will want to fix.

**David Smith** · 2026-07-21

> I do something similar, but I have single skills/commands that run through a workflow for the type of task I'm working on. Features, bug fixes, large projects, research, etc.

**Gerald Besson** · 2026-07-21

> I tested and it works, the AskUserQuestion is part of the orientation flow and dispatch a subagent to adapt model and permissions and to frame the session. It feels heavy tho

  ↳ **Matt Murphy** · 2026-07-21

  > Gerald, that makes a lot more sense now. I see where I misunderstood what I was looking at.
  > 
  > Personally, I don't think it's heavy because of the AskUserQuestion step; I think it's heavy because you're asking the model to rebuild context at the beginning of every session.
  > 
  > That's actually one of the reasons I spend so much time talking about Institutional Brains. So the more your architecture, standards, conventions, and business context become persistent assets instead of session prompts, the less orchestration you have to do every time you sit down to work.
  > 
  > I think you're solving a real problem. I'd just keep asking yourself, "Can this move from runtime orchestration into permanent project memory?" Every time the answer is yes, your workflow gets a little simpler and a little more deterministic.

  ↳ **Gerald Besson** · 2026-07-22

  > I love the concept of persistent assets, it make so much sense


---
_Source: https://the-faction.mn.co/posts/104823272_
