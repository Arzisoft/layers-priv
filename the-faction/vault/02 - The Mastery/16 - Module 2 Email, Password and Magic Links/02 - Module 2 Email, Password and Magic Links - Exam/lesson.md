---
course: "The Mastery"
module: "Module 2: Email, Password and Magic Links"
lesson: "Module 2: Email, Password and Magic Links — Exam"
type: "course_quiz"
post_id: 105098472
space_id: 24191170
source: "https://the-faction.mn.co/posts/105098472"
updated: "2026-08-10T20:44:09Z"
---

# Module 2: Email, Password and Magic Links — Exam

> Exam for **Module 2: Email, Password and Magic Links** (The Mastery) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. How must passwords be stored in your AI-built app?

- **A.** Encrypted with a key the app holds, so support staff can decrypt one when users call in for help
- **B.** In a separate database from user profiles, where plain text storage becomes acceptable
- **C.** As strong one-way hashes with a modern algorithm, so nobody, including you, can read them  ✅
- **D.** Compressed and reversed, a transformation attackers do not expect from smaller apps

> **Answer:** C

### Q2. What actually makes a password policy strong?

- **A.** Requiring real length and checking against known breached passwords, over symbol theater  ✅
- **B.** Forcing a symbol, a number, and a capital letter, the combination attackers supposedly can't guess
- **C.** Rotating every password monthly, since age is the property that weakens credentials
- **D.** Capping length at twelve characters, since longer passwords slow the hashing service

> **Answer:** A

### Q3. What is a magic link, mechanically?

- **A.** A permanent personal URL each user bookmarks and reuses as their private entrance
- **B.** A shortcut that skips identity checks for returning visitors recognized by device
- **C.** A link that shares a logged-in session between two of the same user's own devices
- **D.** A single-use, expiring login link sent to the user's email, proving control of that inbox  ✅

> **Answer:** D

### Q4. What two properties must every magic link have to be safe?

- **A.** A memorable URL and a branded domain, so users learn to recognize legitimate links
- **B.** A short expiry and single-use consumption, so an old or intercepted link buys nothing  ✅
- **C.** A visible username inside the URL and a click counter that users can verify themselves
- **D.** Delivery to two addresses at once, so a compromised inbox alone cannot complete login

> **Answer:** B

### Q5. Why verify email addresses at signup at all?

- **A.** Unverified addresses mean typos, fakes, and someone else's inbox holding the account keys  ✅
- **B.** Verification is what activates the free tier of most transactional email providers
- **C.** Verified emails load faster in the database, since confirmed rows skip repeated validity checks
- **D.** It is a legal requirement before any application may store a name alongside an email

> **Answer:** A

### Q6. What should happen after repeated failed login attempts on one account?

- **A.** Nothing visible, since reacting to failures teaches attackers which accounts exist
- **B.** Permanent account closure, since repeated failure is itself the proof of an attack
- **C.** Progressive slowing or a temporary hold, raising the cost of guessing without killing access  ✅
- **D.** An immediate password reset email, replacing the credential the attacker is guessing at

> **Answer:** C

### Q7. A login fails. Why should the error message stay generic?

- **A.** Generic errors render faster, and login speed is where users judge overall application quality
- **B.** Specific errors expose the framework's names for fields, helping attackers pick tools
- **C.** Detailed messages overflow mobile screens, and truncated errors confuse users more
- **D.** Saying which part was wrong confirms which accounts exist, feeding attackers a user list  ✅

> **Answer:** D

### Q8. You find plaintext passwords in your AI's debug logs. What do you direct?

- **A.** Restrict the log files to admin readers only, since access control makes the entries safe
- **B.** Strip credentials from logging now, purge stored logs, and treat exposed ones as burned  ✅
- **C.** Keep the logs but rename the field so automated scanners no longer match on the word
- **D.** Nothing yet; debug logs rotate away within weeks, which retires the exposure naturally

> **Answer:** B

### Q9. Why check new passwords against lists of known breached passwords?

- **A.** Breach lists are the licensing source for password strength meters used in signup forms
- **B.** It satisfies the database vendor's terms, which forbid storing previously leaked strings
- **C.** Attackers try leaked passwords first, so blocking them removes the likeliest successful guesses  ✅
- **D.** Breached passwords hash more slowly, and screening them keeps login latency predictable

> **Answer:** C

### Q10. Someone signs up with an email that already has an account. What should the flow do?

- **A.** Behave identically either way to outsiders, and alert the real owner through their inbox  ✅
- **B.** Show 'this email is already registered' clearly, since honesty is the best experience
- **C.** Merge the two signups automatically, since matching emails prove a shared identity
- **D.** Block that email address for a day, giving the true owner time to notice the collision first

> **Answer:** A

### Q11. What is the real security ceiling of magic-link-only authentication?

- **A.** Links stop working on corporate networks, locking out the business users worth the most
- **B.** The account is exactly as secure as the user's inbox, and inboxes get compromised often  ✅
- **C.** Email delivery costs scale with logins, making the model unaffordable past early stage
- **D.** Browsers throttle repeated link opens, which caps how often any single user can actually log in

> **Answer:** B

### Q12. Why is hashing, not encryption, the correct treatment for passwords?

- **A.** Hashes take less storage than encrypted values, which matters at millions of accounts
- **B.** Encryption is patented for credential use, while hashing is free for commercial apps
- **C.** Hashing runs on the browser side, which keeps the password off your servers entirely
- **D.** Encryption is reversible by design; a hash can be checked but never turned back into text  ✅

> **Answer:** D

### Q13. A user changes their password. What should happen to their other active sessions?

- **A.** They get invalidated, so anyone holding the old credential or a hijacked session is out  ✅
- **B.** They continue untouched, since interrupting other devices punishes the legitimate user
- **C.** They convert to read-only access for a week, a compromise between security and user convenience
- **D.** They transfer to the new password automatically, keeping every device logged in cleanly

> **Answer:** A

### Q14. What does a salt add to password hashing?

- **A.** A second password layered onto the first, doubling what an attacker has to guess and work through
- **B.** A timestamp inside the hash, letting the app age out credentials that get too old
- **C.** Uniqueness per user, so identical passwords hash differently and rainbow tables go useless  ✅
- **D.** Compression of the final hash, cutting the storage cost of the credentials table in half

> **Answer:** C

### Q15. Where should sending of verification and reset emails happen relative to the web request?

- **A.** Inline before responding, since the user must not see success until the email has actually landed
- **B.** In a background queue, so slow email providers never hang or fail the user-facing request  ✅
- **C.** In a nightly batch, since bundled sends cost less than individual transactional emails
- **D.** On the user's own device, which keeps the email contents off your servers completely

> **Answer:** B

### Q16. How should email flows be tested in development?

- **A.** With the founder's personal inbox as the catch-all, since one person can monitor it live
- **B.** By skipping email tests entirely, since delivery providers guarantee inbox placement contractually
- **C.** Against the production user list at low volume, since only real inboxes prove the flow
- **D.** Through a sandbox or capture tool, so no real user ever receives a test email by mistake  ✅

> **Answer:** D

### Q17. Throttling versus hard lockout after failed logins: what is the trade being weighed?

- **A.** Slowing attackers versus letting an attacker deliberately lock real users out of accounts  ✅
- **B.** Server cost versus email cost, since each lockout triggers a notification message
- **C.** Nothing real; the two mechanisms are identical in effect and differ only in naming
- **D.** Speed of login versus strength of password, the classic usability exchange in auth

> **Answer:** A

### Q18. Why normalize emails, trimming spaces and lowering case, before storing or matching?

- **A.** Mixed-case emails cost more to index, and normalization keeps the table inside limits
- **B.** The same person typing variants of their address must land on one account, not several  ✅
- **C.** Email providers reject mixed-case addresses, so normalization prevents delivery failure
- **D.** Normalization encrypts the address as a side effect, improving privacy posture for free

> **Answer:** B

### Q19. Your AI caps passwords at 16 characters 'for safety'. What do you direct?

- **A.** Keep the cap but raise it to 20, the upper bound that hashing services support reliably
- **B.** Lower it to 12, since shorter maximums reduce the storage the credentials table needs
- **C.** Remove the low cap and allow long passphrases; length is what makes passwords strong  ✅
- **D.** Add a second field for overflow characters, preserving both the cap and long passwords

> **Answer:** C

### Q20. Your AI proposes SMS codes as the primary login method. What should shape the decision?

- **A.** SIM swap risk, delivery reliability, and per-message cost, weighed against your users  ✅
- **B.** Nothing; SMS is the industry default and defaults exist so builders can skip decisions
- **C.** The character limit of SMS, since codes above six digits split into multiple messages
- **D.** Whether your AI can generate the SMS templates, since copywriting is the hard part

> **Answer:** A

### Q21. Why have security questions like 'mother's maiden name' fallen out of practice?

- **A.** They doubled login time, and conversion data showed users abandoning at the question
- **B.** Storing questions costs more than passwords, since answers require their own tables
- **C.** Regulations now classify family names as biometric data, restricting their collection broadly
- **D.** The answers are guessable or publicly findable, a weaker secret than the password itself  ✅

> **Answer:** D

### Q22. What makes the email that carries a magic link trustworthy rather than phishing-like?

- **A.** A subject line in capital letters, since urgency is what separates real mail from fakes
- **B.** Attaching the link as a PDF, since attachments carry more authority than inline links
- **C.** Clear sender identity, a stated expiry, and no request for anything beyond the click  ✅
- **D.** Sending it twice in a row, since duplicates prove the message came from a real system

> **Answer:** C

### Q23. A spike of failed logins hits hundreds of accounts in an hour. What is this, and what should catch it?

- **A.** A traffic surge from a marketing win; a conversion dashboard ought to celebrate it properly
- **B.** Credential stuffing from a breach elsewhere; monitoring with alerts should surface it live  ✅
- **C.** A browser bug corrupting passwords; a support macro should be ready for the ticket wave
- **D.** Users forgetting passwords after a holiday; no system response is actually required

> **Answer:** B

### Q24. Your hashing algorithm is outdated and needs upgrading. How do you migrate existing hashes?

- **A.** Decrypt every stored hash and rehash the results with the new algorithm in one batch job
- **B.** Email all users their current passwords and ask them to re-enter them under the new scheme
- **C.** Delete all password hashes and force a global reset, the only technically possible route
- **D.** Rehash each user's password at their next login, when the plaintext is briefly present  ✅

> **Answer:** D

### Q25. Which principle should govern every credential decision you direct?

- **A.** Hold secrets so you can't reveal them: hash passwords, expire links, and say nothing useful  ✅
- **B.** Convenience first: every security measure that costs a signup is a measure to remove
- **C.** Match the biggest apps: copy the login flow of the largest tech company and stay current
- **D.** Trust the inbox: email possession is identity, so every flow can safely reduce to email

> **Answer:** A


---
_Take it in the browser: https://the-faction.mn.co/posts/105098472_
