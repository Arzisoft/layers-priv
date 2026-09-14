---
space: "The Pit"
author: "Matt Murphy"
post_id: 105068746
reactions: 3
comments: 4
published: "2026-07-25T15:06:54Z"
source: "https://the-faction.mn.co/posts/105068746"
---

# If your app touches patient data, student health records, or any protected healt

If your app touches patient data, student health records, or any protected health information, you are subject to HIPAA right now. Your AI does not know that.

Today I walk through encryption requirements for PHI, access controls with audit logging, and Business Associate Agreements with every third-party service that touches your data. One complaint starts at $100 per violation.

 -MM

ORCHESTRATION PROMPT

Direct your AI: "I am building a healthcare application that handles protected health information. Perform a HIPAA compliance audit and build three systems: (1) Identify every field in my database that contains PHI and ensure encryption at rest and in transit. Check backups, application logs, and data exports for unencrypted PHI exposure. (2) Build role-based access controls for PHI records with a complete audit log: user ID, record accessed, action taken, timestamp, IP address, and session ID. The audit log must be immutable and retained for 6 years per HIPAA requirements. (3) Generate a Business Associate Agreement template and identify every third-party service in my stack that could access PHI (hosting, email, analytics, error tracking, payment processing). List which ones require a signed BAA."

---

## Video transcript

_deepgram auto-captions (Mighty) · 2m00s_

Your AI built a healthcare app, but it's never heard of HIPAA. One complaint to the Office for Civil Rights triggers an investigation that starts at one hundred dollars per violation and scales all the way up to two million dollars Your AI doesn't know that. It will literally store patient data wherever it wants and it'll transmit it however it feels like it and it'll log it again wherever it wants. So if your application touches any patient data, student health records, or protected health information, you're already subject to a federal regulation. And your AI?

Never asked a single question about it. So here are the three things you direct your AI to build right now if your app is touching health data. Step one, encryption at rest and in transit on every field that contains protected health information. Not just your database, your backups, your logs, your exports. Your AI may have encrypted that database but left PHI sitting in plain text in your application logs.

One log file is all it takes for a pretty significant fine. Step two, access controls with audit logging on every record that contains PHI. Who accessed it, when, from where, and what did they do with it? HIPAA requires you to produce this on demand. Your AI built role based access, but it did not build the paper trail that proves what touched what.

And step three, a business associate agreement with every third party service that touches that data. Your hosting provider, your email service, your analytics platform, if they can see protected health information, they need a BAA on file. Your AI integrated six services and signed zero agreements. One of those services has a breach and you're liable because you have no contract that defines the obligations. So yeah, your AI builds fast, but it does not build compliant.

Direct your AI to fix that before your first patient walks through the door.


---

## Discussion

**Efrain Gonzalez** · 2026-07-25

> Awesome, just what i needed!

  ↳ **Matt Murphy** · 2026-07-25

  > Thanks, Efrain!

**Naveed Arshad** · 2026-07-25

> I'm here for the transcripts. Just what I needed. It was hard to download videos and transcribe them.

  ↳ **Matt Murphy** · 2026-07-26

  > While you’re here, you should try the courses they’re way more informative than the videos or the prompts.


---
_Source: https://the-faction.mn.co/posts/105068746_
