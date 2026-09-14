---
space: "The Pit"
author: "Matt Murphy"
post_id: 104111508
reactions: 0
comments: 0
published: "2026-07-05T20:30:01Z"
source: "https://the-faction.mn.co/posts/104111508"
---

# A $20 self-hosted runner runs unlimited minutes.

A $20 self-hosted runner runs unlimited minutes.

The same pipeligithubactions [#cicd](https://the-faction.mn.co/spaces/23777071/search?term=%23cicd) [#selfhosted](https://the-faction.mn.co/spaces/23777071/search?term=%23selfhosted) [#devops](https://the-faction.mn.co/spaces/23777071/search?term=%23devops) triggers.

Usage alerts at 75%. CI that scales does not surprise you on day 19.

-MM

[#githubactions](https://the-faction.mn.co/spaces/23777071/search?term=%23githubactions) [#cicd](https://the-faction.mn.co/spaces/23777071/search?term=%23cicd) [#selfhosted](https://the-faction.mn.co/spaces/23777071/search?term=%23selfhosted) [#devops](https://the-faction.mn.co/spaces/23777071/search?term=%23devops) [#production](https://the-faction.mn.co/spaces/23777071/search?term=%23production)

---

## Video transcript

_deepgram auto-captions (Mighty) · 1m31s_

Your CICD pipeline just exceeded the free tier mid sprint. Here are three things you're going to change right now to fix it. Step one, self hosted runners. GitHub actions let you bring your own compute. It's a twenty dollars per month server and it runs unlimited minutes.

So that same pipeline that costs twelve hundred dollars in overrun charges now runs for twenty dollars on your own machine. Yeah, you manage the server and you manage the runner software and you manage the updates. But for teams that are burning through CI minutes, the math takes five seconds to figure out. It's a win. Step two, conditional pipelines.

Not every commit needs every single test. A change to your readme does not need integration tests. A change to your marketing page does not need your backend build. Path based triggers run only the stages that match the changed files. Fewer stages, fewer minutes, same safety.

Most teams run the full suite on every push. That's not thorough, that's wasteful. Step three, monitor your usage before it surprises you. GitHub shows you your minute consumption in settings. Check it weekly.

Set a team alert at seventy five percent of your monthly allocation. When the alert fires, you have time to optimize and fix. When the pipeline stops, you have no time for anything. So the CI that scales is not the one with the most features, it's the one that does not surprise you on day nineteen in the middle of that sprint.


---
_Source: https://the-faction.mn.co/posts/104111508_
