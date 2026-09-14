---
type: transcript
lesson: "Your AI generated a complete feature in twenty minutes."
course: "The Pit"
author: "Matt Murphy"
post_id: 104635763
published: "2026-07-16T13:00:01Z"
source_url: "https://the-faction.mn.co/posts/104635763"
duration: "1m36s"
words: 240
transcribed_by: "deepgram auto-captions (Mighty)"
---

# Transcript — Your AI generated a complete feature in twenty minutes.

> Your AI generated a complete feature in twenty minutes.

Your AI generated a complete feature in twenty two minutes. Login flow, dashboard, payment processing, all functional. It's gorgeous. But nobody tested any of it. Here are the three things you're going to direct your AI to do right now to fix it.

Step one, write tests alongside the feature, not after the fact. You direct your AI to generate tests for every feature it builds as you're building those features. Same conversation. Build the login flow, write the test that verify it. Login, logout, wrong password, and account lockout.

If you do not ask AI for tests, you do not get tests. Your AI does not know that they are missing. Step two, set a coverage threshold. Direct your AI to run the test suite on every commit. If coverage drops below sixty percent, the commit is failed.

Sixty percent is the floor where you catch the failures that matter before your customers catch them. And for step three, separate unit from integration. Unit tests verify individual functions. They run-in seconds on every push. Integration tests verify the full user path, so they run on merges.

Direct your AI to split them up. Running everything on every push is slow and inefficient. Running nothing though, totally reckless. So your AI ships untested code all day long. It does not know the code is untested because you never asked for it.

The quality gate is solely yours, not your AI's.

---
_Source: https://the-faction.mn.co/posts/104635763_
