---
type: transcript
lesson: "If your app touches patient data, student health records, or any protected healt"
course: "The Pit"
author: "Matt Murphy"
post_id: 105068746
published: "2026-07-25T15:06:54Z"
source_url: "https://the-faction.mn.co/posts/105068746"
duration: "2m00s"
words: 326
transcribed_by: "deepgram auto-captions (Mighty)"
---

# Transcript — If your app touches patient data, student health records, or any protected healt

> If your app touches patient data, student health records, or any protected health information, you are subject to HIPAA right now. Your AI does not know that.

Your AI built a healthcare app, but it's never heard of HIPAA. One complaint to the Office for Civil Rights triggers an investigation that starts at one hundred dollars per violation and scales all the way up to two million dollars Your AI doesn't know that. It will literally store patient data wherever it wants and it'll transmit it however it feels like it and it'll log it again wherever it wants. So if your application touches any patient data, student health records, or protected health information, you're already subject to a federal regulation. And your AI?

Never asked a single question about it. So here are the three things you direct your AI to build right now if your app is touching health data. Step one, encryption at rest and in transit on every field that contains protected health information. Not just your database, your backups, your logs, your exports. Your AI may have encrypted that database but left PHI sitting in plain text in your application logs.

One log file is all it takes for a pretty significant fine. Step two, access controls with audit logging on every record that contains PHI. Who accessed it, when, from where, and what did they do with it? HIPAA requires you to produce this on demand. Your AI built role based access, but it did not build the paper trail that proves what touched what.

And step three, a business associate agreement with every third party service that touches that data. Your hosting provider, your email service, your analytics platform, if they can see protected health information, they need a BAA on file. Your AI integrated six services and signed zero agreements. One of those services has a breach and you're liable because you have no contract that defines the obligations. So yeah, your AI builds fast, but it does not build compliant.

Direct your AI to fix that before your first patient walks through the door.

---
_Source: https://the-faction.mn.co/posts/105068746_
