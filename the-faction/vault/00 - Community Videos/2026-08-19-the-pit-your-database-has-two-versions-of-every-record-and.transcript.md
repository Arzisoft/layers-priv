---
type: transcript
lesson: "Your database has two versions of every record and your app is showing users the"
course: "The Pit"
author: "Matt Murphy"
post_id: 106084435
published: "2026-08-19T14:00:04Z"
source_url: "https://the-faction.mn.co/posts/106084435"
duration: "2m14s"
words: 324
transcribed_by: "deepgram auto-captions (Mighty)"
---

# Transcript — Your database has two versions of every record and your app is showing users the

> Your database has two versions of every record and your app is showing users the wrong one. This is replication lag and it hits every app that scales past one database. Today I walk through read-after-write consistency routing that pins users to the primary after writes, replica lag monitoring with 

Your database has two versions of every record right now. And your app is showing users the wrong one. So your write went to primary, but your read came back from a replica that's three seconds behind it. Two databases, two versions of the truth, and your user is staring at the wrong one. They submitted a support ticket saying your app is broken.

It is not broken. It is lying to them. Here's what happens when your app scales past one database and your AI never accounted for replication lag. Step one, read after write consistency routing. When a user writes data, the next read from that same user must come from a primary, not a replica.

A short consistency window routes that user's reads to the primary for a defined period after any write. Everyone else continues reading from replicas. So Directory AI to implement session aware read routing that pins a user to the primary for a configurable window after any write. That's a win. Step two, replica lag monitoring with automatic failover thresholds.

So replication lag spikes under load during large transactions and during schema changes. If your replica falls ten seconds behind, every read from it returns data your users changed ten seconds ago. So direct your AI to instrument replica lag monitoring and define a threshold that reads automatically reroute to all primary until the replica catches up. And step three, conflict resolution on concurrent writes across regions. Two users editing the same record in two regions, both rights succeed on their local primary.

Replication carries both changes. One overwrites the other with no warning at all. So direct your AI to implement last right wins with timestamp resolution or operational transforms that merge concurrent changes instead of silently dropping one. Your database scaled. Your consistency, well, it didn't.

So direct your AI to fix the gap before your users find it for you. And that's the win.

---
_Source: https://the-faction.mn.co/posts/106084435_
