---
space: "The Pit"
author: "Matt Murphy"
post_id: 107025616
reactions: 0
comments: 0
published: "2026-09-10T14:00:05Z"
source: "https://the-faction.mn.co/posts/107025616"
---

# An attacker just typed a crafted string into your search field and your database

An attacker just typed a crafted string into your search field and your database returned every user's credentials. Your AI dropped into raw SQL. User input goes directly into the query. A search field, a filter, a sort parameter. An attacker types a crafted string and your database answers. Direct your AI to use the ORM's safe raw query method that treats input as data, not as part of the command. Validate every input before it reaches any query. Constrain type and length. Then find every raw query in your codebase. One search. Any raw query built from user input is an open door. Your ORM is not the vulnerability. The one place your AI bypassed it is.

**PROMPT:** You are a Prisma security auditor specializing in SQL injection prevention. Review the following codebase for raw query vulnerabilities. Check: (1) Search for all instances of $queryRaw, $queryRawUnsafe, $executeRaw, and $executeRawUnsafe. Flag any use of the Unsafe variants as CRITICAL. (2) For each queryRawcall,determineifitusestaggedtemplateliterals(safe:prisma.queryRaw call, determine if it uses tagged template literals (safe: prisma. queryRawcall,determineifitusestaggedtemplateliterals(safe:prisma.queryRawSELECT * FROM users WHERE id = ${userId}) or string concatenation/interpolation (unsafe: prisma.$queryRaw("SELECT * FROM users WHERE id = " + userId)). (3) Check if user-supplied input flows into any raw query without validation. Trace the input from API route to query. (4) Verify input validation: type checking, length constraints, allowlist matching for enumerated values. (5) Check if any raw queries could be replaced with Prisma's built-in query methods. For each finding, provide the exact safe implementation.

---

## Video transcript

_deepgram auto-captions (Mighty) · 2m30s_

An attacker just typed a crafted string right into your search field and your database returned every user's credentials. That's not a win. Your AI dropped into raw SQL and removed every protection that Prisma provides. So your AI needed a complex join or a search feature, Prisma's standard methods could not handle it, so it wrote a raw SQL and every protection your ORM provides disappeared right then. The ORM protected you.

The escape hatch does not. So here's how you're gonna direct your AI to close that gap. Number one, your AI put user input directly into a database command. A search field, a filter or a sort parameter, right? So any input your users touch is now a direct line to your database with nothing standing between them.

So an attacker does not need to break into your system. They just type a crafted string to form in your AI built and your database answers every question that they ask. Customer tables, user credentials, payment records. They have access to everything. The ORM was designed to prevent exactly this.

So your AI bypassed it the moment the query got complicated. Right? So direct it to use the ORM safe method for raw queries. That treats input as data, not as a part of the command. And that's a win.

Number two, validate every input before it reaches any query. A search field that accepts ten thousand characters when the longest valid search is two hundred is not a feature. It's an open invitation to get hacked. A price filter that accepts text is not flexible. It's exploitable.

Directory add to constrain every input to the expected type and length before it touches the database layer at all. The validation should reject anything unexpected. Not try to sanitize it, reject it. That's the win. And number three, direct your AI to find every raw query in your code base right now.

One search, every instance. Any raw query that builds itself from user input is an open door to your system. So your AI may have written one or it may have written twenty. You do not know until you look. So each one is a direct channel between a form field and your entire Your arm is not the vulnerability, but that one place your AI bypassed it certainly is.

Go find it. Get it fixed.


---
_Source: https://the-faction.mn.co/posts/107025616_
