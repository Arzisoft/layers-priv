---
space: "The Pit"
author: "Matt Murphy"
post_id: 104567194
reactions: 4
comments: 1
published: "2026-07-14T15:08:31Z"
source: "https://the-faction.mn.co/posts/104567194"
---

# Today's fix is about idle session timeouts that punish active users.

Today's fix is about idle session timeouts that punish active users.

Your security settings kick users out every fifteen minutes.Even when they are actively working.Fifteen minutes idle means kill the session.But your definition of idle is broken.Here are three things you direct your AI to fix right now.

Step one.

Define meaningful activity.Mouse movement is not activity. A tab open in the background is not activity.Direct your AI to track actions that prove the user is working.Form submissions. Button clicks. API calls. Page navigation.If the user is reading a long document without clicking, that is not idle. Build an exception for sustained focus.

Step two.

Warn before you kill.Direct your AI to show a modal sixty seconds before the session expires.Your session expires in sixty seconds. Click to stay logged in.The user who stepped away for coffee sees it when they return. The user who left for the day does not.One warning saves a hundred frustrated support tickets.

Step three.

Preserve state on re-authentication.The session expired. The user logs back in.Direct your AI to return them exactly where they were.Not the homepage. Not a blank dashboard.Their unsaved form. Their half-completed workflow.If re-authentication erases their work, your security just cost you a customer.

Secure sessions. Smart timeouts. Preserved state.

Security that protects without punishing your users.

ORCHESTRATION PROMPT:

Implement session timeout that tracks meaningful user activity form submissions, button clicks, API calls, and page navigation not mouse movement or passive tab presence. Show a warning modal 60 seconds before session expiration with a one-click extend option. When a session expires and the user re-authenticates, restore their exact application state current page, unsaved form data, and workflow position.

---

## Video transcript

_deepgram auto-captions (Mighty) · 1m39s_

Your security settings are kicking users out every fifteen minutes, even when they're actively working. So your definition of idle might be broken. Here are the three things you're going to direct your AI to fix right now. Step one, define meaningful activity. Mouse movement, not an activity.

A tab open in the background, also not an activity. Direct your AI to track actions that prove the user is still working. Form submissions, button clicks, API calls, page navigation. If the user is reading a long document without clicking, that also is not idle. So build an exception for sustained focus.

That's a win. Step two, warn them before you kill them. Direct your AI to show a modal sixty seconds before the session expires. Your session expires in sixty seconds, click to stay logged in. The user who stepped away for coffee sees it when they return.

The user who left office for the day doesn't. That's the win. One warning will save you hundreds of frustrated support tickets, trust me. Step three, preserve state on re authentication. The session expired, the user logs back in.

You need to direct your AI to return them exactly where they were at, not the home page, not a blank dashboard, Their unsaved form, their half completed workflow, wherever they were. If re authentication erases that work, your security just costs you customer. Secure sessions, smart timeouts, and preserve state. Those are best practices. So build security that protects you without punishing your users.


---

## Discussion

**Efrain Gonzalez** · 2026-07-15

> Hmm... working on it!


---
_Source: https://the-faction.mn.co/posts/104567194_
