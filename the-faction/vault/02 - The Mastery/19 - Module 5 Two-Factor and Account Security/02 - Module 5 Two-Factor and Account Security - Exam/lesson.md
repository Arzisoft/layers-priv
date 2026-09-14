---
course: "The Mastery"
module: "Module 5: Two-Factor and Account Security"
lesson: "Module 5: Two-Factor and Account Security — Exam"
type: "course_quiz"
post_id: 105098891
space_id: 24191170
source: "https://the-faction.mn.co/posts/105098891"
updated: "2026-08-10T20:44:09Z"
---

# Module 5: Two-Factor and Account Security — Exam

> Exam for **Module 5: Two-Factor and Account Security** (The Mastery) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. What does a second factor actually add to account security?

- **A.** A stronger password, since the code effectively doubles the credential's length
- **B.** Legal protection, transferring breach liability to the authenticator app's vendor
- **C.** Encryption of the session, upgrading the connection the login travels across
- **D.** An independent proof, so a stolen password alone is no longer enough to get in  ✅

> **Answer:** D

### Q2. What are the three classic factor categories?

- **A.** Something you know, something you have, and something you are, each proven separately  ✅
- **B.** Something you typed, something you clicked, and something you saved in the browser
- **C.** Your password, your username, and your registered recovery email address on file
- **D.** Your device model, your browser version, and your network connection's exact origin point

> **Answer:** A

### Q3. Why do authenticator apps beat SMS codes as a second factor?

- **A.** App codes are longer than SMS codes, and length is what determines factor strength
- **B.** SMS codes cost money per message while authenticator apps generate codes for free
- **C.** SMS can be intercepted or SIM-swapped; app codes never travel over a network at all  ✅
- **D.** Authenticator apps work offline in airplanes, the environment attackers exploit most

> **Answer:** C

### Q4. What are backup codes for, and how should users treat them?

- **A.** Speeding up login on slow networks; users should keep them in the browser's autofill list
- **B.** Regaining access when the second factor is lost; users should store them safely offline  ✅
- **C.** Sharing the account with family members; users should distribute one code per person
- **D.** Testing that 2FA works after setup; users should burn all of them at enrollment time

> **Answer:** B

### Q5. Where should 2FA be required rather than merely offered?

- **A.** Nowhere; requirements create friction, and offered-but-optional is the mature posture
- **B.** Everywhere equally, including read-only actions, since consistency is what users learn
- **C.** Only at signup, the single moment when identity is genuinely in question for the app
- **D.** On admin accounts and dangerous actions, where a takeover does the most damage  ✅

> **Answer:** D

### Q6. Why are account recovery flows the favorite target of attackers?

- **A.** Recovery pages load slowly, giving automated tools more time to operate per attempt
- **B.** Recovery emails are sent unencrypted, unlike every other message the application sends
- **C.** Recovery exists to bypass normal factors, so a weak flow undoes every strong factor  ✅
- **D.** Recovery endpoints are excluded from logging by convention, hiding attacker traffic

> **Answer:** C

### Q7. What is step-up authentication?

- **A.** Requiring fresh or stronger proof at the moment of a sensitive action, not just login  ✅
- **B.** Increasing password length requirements each year an account remains actively used
- **C.** Escalating a support ticket to a senior agent when login problems repeat themselves often
- **D.** Adding one extra factor per device, so a third device demands three separate proofs

> **Answer:** A

### Q8. Your AI proposes emailing the 2FA code to the account's email. What is the structural weakness?

- **A.** Email codes arrive slowly, and login abandonment climbs with every second of delay
- **B.** The email account resets the password too, so both factors collapse into one inbox  ✅
- **C.** Mail providers truncate numeric codes, causing support tickets that outweigh value
- **D.** Email codes cannot expire, unlike app codes which rotate every thirty seconds or so

> **Answer:** B

### Q9. "Trust this device for 30 days." What is the design consideration?

- **A.** Trusted devices sync across accounts, so one choice covers the household's logins
- **B.** Thirty days is a legal maximum, so the checkbox is really regulatory compliance
- **C.** Device trust removes the password requirement too, merging convenience with risk
- **D.** Each trusted device is a standing bypass of the second factor, so scope and expiry matter  ✅

> **Answer:** D

### Q10. Why notify users about logins from new devices or locations?

- **A.** The real owner is the best intrusion detector you have, if you give them the signal early  ✅
- **B.** Notifications prove app activity to the platform, protecting your app store ranking
- **C.** Login alerts are required before an app may store any authentication cookie at all
- **D.** Each notification resets the session clock, keeping active users logged in longer

> **Answer:** A

### Q11. An attacker deliberately fails 2FA repeatedly to lock the real owner out. What is this, and what is the balance?

- **A.** A billing exploit; the balance is charging per failed attempt so attacks fund defense
- **B.** A denial-of-service angle on lockouts; the balance is slowing attackers without jailing owners  ✅
- **C.** A phishing variant; the balance is user education against clicking unfamiliar links
- **D.** An impossibility; 2FA failures cannot lock accounts under any mainstream design today

> **Answer:** B

### Q12. What are passkeys, in practical terms?

- **A.** Hardware dongles shipped by your app to each user, proving possession through the mail
- **B.** Longer passwords generated by browsers, stored in the same field as normal ones are
- **C.** Cryptographic credentials bound to a device or account, replacing passwords entirely  ✅
- **D.** Temporary guest passwords that expire after a single use by a designated visitor

> **Answer:** C

### Q13. How do you roll out mandatory 2FA to an existing user base without chaos?

- **A.** Announce it, start with admins, offer a grace window, and support users through it  ✅
- **B.** Flip it on overnight for everyone, since a single painful day beats a slow migration
- **C.** Enforce it only for new signups forever, letting the existing base age out naturally
- **D.** Offer paid exemptions, converting the friction into a small recurring revenue line

> **Answer:** A

### Q14. A user has lost their phone, their backup codes, and their old number. What does a responsible flow do?

- **A.** Restore access instantly from the registered email, since email is the root identity
- **B.** Close the account permanently, the only response that fully protects the stored data
- **C.** Have support disable 2FA on request, since a human conversation is itself a factor
- **D.** Require real identity verification with friction and delay, because this is the takeover path  ✅

> **Answer:** D

### Q15. Why rate-limit 2FA code attempts specifically?

- **A.** Code checks are computationally heavy, and limits keep authentication servers quick
- **B.** Providers throttle apps that verify codes too frequently under their fair use terms
- **C.** Six-digit codes fall to brute force quickly if an attacker gets unlimited guesses  ✅
- **D.** Users mistype codes at predictable rates, and limits keep support volume forecastable

> **Answer:** C

### Q16. A user completes 2FA. What should happen to their session's standing?

- **A.** Nothing changes; 2FA is a login gate and sessions carry no memory of how they began
- **B.** The session is marked strongly verified, and that standing is what sensitive actions check  ✅
- **C.** The session doubles in length, the standard reward for completing the extra security steps
- **D.** The session locks to the device's exact network address, and drops if the user changes wifi

> **Answer:** B

### Q17. Attackers call your support line pretending to be locked-out users. What is the defense?

- **A.** Verification procedures support must follow every time, with no sympathy exceptions  ✅
- **B.** Removing the support phone line, closing the channel the attack depends on entirely
- **C.** Caller ID matching against the account's registered phone number before any conversation
- **D.** A callback delay of one hour, which outlasts the patience of most social engineers

> **Answer:** A

### Q18. How should TOTP secrets be stored on your side?

- **A.** Hashed like passwords, since secrets and passwords share identical storage needs
- **B.** In the frontend cache, so code verification can run without a network round trip
- **C.** In plain text but in a renamed column, hiding them from casual database inspection
- **D.** Encrypted server-side with tight access, since anyone reading them can mint valid codes  ✅

> **Answer:** D

### Q19. Which signals suggest an account takeover in progress?

- **A.** A user upgrading their plan, since attackers add capacity before extracting data
- **B.** Long sessions on one device, the signature of an attacker settled into an account
- **C.** New device, new location, factor changes, and recovery attempts clustered in time  ✅
- **D.** Faster typing between fields, measurable evidence that a script replaced the human

> **Answer:** C

### Q20. Why direct your AI to use an established 2FA library instead of implementing code generation itself?

- **A.** Custom code generation is patent-encumbered, exposing the business to real licensing claims
- **B.** The algorithms have edge cases like clock drift that libraries already handle correctly  ✅
- **C.** Libraries produce prettier codes, and visual clarity reduces mistyped code attempts
- **D.** Only registered libraries can talk to authenticator apps under platform agreements

> **Answer:** B

### Q21. What makes a security notification email itself safe, given that phishing imitates them?

- **A.** It informs and points users to the app they know, rather than pushing urgent links to click  ✅
- **B.** A large red banner, the visual convention that separates real alerts from imitations
- **C.** Sending from a different domain each time, keeping attackers from learning the pattern
- **D.** Including the user's password in the message, proof that only the real service could send it

> **Answer:** A

### Q22. What should the 2FA policy be for accounts with admin power in your AI-built app?

- **A.** Optional but encouraged through a banner, respecting each admin's stated personal preference
- **B.** Optional until an incident occurs, since real events are what justify real friction
- **C.** Mandatory without exceptions, because these accounts are where a takeover becomes a breach  ✅
- **D.** Replaced by IP restrictions, which protect admins without any per-login friction

> **Answer:** C

### Q23. The "remember this device" cookie: what must be true about it technically?

- **A.** It must contain the user's password encrypted, so trust can be re-verified silently
- **B.** It must be its own scoped, revocable token, not a longer-lived copy of the session  ✅
- **C.** It must be shared across all of the user's browsers, or the feature confuses people
- **D.** It must never expire, since expiring trust contradicts the promise of the checkbox

> **Answer:** B

### Q24. What should the enrollment flow teach in the thirty seconds it has?

- **A.** The history of two-factor authentication, since context is what really drives adoption rates
- **B.** The company's security certifications, building the trust that precedes enrollment
- **C.** How to disable 2FA later, since exit clarity is what makes people willing to enter
- **D.** Save the backup codes now, in a real place, because that is the step users skip and regret  ✅

> **Answer:** D

### Q25. Which principle should govern every 2FA and account security decision you direct?

- **A.** Strengthen the front door without leaving the back open: factors, recovery, and support must hold together  ✅
- **B.** Maximum factors everywhere: three proofs beat two, and friction is the fair price of safety
- **C.** 2FA is optional polish: real security lives in the password, and factors are mostly marketing
- **D.** Outsource the risk: once an authenticator app is involved, takeovers become its problem alone

> **Answer:** A


---
_Take it in the browser: https://the-faction.mn.co/posts/105098891_
