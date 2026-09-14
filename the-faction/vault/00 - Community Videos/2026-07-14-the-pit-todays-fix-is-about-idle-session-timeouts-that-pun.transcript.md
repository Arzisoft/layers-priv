---
type: transcript
lesson: "Today's fix is about idle session timeouts that punish active users."
course: "The Pit"
author: "Matt Murphy"
post_id: 104567194
published: "2026-07-14T15:08:31Z"
source_url: "https://the-faction.mn.co/posts/104567194"
duration: "1m39s"
words: 252
transcribed_by: "deepgram auto-captions (Mighty)"
---

# Transcript — Today's fix is about idle session timeouts that punish active users.

> Today's fix is about idle session timeouts that punish active users.

Your security settings are kicking users out every fifteen minutes, even when they're actively working. So your definition of idle might be broken. Here are the three things you're going to direct your AI to fix right now. Step one, define meaningful activity. Mouse movement, not an activity.

A tab open in the background, also not an activity. Direct your AI to track actions that prove the user is still working. Form submissions, button clicks, API calls, page navigation. If the user is reading a long document without clicking, that also is not idle. So build an exception for sustained focus.

That's a win. Step two, warn them before you kill them. Direct your AI to show a modal sixty seconds before the session expires. Your session expires in sixty seconds, click to stay logged in. The user who stepped away for coffee sees it when they return.

The user who left office for the day doesn't. That's the win. One warning will save you hundreds of frustrated support tickets, trust me. Step three, preserve state on re authentication. The session expired, the user logs back in.

You need to direct your AI to return them exactly where they were at, not the home page, not a blank dashboard, Their unsaved form, their half completed workflow, wherever they were. If re authentication erases that work, your security just costs you customer. Secure sessions, smart timeouts, and preserve state. Those are best practices. So build security that protects you without punishing your users.

---
_Source: https://the-faction.mn.co/posts/104567194_
