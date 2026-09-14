---
type: transcript
lesson: "Your RLS policies are your second wall."
course: "The Pit"
author: "Matt Murphy"
post_id: 103874347
published: "2026-06-29T14:15:08Z"
source_url: "https://the-faction.mn.co/posts/103874347"
duration: "1m34s"
words: 234
transcribed_by: "deepgram auto-captions (Mighty)"
---

# Transcript — Your RLS policies are your second wall.

> Your RLS policies are your second wall.

Your RLS policies exist and they look great, but your API keeps bypassing them. Here are the three things you do right now to fix it. Step one: Audit usage of every service role key. The service role key skips all RLS policies. So find every API route that uses it and list them out.

If the service key appears in client side code, your database is fully public. Replace the service roll calls with a non key and user scope JWTs everywhere you can. When you must use the service key, lock it inside server side functions that validate every request before it touches the database. That's a win. Step two, API middleware as the first wall.

Every endpoint gets three checks before it processes anything. Is the user authenticated? Is the user authorized for this specific resource? And does the input pass validation? Your RLS policies are your second wall.

Your middleware is your first. If the first wall has no guards, the second wall doesn't even matter. Step three, edge validation before the request reaches your server. Malformed payload rejected, oversized requests rejected, missing tokens rejected, three paths, three locks. Security is not one policy on the database.

It is every single gate between the user and your data. If you're interested in the longer format, a deep dive video into this topic, it can be found in The War Room.

---
_Source: https://the-faction.mn.co/posts/103874347_
