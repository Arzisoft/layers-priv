---
space: "The Pit"
author: "Matt Murphy"
post_id: 105993244
reactions: 5
comments: 0
published: "2026-08-15T19:00:01Z"
source: "https://the-faction.mn.co/posts/105993244"
---

# Nightly backups are a 24-hour gamble on nothing going wrong between snapshots. T

Nightly backups are a 24-hour gamble on nothing going wrong between snapshots. Today I walk through point-in-time recovery, tested restoration runbooks, and defining your RTO and RPO. If you have never restored from a backup into a working database, this one is for you.

**PROMPT:** Direct your AI: "Build a database disaster recovery system: PITR configuration with WAL archiving, quarterly restoration test runbook, and RTO/RPO definition matched against current backup capability."

---

## Video transcript

_deepgram auto-captions (Mighty) · 2m16s_

Your database just lost fourteen hours of customer data. Your last backup from midnight. Everything users did today, every transaction, every upload, every message, every account change, Gone. Because your AI set up nightly backups but your database failed at two pm in the afternoon. So nightly backups are not disaster recovery.

They are a twenty four hour gamble on nothing going wrong between those two snapshots. So here's what the real database disaster recovery looks like. One, point in time recovery. Not nightly snapshots, continuous write ahead log archiving that lets you restore your database to any second, not just midnight. So if your database crashes at two forty seven pm, your restore comes back at two forty six.

You lose one minute of data instead of fourteen hours. Your AI knows how to configure WAL archiving. Supabase supports PITR on paid plans and every major provider offers it. Your AI never turned it on because nightly felt like enough. Step two, a tested restoration runbook.

Not a backup that exists, a backup that has been restored. When was the last time you actually restored from a backup into a working database? If the answer is never, your backup is a hope, not a plan. Direct your AI to schedule a quarterly restoration test at a minimum. Spin up clean environment, restore into it, verify the data is intact and the application runs.

Document the steps, time it. Your recovery time is not theoretical. It's always measured every time. That's a win. And step three, a defined RTO and RPO.

Recovery time objective is how long your business can survive with the database down. Recovery point objective is how much data can you afford to lose. If you do not know these numbers, your AI cannot build a recovery plan that meets them. So direct your AI to define both based on your business requirements, not your infrastructure defaults. Your backup is not your recovery plan.

Your tested, timed, documented recovery plan is your recovery plan. Get out there and make one.


---
_Source: https://the-faction.mn.co/posts/105993244_
