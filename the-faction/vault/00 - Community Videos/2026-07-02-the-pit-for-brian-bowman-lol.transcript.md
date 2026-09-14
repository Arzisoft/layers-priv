---
type: transcript
lesson: "For Brian Bowman LOL!"
course: "The Pit"
author: "Matt Murphy"
post_id: 104072102
published: "2026-07-02T23:08:52Z"
source_url: "https://the-faction.mn.co/posts/104072102"
duration: "1m21s"
words: 218
transcribed_by: "deepgram auto-captions (Mighty)"
---

# Transcript — For Brian Bowman LOL!

> For [Brian Bowman](https://the-faction.mn.co/members/40287351) LOL!

If you haven't heard, GitHub Copilot just had a remote code execution vulnerability. CVSS score nine point six out of ten. That's critical folks. So here's what happened. Someone put a hidden prompt injection in a PRD.

Not in the code, in the description of the code. Copilot read the description as context. The injection triggered code execution on the developer's machine without them even knowing it. Remote code execution from a normal pull request through an AI coding assistant. Let that sink in, VibeCoders.

That's a death spiral. The tool you trust the most to help you write code just became the attack vector. Not the code it generated, the AI itself. This has been patched, but the pattern has not. We're going to see a lot more of it.

Every AI tool that reads context from external sources is a potential injection surface. Your AI assistant reads your repo, your comments, your issues, your PRs. If any of those inputs can be poisoned, your AI can be weaponized against your app. This is why we teach security as the entire layer in the AI directed engineering stack. Because the threat model has changed and it will keep changing.

And most builders do not know it yet, especially Vibe coders using AI assistance this exact same way.

---
_Source: https://the-faction.mn.co/posts/104072102_
