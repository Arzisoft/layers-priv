---
type: transcript
lesson: "Three backup decisions you make right now."
course: "The Pit"
author: "Matt Murphy"
post_id: 104073060
published: "2026-07-03T13:15:06Z"
source_url: "https://the-faction.mn.co/posts/104073060"
duration: "1m34s"
words: 244
transcribed_by: "deepgram auto-captions (Mighty)"
---

# Transcript — Three backup decisions you make right now.

> Three backup decisions you make right now.

Your app has no backup strategy and that means that your users have no protection. So here are the three things you need to decide right now to fix it. Step one, frequency. Your database changes every time a user does anything. A daily backup means you accept losing up to twenty four hours of their data.

If your app processes payments, that's twenty four hours of revenue you can't recover. So point in time recovery captures every transaction continuously and almost every managed database supports it. It's a setting, turn it on, that's a win. Step two, Location. Your backup lives on the same server as your database.

When the server dies, the backup dies with it. That's not a win. That is not even a backup. That is a second copy of the exact same risk. So cross region or off-site backup is the backup that must survive things that kill your primary server.

Step three. Test the restore. And for the people in the back, test the restore. Your backup has been running for months. You've never restored it.

A backup you've never tested is not a safety net. It's not even a backup. It's a guess. So restore to a test environment once a month minimum. Verify that data, verify the app runs, because the worst time to find out your backup is broken is during the outage you need a backup.

So decide before your users decide for you.

---
_Source: https://the-faction.mn.co/posts/104073060_
