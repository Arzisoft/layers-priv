---
course: "The Mastery"
module: "Module 1: Auth Architecture and Session Models"
lesson: "Module 1: Auth Architecture and Session Models — Exam"
type: "course_quiz"
post_id: 105098293
space_id: 24191170
source: "https://the-faction.mn.co/posts/105098293"
updated: "2026-08-10T20:44:09Z"
---

# Module 1: Auth Architecture and Session Models — Exam

> Exam for **Module 1: Auth Architecture and Session Models** (The Mastery) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. What question is authentication actually answering in your AI-built app?

- **A.** Which features this account has paid for, so the app can display the right pricing tier and limits
- **B.** Who this person actually is, proven by something only the real account holder can provide  ✅
- **C.** How fast the app should respond to this person, based on their current subscription level
- **D.** Which server region the person's requests should route to for the lowest possible latency

> **Answer:** B

### Q2. What is the difference between authentication and authorization?

- **A.** They are two names for the same check, kept separate only for historical library reasons
- **B.** Authentication covers web apps while authorization is the equivalent standard for mobile
- **C.** Authorization happens first at signup, and authentication takes over after the very first login
- **D.** Authentication proves who you are; authorization decides what that identity is allowed to do  ✅

> **Answer:** D

### Q3. What is a session in a server-session auth model?

- **A.** A server-side record of a logged-in user, referenced by an ID the browser sends with requests  ✅
- **B.** The window of time a user keeps the browser tab open before the app forces a full page refresh
- **C.** A compressed copy of the user's profile cached in the browser for faster page loading
- **D.** The database transaction that wraps all of a user's actions until they log out again

> **Answer:** A

### Q4. Your AI asks whether to use server sessions or stateless tokens. What is the real trade-off?

- **A.** Tokens only work on mobile apps, while server sessions only work in desktop browsers
- **B.** Sessions are free while token libraries carry licensing costs at real production scale
- **C.** Tokens avoid a server lookup but are hard to revoke; sessions revoke instantly but need storage  ✅
- **D.** There is none; the two approaches are fully interchangeable in every practical situation

> **Answer:** C

### Q5. Why direct your AI to use a proven auth library or provider instead of writing auth from scratch?

- **A.** Auth is full of subtle failure modes; proven components carry years of fixes you'd relearn painfully  ✅
- **B.** Custom auth code is illegal for commercial applications under most consumer protection law
- **C.** Scratch-built auth runs slower because it cannot access the browser's native login cache
- **D.** App stores reject applications whose login screens were not built from their certified kits

> **Answer:** A

### Q6. Why do sessions expire at all instead of lasting forever?

- **A.** Expiry frees database rows, and session tables otherwise grow past what hosting plans allow
- **B.** Browsers delete cookies weekly regardless, so matching that schedule avoids login errors
- **C.** Regulators cap login duration at thirty days for any app that stores personal information
- **D.** A stolen or abandoned session becomes worthless once it lapses, capping the damage window  ✅

> **Answer:** D

### Q7. Where should the secret keys that sign or protect sessions live?

- **A.** In the frontend bundle, lightly encoded so casual readers cannot recognize the values
- **B.** In protected server configuration, never in code files that get committed or shared around  ✅
- **C.** In the users table, so each account's row carries the key material that protects it
- **D.** In the team chat, pinned for quick reference whenever an agent needs to rebuild auth

> **Answer:** B

### Q8. Your AI sets the session cookie without HttpOnly or Secure flags. Why direct a fix?

- **A.** Unflagged cookies expire at random intervals, logging users out in the middle of active sessions
- **B.** Browsers now show warning banners on unflagged cookies, which damages user confidence
- **C.** Those flags keep the cookie away from page scripts and off plain connections, blocking theft  ✅
- **D.** Cookie flags compress the session payload, and skipping them slows down every page load

> **Answer:** C

### Q9. A user clicks log out. What must actually happen for logout to be real?

- **A.** The session is invalidated on the server side, so the old ID stops working even if replayed  ✅
- **B.** The browser tab closes automatically, since an open tab is what keeps a session alive
- **C.** The user's row is locked for an hour, preventing any immediate re-authentication attempt afterward
- **D.** The logout is recorded in analytics, since measured logouts are what define the feature

> **Answer:** A

### Q10. Your AI stores the session token in localStorage for convenience. What is the risk?

- **A.** localStorage is wiped on every browser update, forcing all users to log in again weekly
- **B.** Any script that runs on the page can read it, so one injected script walks away with logins  ✅
- **C.** localStorage entries sync across devices, letting family members share accounts freely
- **D.** Tokens in localStorage expire twice as fast, doubling the login prompts users experience daily

> **Answer:** B

### Q11. What is the honest trade-off of a long-lived "remember me" session?

- **A.** Longer sessions cost more, since providers bill by the total hours sessions stay alive overall
- **B.** Remembered sessions slow the app, since each request carries a heavier signed payload
- **C.** There is none; convenience features by definition carry no security cost worth naming
- **D.** Convenience rises but so does exposure: a stolen device or cookie stays useful far longer  ✅

> **Answer:** D

### Q12. Why build a screen where users can see and revoke their active sessions and devices?

- **A.** Session lists are required before app stores approve any application with a login screen today
- **B.** It doubles as an analytics dashboard, showing which device types drive your engagement
- **C.** When users suspect compromise, they can see what's connected and cut intruders off directly  ✅
- **D.** It reduces support tickets about billing, since devices map directly onto seat pricing

> **Answer:** C

### Q13. Your app uses stateless tokens and a user reports a compromised account. What problem surfaces immediately?

- **A.** Issued tokens stay valid until they expire, so cutting the attacker off takes extra machinery  ✅
- **B.** Stateless tokens cannot be read by your own servers, so the account cannot be inspected
- **C.** The user's password hash must be deleted, which erases the account beyond any recovery
- **D.** Token signatures corrupt under suspicion, locking out the real user along with the attacker too

> **Answer:** A

### Q14. When does a managed auth provider beat building auth into your own backend?

- **A.** Never; serious products always own every layer of authentication without any exception
- **B.** When speed, breach liability, and features like SSO matter more than control and per-user cost  ✅
- **C.** Only for hobby projects, since managed providers cap accounts below commercial scale
- **D.** Whenever your AI recommends it, since agents always weigh these decisions correctly

> **Answer:** B

### Q15. Why should the session ID be regenerated at the moment of login?

- **A.** Fresh IDs compress better in transit, trimming a few bytes from every request afterward
- **B.** Browsers reject reused IDs after major updates, so regeneration prevents random logouts
- **C.** Regeneration resets the expiry clock, giving users the longest possible session window
- **D.** An ID that existed before login could have been planted; a fresh one can't be pre-known  ✅

> **Answer:** D

### Q16. Which auth events deserve logging from day one?

- **A.** Logins, failures, logouts, resets, and permission changes, with time, account, and source  ✅
- **B.** Only successful logins, since failures are noise that fills storage without any real insight
- **C.** Every keystroke on the login form, since full replay is what investigations require
- **D.** Nothing at first, since logging is a scale problem that small apps shouldn't pay for

> **Answer:** A

### Q17. Should one account hold multiple simultaneous sessions? What kind of decision is this?

- **A.** A performance decision; concurrent sessions multiply load, so the database sets the practical limit
- **B.** A legal decision; most jurisdictions require single-session enforcement for consumer apps
- **C.** A business decision: sharing, devices, and pricing shape it, and the app enforces the choice  ✅
- **D.** No decision at all; browsers already prevent one account from opening parallel sessions

> **Answer:** C

### Q18. Where must the "is this user logged in and allowed" check run?

- **A.** Once at the login screen, since everything past that door is by definition trusted space
- **B.** On the server for every protected request, since anything client-side can be bypassed  ✅
- **C.** In the mobile app only, since browsers enforce login state natively on the web side
- **D.** In a nightly batch job that reviews the day's requests and flags any that lacked auth

> **Answer:** B

### Q19. Your app uses cookie sessions. Why does your AI need to handle CSRF?

- **A.** CSRF is a cookie-size limit, and busy accounts overflow it without periodic manual trimming
- **B.** CSRF attacks only matter for banks, but handling it satisfies a compliance checkbox
- **C.** CSRF tokens speed up form rendering, which is why frameworks include them by default
- **D.** Browsers attach cookies automatically, so another site can trigger actions as the user  ✅

> **Answer:** D

### Q20. What does a real test plan for session handling include?

- **A.** Loading the login page one thousand times to prove the form renders at consistent speed every time
- **B.** A single happy-path test: log in, see the dashboard, and confirm the welcome message
- **C.** Expiry, logout, revoked sessions, tampered IDs, and reuse after password change, all tried  ✅
- **D.** Screenshots of each auth screen archived so future designers keep the layout consistent

> **Answer:** C

### Q21. Your app lets visitors start work before signing up. What must the design handle?

- **A.** Upgrading the anonymous state into a real account without losing what the visitor did  ✅
- **B.** Blocking anonymous users from seeing prices, since quotes require verified identities
- **C.** Deleting anonymous work nightly, since unowned data cannot legally persist past a day
- **D.** Issuing anonymous visitors admin rights temporarily so their trial feels fully featured

> **Answer:** A

### Q22. A user's session expires mid-task. What separates good handling from bad?

- **A.** Bad apps log the expiry; good apps extend sessions silently forever to avoid friction
- **B.** Good handling preserves their work and returns them to it after re-login, not a dead end  ✅
- **C.** Good apps expire sessions only at midnight, when users are least likely to be working
- **D.** The difference is cosmetic, since expiry behavior has no effect on how users judge apps overall

> **Answer:** B

### Q23. Before your AI writes any auth code, what should you direct it to produce?

- **A.** The marketing copy for the login page, since positioning decides the signup conversion rate
- **B.** A benchmark of competitors' login speeds, since auth performance is the differentiator
- **C.** A written map of the auth flows: signup, login, logout, reset, and expiry, decisions made  ✅
- **D.** The database purchase order, since auth capacity planning precedes any design work

> **Answer:** C

### Q24. Several employees share one login for the admin dashboard. What is the real problem?

- **A.** Shared logins double billing, since providers detect and charge for each distinct device used
- **B.** Sessions collide when shared, corrupting the dashboard data that both users are editing
- **C.** Nothing, as long as the password is strong and gets rotated on a quarterly schedule
- **D.** You lose accountability and clean offboarding: nobody can say who did what, or cut one out  ✅

> **Answer:** D

### Q25. Which principle should govern every auth architecture decision you direct?

- **A.** Auth is the front door: proven parts, sessions controlled server-side, revocation designed early  ✅
- **B.** Auth is friction: minimize every check, since each security step measurably costs signups
- **C.** Auth is a commodity: copy whatever the most recent tutorial recommends and move along
- **D.** Auth is invisible: as long as login works in the demo, the architecture underneath is fine

> **Answer:** A


---
_Take it in the browser: https://the-faction.mn.co/posts/105098293_
