---
course: "The Mastery"
module: "Module 6: Password Reset and Edge Cases"
lesson: "Module 6: Password Reset and Edge Cases — Exam"
type: "course_quiz"
post_id: 105099028
space_id: 24191170
source: "https://the-faction.mn.co/posts/105099028"
updated: "2026-08-10T20:44:09Z"
---

# Module 6: Password Reset and Edge Cases — Exam

> Exam for **Module 6: Password Reset and Edge Cases** (The Mastery) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. What is the anatomy of a safe password reset flow?

- **A.** The user answers their security question and picks a new password on the same page
- **B.** A time-limited, single-use token sent to the verified email, exchanged for a new password  ✅
- **C.** Support verifies the caller's date of birth and reads a temporary password over the phone
- **D.** The app texts the old password to the registered number so the user can log in and change it

> **Answer:** B

### Q2. Why must the app never email the user their existing password?

- **A.** Emailed passwords get flagged as spam, so the message rarely reaches the user anyway
- **B.** Email length limits truncate long passwords, delivering a string that no longer works at login
- **C.** Being able to send it means you stored it readably, the deeper failure the email reveals  ✅
- **D.** Password emails are billed at a premium rate by every transactional mail provider

> **Answer:** C

### Q3. What properties must the reset token itself have?

- **A.** Random, expiring, single-use, and stored hashed, so a leak doesn't leak live reset keys  ✅
- **B.** Sequential and memorable, so support can read one to a user over the phone if ever needed
- **C.** Derived from the username, so tokens can be regenerated without a database lookup
- **D.** Permanent per account, so a user's reset link works whenever they eventually need it

> **Answer:** A

### Q4. Someone requests a reset for an email with no account. What should the response say?

- **A.** "No account exists for this address," the honest answer that saves the visitor time
- **B.** "This address is blocked," discouraging the probing without confirming anything real about accounts
- **C.** An error code only, letting the visitor's own technical skill interpret the outcome
- **D.** The same message as for a real account, so the endpoint never confirms who is registered  ✅

> **Answer:** D

### Q5. A user requests a second reset link while the first is still valid. What should happen to the first?

- **A.** Both remain valid until their natural expiry, since invalidating links breaks user trust
- **B.** The earlier token dies when the new one is issued, so only one live reset path exists  ✅
- **C.** The first link upgrades to admin scope, reflecting the urgency two requests imply
- **D.** The account locks for an hour, since repeated requests are themselves suspicious

> **Answer:** B

### Q6. Why should completing a password reset invalidate the account's active sessions?

- **A.** If an intruder is the reason for the reset, this is the moment their access actually ends  ✅
- **B.** Session tables need periodic clearing anyway, and resets are a convenient trigger
- **C.** Fresh sessions render faster, giving the user a subtly better post-reset experience
- **D.** Regulations require session churn after any credential change in consumer software

> **Answer:** A

### Q7. Your AI built a reset where clicking the email link immediately sets a new random password. What is the flaw?

- **A.** Random passwords are weaker than user-chosen ones, downgrading account security
- **B.** The flow works but wastes an email, since the new password requires its own message
- **C.** Password generation on click doubles server load during reset traffic spikes
- **D.** Link clicks happen without intent, by scanners and previews; the change needs a real form  ✅

> **Answer:** D

### Q8. A user wants to change the email on their account. What does the safe flow verify?

- **A.** The new address only, since the old one is already proven by the active session
- **B.** Nothing beyond the session, since email changes are profile edits like any other
- **C.** Control of the new address, notice to the old one, and re-authentication before the swap  ✅
- **D.** A waiting period of thirty days, after which the change applies automatically

> **Answer:** C

### Q9. A reset is requested for a deactivated account. What should the flow do?

- **A.** Reactivate the account automatically, since a reset request proves renewed interest
- **B.** Behave outwardly like any reset, while internally following the account's state rules  ✅
- **C.** Return a clear "account deactivated" message so the requester contacts support instead
- **D.** Forward the request to the sales team, since deactivated users are win-back leads

> **Answer:** B

### Q10. Attackers script thousands of reset requests against your user list. What limits the damage?

- **A.** Rate limits per account and per source, so the flood is throttled before inboxes fill  ✅
- **B.** Larger email sending quotas, so legitimate resets still fit alongside the attack volume
- **C.** A CAPTCHA on login only, since reset endpoints are not what such scripts target
- **D.** Nothing; reset floods are harmless because the links all require inbox access anyway

> **Answer:** A

### Q11. Corporate email scanners open every link, consuming single-use reset tokens before users can. What is the fix?

- **A.** Detect scanners by speed and serve them fake pages while burning the token anyway
- **B.** Exempt corporate domains from single-use rules, restoring convenience for business
- **C.** Consume the token on the form's submission rather than the link's opening, not the click  ✅
- **D.** Send reset links twice, giving each user a spare after the scanner consumes the first one

> **Answer:** C

### Q12. A user has lost access to their email entirely. What does responsible account recovery look like?

- **A.** Instant reset via SMS, since the phone is a strict superset of email as identity proof
- **B.** Automatic transfer to any new email the user types, since typing shows intent clearly
- **C.** Permanent loss, since email is identity and identity loss is by definition fully unrecoverable
- **D.** A slower manual path with real identity verification, because this is how takeovers happen  ✅

> **Answer:** D

### Q13. What belongs in the reset email itself?

- **A.** The account's username and recent activity, context proving the message's apparent legitimacy
- **B.** The link, a clear expiry, and a note to ignore it if unrequested, nothing personal beyond  ✅
- **C.** The old password's first two characters, helping the user recall before they reset
- **D.** A phone number to call instead, since voice channels are safer than clickable links

> **Answer:** B

### Q14. A password change completes. Who gets told, and why?

- **A.** The account's email gets a notification, so an unauthorized change is discovered fast  ✅
- **B.** Nobody, since confirmations train users to expect email and expand the phishing surface
- **C.** The whole team on shared workspaces, since credential changes affect collaborators
- **D.** Support staff, who keep a manual ledger of changes for dispute resolution later on

> **Answer:** A

### Q15. Your app uses email as the login identity, and a user's company domain just changed. What surfaces?

- **A.** Nothing; email changes are cosmetic once an account's internal ID exists in the tables
- **B.** A billing question, since invoices carry the email address and finance requires continuity
- **C.** Every place that treated the email as permanent: login, invites, and history must move  ✅
- **D.** A legal notice requirement, since identity changes must be published in most regions

> **Answer:** C

### Q16. Two reset tokens exist because the user double-clicked. Which should work?

- **A.** Only the newest issued token, with all earlier ones dead the moment it was created  ✅
- **B.** Both, since punishing a double-click with a dead link is hostile to already nervous users
- **C.** Whichever arrives at the server first, with the race decided by network timing
- **D.** Neither, forcing a third clean request as the tiebreaker between the duplicates

> **Answer:** A

### Q17. Your AI shipped the happy path and calls the reset feature done. Why is that the beginning, not the end?

- **A.** The happy path still needs visual polish, and design review is the actual finish line
- **B.** Feature completion requires load testing, which no reset flow has yet passed here
- **C.** Marketing hasn't announced the feature, and unannounced features are unfinished ones
- **D.** Auth quality lives in the edges: expired tokens, scanners, floods, and lost access decide it  ✅

> **Answer:** D

### Q18. What does a real test pass over the reset flow include?

- **A.** One successful reset on the founder's account, witnessed by the team on a call
- **B.** Expired, reused, and tampered tokens, wrong accounts, and flood behavior, all attempted  ✅
- **C.** A survey of users about whether they feel the reset flow can be trusted fully
- **D.** Comparing screenshot pixels against the design file for every state of the form

> **Answer:** B

### Q19. A user asks to delete their account. What does a safe deletion flow include?

- **A.** Instant, irreversible deletion on click, since hesitation features disrespect user intent
- **B.** A phone confirmation with support, the only channel where identity is fully provable
- **C.** Re-authentication, a clear grace window, and honest communication about what is removed  ✅
- **D.** Conversion to a dormant plan, since true deletion is unnecessary if billing stops

> **Answer:** C

### Q20. An account dormant for three years suddenly resets its password and drains its stored value. What was missing?

- **A.** A dormancy fee that would have emptied the balance before any attacker could reach it
- **B.** An age cap on accounts, closing anything unused for more than twenty-four months
- **C.** A rule against storing value, the feature that made the account worth taking over
- **D.** Extra verification for high-risk actions on long-dormant accounts, the prime targets  ✅

> **Answer:** D

### Q21. Why should the reset request endpoint respond in roughly constant time whether or not the account exists?

- **A.** Response-time differences leak which emails are registered, the secret the text protects  ✅
- **B.** Constant timing satisfies latency budgets, keeping the endpoint inside its SLA quite cleanly
- **C.** Timers on the frontend break when responses vary, so the constraint is a UI one really
- **D.** Email providers penalize bursty senders, and steady timing smooths the sending curve

> **Answer:** A

### Q22. Support receives a convincing, urgent request to reset a customer's password manually. What governs the response?

- **A.** Empathy and speed, since locked-out customers churn within hours of a single bad experience
- **B.** Seniority, with manager approval converting any manual reset into an authorized one
- **C.** The verification procedure, followed exactly, because urgency is the attacker's main tool  ✅
- **D.** Ticket volume, with manual resets allowed whenever the queue can absorb the risk

> **Answer:** C

### Q23. Which reset-related events belong in the audit log?

- **A.** Only completed resets, since requests that never finish carry no security meaning
- **B.** Requests, sends, completions, and failures, with time and source, since patterns tell all  ✅
- **C.** Nothing; reset logs contain emails, and storing emails in logs is itself the real violation
- **D.** Only failures, since successful resets are routine and logging routine wastes storage

> **Answer:** B

### Q24. A token expires while the user is filling in their new password. What separates good handling from bad?

- **A.** Good apps extend the token silently when the form is open, since presence proves intent
- **B.** Nothing; expiry mid-form is rare enough that any behavior is acceptable in practice
- **C.** Good apps auto-submit the form at the expiry moment, racing the deadline for the user
- **D.** A clear message and a one-click path to a fresh link, instead of a dead-end error page  ✅

> **Answer:** D

### Q25. Which principle should govern reset and recovery design in every build you direct?

- **A.** Recovery is the back door: build it as carefully as login, because attackers walk through it  ✅
- **B.** Recovery is support's job: humans resolve lockouts better than any automated flow
- **C.** Recovery is friction: the harder regaining access is, the more secure the app becomes
- **D.** Recovery is rare: engineering effort belongs on the login path that runs every day

> **Answer:** A


---
_Take it in the browser: https://the-faction.mn.co/posts/105099028_
