---
type: transcript
lesson: "Your deployment takes forty-five minutes. Your team deploys once a week because"
course: "The Pit"
author: "Matt Murphy"
post_id: 103660845
published: "2026-06-24T00:35:52Z"
source_url: "https://the-faction.mn.co/posts/103660845"
duration: "1m29s"
words: 235
transcribed_by: "deepgram auto-captions (Mighty)"
---

# Transcript — Your deployment takes forty-five minutes. Your team deploys once a week because

> Your deployment takes forty-five minutes. Your team deploys once a week because of it.

Your deployment takes forty five minutes. And your team, they only deploy once a week because it takes so long. So bugs, they sit in staging for days and features, they're always waiting in line. Here are the three things you can do right now to fix it. Step one, your pipeline is doing way too much.

Every deployment runs every test, every lint check, every integration suite. The whole thing is running sequentially. So one step finishes before the next one can start. What I would do, brake deploys into parallel lanes whenever you can. Split unit tests from integration tests, run linting alongside both.

A forty five minute pipeline is usually a five minute pipeline running nine steps in a row. Step two, your builds are not cached. Every deployment installs every dependency from scratch. The node modules folder downloads fresh every single time. Caching dependencies between builds cuts minutes immediately.

Your dependencies did not change since yesterday, so stop rebuilding them from scratch every time. That's a win. Step three. Your deployment is all or nothing. One artifact, one environment, one prayer.

Canary deployments release to a small percentage of traffic first. It's a best practice. So if something breaks, five percent of users notice instead of one hundred percent of your users. So always deploy small, deploy often, deploy with a rollback plan. Speed is not recklessness, but slowness sure is.

---
_Source: https://the-faction.mn.co/posts/103660845_
