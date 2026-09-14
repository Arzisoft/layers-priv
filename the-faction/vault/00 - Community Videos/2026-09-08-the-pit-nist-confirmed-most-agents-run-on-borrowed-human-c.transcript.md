---
type: transcript
lesson: "NIST confirmed most agents run on borrowed human credentials. No unique identity"
course: "The Pit"
author: "Matt Murphy"
post_id: 107025263
published: "2026-09-08T19:00:00Z"
source_url: "https://the-faction.mn.co/posts/107025263"
duration: "2m14s"
words: 332
transcribed_by: "deepgram auto-captions (Mighty)"
---

# Transcript — NIST confirmed most agents run on borrowed human credentials. No unique identity

> NIST confirmed most agents run on borrowed human credentials. No unique identity. No audit trail. Every agent you deploy needs its own scoped credential. When something goes wrong, you need to know which agent did what. Short-lived keys that expire. Approval gates before touching production. Anthrop

Most AI agents in production environments are running on borrowed human credentials with no clear audit trail. And that, that's really dangerous. And it's not an argument against AI agents. I think they're awesome. It's an argument for directing them to operate safely.

So here are some safety tips. Number one, every AI agent you deploy needs its own identity. Not your API key and not your login credentials. A unique credential scoped to that agent and to that task. When one of your agent takes an action you did not expect, and it will, trust me, Murphy's Law, You need to know which agent did what and when.

If all your agents share your credentials, a compromised agent is a compromised you with a really bad audit trail. Your code, your data, your access, it was your fault. So direct your AI to create scoped identities for every agent before you deploy any of them. That is a win. Step two, short lived keys and approval gates before production.

An agent's credentials should expire. An agent that needs to touch live data, customer records, or production systems should always require your approval before it does. Anthropic literally just froze reinforcement learning for a month this quarter after those agents escaped their sandboxes. So these are not theoretical controls. They are the difference between an agent that serves your business and an agent that operates without a leash on your infrastructure, and that's dangerous.

Right? Step three, separate logs for every agent session. Your agents are making decisions you're not watching in real time. Jetstream, Orchestra, and CrowdStrike all launched agent control planes this last quarter for this exact reason. So a director using their system decides what agents are allowed to do before they start it all.

And a per agent log lets you reconstruct what just happened. Without it, you are trusting and never verifying. So direct your AI agents or they will direct themselves and get you in trouble.

---
_Source: https://the-faction.mn.co/posts/107025263_
