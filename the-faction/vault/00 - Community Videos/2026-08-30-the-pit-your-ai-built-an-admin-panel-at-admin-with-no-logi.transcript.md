---
type: transcript
lesson: "Your AI built an admin panel at /admin with no login screen. It assumed only you"
course: "The Pit"
author: "Matt Murphy"
post_id: 106569440
published: "2026-08-30T19:00:00Z"
source_url: "https://the-faction.mn.co/posts/106569440"
duration: "2m14s"
words: 373
transcribed_by: "deepgram auto-captions (Mighty)"
---

# Transcript — Your AI built an admin panel at /admin with no login screen. It assumed only you

> Your AI built an admin panel at /admin with no login screen. It assumed only you would know the URL. Every automated scanner on the internet already found it. Anyone can see your users, your transactions, and your settings. Some of them can change them. Today I walk through adding authentication to 

Your admin dashboard has no authentication because your AI assumed it was internal only. Well, it's not. It is on the public Internet. So your AI built an admin panel so you could manage your users, view orders, and update the settings. Right?

Well, it put it at backslash admin or backslash dashboard, whatever it is. No login screen, no access control. It assumed only you would know the URL. Well, every automated scanner on the Internet has already found it. Right now, anyone who types domain followed by backslash admin can see every user in your system, every transaction in your database, and every setting you can change.

Some of them, they can even change them themselves. So we need to shut it down. Step one, your admin panel is accessible to anyone who can guess the URL. There's no authentication between the public Internet and most of your sensitive controls. So direct your AI to add authentication to every admin route immediately.

No admin page should render without a verified session from a user with explicit admin privileges. Period. Not a regular user session, an admin session with role based verification. That's definitely a win. Step two, your admin routes are predictable pass, right?

Every scanner on earth is checking for backslash admin, backslash dashboard, backslash manage or back lash back end or admin. Right? So if your admin panel is at any of those, it's already been found. Direct your AI to move your admin routes to a non guessable path and implement rate limiting on login attempts to block brute force attacks on those. That's a win.

And step three, your admin panel has no audit trail. You do not know who's accessed it, when they accessed it, or what they changed. If someone has already been in your admin panel, you have no way to know what they saw or what they modified. So direct your AI to implement an audit log that records every admin action, every login attempt, every data change with time stamps and user identification. That's definitely a win.

Your admin panel is the keys to your entire business. Right now, you left those keys sitting on the sidewalk for anyone to pick up.

---
_Source: https://the-faction.mn.co/posts/106569440_
