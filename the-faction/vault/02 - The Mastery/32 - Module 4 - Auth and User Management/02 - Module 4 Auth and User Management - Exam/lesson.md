---
course: "The Mastery"
module: "Module 4 — Auth and User Management"
lesson: "Module 4: Auth and User Management — Exam"
type: "course_quiz"
post_id: 106187567
space_id: 24191170
source: "https://the-faction.mn.co/posts/106187567"
updated: "2026-08-21T15:20:06Z"
---

# Module 4: Auth and User Management — Exam

> Exam for **Module 4 — Auth and User Management** (The Mastery) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. Your AI-built client portal works locally, but production magic link emails send users to localhost:3000 and fail. What is the most likely cause?

- **A.** The magic link tokens are expiring before users click them, so Supabase falls back to the default local development redirect.
- **B.** The production build was deployed without the Supabase anon key, so the client library defaults every redirect to localhost.
- **C.** The email template still contains a hardcoded development URL that the AI forgot to swap out during the production build.
- **D.** The project's Site URL in the Supabase dashboard is still set to localhost, so every emailed link points at the dev machine.  ✅

> **Answer:** D

### Q2. Reviewing an AI build, you see the app querying auth.users directly for display names and avatars. What should you direct the AI to do instead?

- **A.** Expose the auth schema to the API so the app can read auth.users safely, and add an RLS policy restricting rows per user.
- **B.** Create a public profiles table whose id references auth.users, auto-populated by a signup trigger, and query that instead.  ✅
- **C.** Copy the needed columns from auth.users into user_metadata on signup so the client can read them from the session object.
- **D.** Add a database view over auth.users with only safe columns, and grant the anon role select access so the existing queries keep working.

> **Answer:** B

### Q3. Your AI creates profile rows from the frontend after signup succeeds. A tester closes the tab mid-signup and later logins crash on a missing profile. What is the right fix?

- **A.** Add a retry loop in the frontend that checks for the profile row on every login and recreates it automatically whenever it is missing.
- **B.** Move profile creation into a Postgres function and trigger on auth.users, so every signup path creates the row atomically.  ✅
- **C.** Wrap the signup call and profile insert in a single client-side transaction so both succeed or both roll back together.
- **D.** Delay profile creation until the user first edits their profile, so no row exists until there is real data to store there.

> **Answer:** B

### Q4. An AI-built SaaS stores each user's role as admin or member in user_metadata. Why must you reject this before shipping?

- **A.** user_metadata is wiped whenever the access token refreshes, so roles would silently disappear from active sessions hourly.
- **B.** user_metadata is only readable server side, so client components could never render role-based navigation without extra calls.
- **C.** user_metadata lives in the auth schema, so RLS policies in the public schema have no way to reference it in a policy check.
- **D.** Users can update their own user_metadata, so any curious user could edit their role to admin and escalate privileges.  ✅

> **Answer:** D

### Q5. Client portal users who leave a tab open overnight return to a blank page and console errors. Which behavior should you require the AI to implement?

- **A.** Extend the access token lifetime in the dashboard to thirty days so sessions rarely expire while a portal tab stays open overnight.
- **B.** Store the user's password encrypted in localStorage so the app can silently sign the user back in when a token expires.
- **C.** Show a modal warning fifteen minutes before expiry and log the user out immediately if they do not click to acknowledge.
- **D.** Attempt a token refresh, and when refresh fails, redirect to the login page gracefully instead of crashing or going blank.  ✅

> **Answer:** D

### Q6. You direct AI to add Google login. It sets the client ID and secret in Supabase, but Google returns a redirect_uri_mismatch error. What did the setup miss?

- **A.** Registering Supabase's callback URL in the Google OAuth app's settings, since providers only redirect to URLs they know.  ✅
- **B.** Enabling the Google provider toggle in the Supabase dashboard, which stays off until the first successful test login runs.
- **C.** Adding Google's token endpoint to the Supabase redirect allow list so the two services can exchange codes securely.
- **D.** Generating a services ID and signed key, which Google requires before any OAuth app can complete the consent screen.

> **Answer:** A

### Q7. An AI-built dashboard hides the admin link for non-admin users, but typing the admin URL directly loads the page fully. What is the core problem?

- **A.** The admin route is missing from the redirect allow list, so Supabase cannot intercept direct navigation to the page itself.
- **B.** Access is enforced only in the UI; the route never validates the session server side, so anyone with the URL reaches it.  ✅
- **C.** The session cookie is not marked httpOnly, letting the browser reuse it for routes the UI had intended to keep hidden.
- **D.** The refresh token grants broader access than the access token, so a refreshed session bypasses the client-side check.

> **Answer:** B

### Q8. A user reports that clicking a password reset email a second time shows a cryptic error page. What should the AI-built flow do with an expired or already used reset link?

- **A.** Silently issue a fresh reset token and continue, since Supabase can safely re-verify the user from the original email link.
- **B.** Log the user in anyway with a temporary session, then force a password change on the first protected route they visit.
- **C.** Detect the invalid link, explain that it has expired or been used already, and offer to send the user a fresh reset email.  ✅
- **D.** Redirect the user to signup, because a consumed reset token means the account's state can no longer be trusted safely.

> **Answer:** C

### Q9. You are building a private client portal for a handful of nontechnical clients who hate passwords. Which Supabase auth approach best fits, per the module?

- **A.** Google OAuth only, since every client already has a Google account and social login removes all the provider configuration work.
- **B.** Email and password with mandatory resets each month, because rotating credentials keeps a small portal properly secure.
- **C.** Anonymous sign-ins gated by a shared portal PIN, keeping friction near zero for a small trusted group of paying clients.
- **D.** Magic links, since clients just click an emailed link to sign in and still receive a standard session with a JWT inside.  ✅

> **Answer:** D

### Q10. Auth works in production, but on preview deploys every OAuth login bounces back with an error. What should you check first?

- **A.** Whether the preview deploy URLs are on the Supabase redirect allow list, since Supabase only redirects to listed URLs.  ✅
- **B.** Whether the preview build uses the service role key, which OAuth callbacks require to exchange the authorization code.
- **C.** Whether the host is stripping auth cookies on preview domains, which blocks Supabase from completing the callback flow.
- **D.** Whether the provider secret was rotated, since preview environments always invalidate any stored OAuth client secrets.

> **Answer:** A

### Q11. Your AI explains that Supabase sessions never expire because tokens renew themselves. Which description of sessions is actually correct?

- **A.** A session is one long-lived JWT that stays valid until the user signs out, so no renewal mechanism is ever involved.
- **B.** A session pairs a short-lived access token with a refresh token that quietly obtains new access tokens as they expire.  ✅
- **C.** A session is a server-side record only; the browser holds a random cookie ID and no tokens ever reach the client at all.
- **D.** A session is re-created on every request by re-verifying the password hash, which is why login feels instant afterward.

> **Answer:** B

### Q12. An AI-generated report screen joins directly against auth.users to list emails. Why does the module say never to query auth.users from your app?

- **A.** The auth schema is not exposed to your API by design; bypassing that breaks on upgrades and can leak private fields.  ✅
- **B.** auth.users rows are encrypted at rest with the service key, so app queries would return unreadable ciphertext columns.
- **C.** Queries against auth.users bypass connection pooling, so even light traffic would exhaust the database connections.
- **D.** Supabase rate limits the auth schema to ten reads per minute, so any real report screen would immediately throttle.

> **Answer:** A

### Q13. You add Google and GitHub login easily, but the AI stalls configuring Sign in with Apple. Per the module, what extra pieces does Apple require?

- **A.** A verified custom email domain, because Apple refuses to send its private relay addresses to default Supabase domains.
- **B.** A paid Supabase plan, since Apple login is gated behind projects that support custom OAuth token lifetime settings.
- **C.** An extra redirect entry per Apple device type, because iOS, iPadOS, and macOS each use distinct callback URL formats.
- **D.** A services ID and a signed key on top of the usual OAuth setup, more than Google or GitHub configuration requires.  ✅

> **Answer:** D

### Q14. During review you notice AI-built signup lets users reach protected routes before confirming their email. Why does the module treat this as a real risk?

- **A.** Unverified accounts cannot receive refresh tokens, so their sessions crash unpredictably once the access token expires.
- **B.** An auth layer that accepts unverified emails undermines everything built on it; the RLS policies then stand on sand.  ✅
- **C.** Supabase deletes unverified users after 24 hours, so their profile rows become orphans that break profile lookups later.
- **D.** Email providers flag apps that skip verification, landing every future magic link and reset email in spam folders.

> **Answer:** B

### Q15. Your AI writes a profiles trigger on auth.users, but signups start failing with a permission error when the function inserts into public.profiles. What should you confirm?

- **A.** That the trigger fires after update instead of after insert, since Supabase finalizes new users through an update step.
- **B.** That the anon role has insert rights on profiles, because signup runs as the anonymous role until a session is issued.
- **C.** That the function is declared security definer, so it has the rights it needs to write into the public schema on signup.  ✅
- **D.** That RLS is disabled on auth.users, because triggers cannot fire on tables that have row level security enforced on them.

> **Answer:** C

### Q16. After you reject roles in user_metadata, your AI asks where tenant IDs and roles should live instead. Per the module, which placement is right?

- **A.** In app_metadata or a profiles column, since only the service role can change app_metadata and RLS governs profiles.  ✅
- **B.** In a signed cookie issued at login, so role data lives client side but cannot be modified without the signing secret.
- **C.** In localStorage keyed by user ID, refreshed on every login so the client always holds the latest role assignments.
- **D.** In JWT custom claims set at signup by the client library, since claims stay immutable for the token's whole lifetime.

> **Answer:** A

### Q17. A tester clicks Continue with GitHub, then cancels on the consent screen and lands on a broken page of your app. What should you direct the AI to handle?

- **A.** Retry the OAuth flow automatically up to three times, since most consent screen cancellations are accidental misclicks.
- **B.** Clear all Supabase cookies and force a full page reload, because a cancelled consent leaves the session half opened.
- **C.** Fall back to signing the user in with an anonymous session so they can browse until they finish connecting GitHub.
- **D.** Detect the provider error or cancellation on the callback and return the user to login with a clear message shown.  ✅

> **Answer:** D

### Q18. Your AI demos a flawless signup and login, then declares auth done. Per the module, why is this demo not enough to ship?

- **A.** Demos run against the local emulator, which uses a different token format than production Supabase Auth would actually issue.
- **B.** AI-built demos disable email confirmation by default, so the happy path shown never actually exercised real auth.
- **C.** AI-built auth handles the happy path; the failures live in expired sessions, unverified emails, and broken reset links.  ✅
- **D.** Signups in a demo bypass the profiles trigger, so the flow proves nothing about the production database schema.

> **Answer:** C

### Q19. Reviewing AI code, you see supabase.auth.loginWithEmailLink() and sendPasswordReset(). Why does the module say to learn the real supabase-js method names?

- **A.** Deprecated method names still compile but silently skip the redirect allow list, creating a security gap in production.
- **B.** Knowing real names like signInWithOAuth and resetPasswordForEmail lets you spot methods the AI invented before you ship.  ✅
- **C.** Method names determine which RLS policies apply to the request, so wrong names can bypass row level security checks.
- **D.** supabase-js maps each method to a dashboard toggle, so invented method names silently disable the matching provider.

> **Answer:** B

### Q20. Your AI says it fixed the auth config in code, but users still get the old confirmation template and wrong session expiry. What does the module remind you of here?

- **A.** Email templates are cached by Supabase for 24 hours, so template fixes always lag one full day behind the deploy.
- **B.** Template changes require re-verifying your sending domain, and pending verification keeps the old template live.
- **C.** Dashboard auth settings like templates, Site URL, and expiry are never touched by code changes; review them yourself.  ✅
- **D.** The AI must be given the service role key before it can edit templates, so the fix silently failed without any errors.

> **Answer:** C

### Q21. A user signs up with an email that already has an account, and the AI-built flow surfaces a raw 422 error. What behavior should you require instead?

- **A.** Handle the duplicate cleanly: tell the user an account may exist and point them to login or a password reset instead.  ✅
- **B.** Automatically merge the two accounts by matching email, keeping the newer password and both metadata blobs intact.
- **C.** Delete the older account after a grace period, since a fresh signup signals the user lost access to the original one.
- **D.** Suppress the error entirely and show the generic signup success screen so nothing about existing accounts is revealed.

> **Answer:** A

### Q22. Your mobile app's magic links open the phone browser and die there, never returning users to the app. Per the module, what does the redirect setup need?

- **A.** A universal Site URL pointing at the app store listing, so Supabase can route users to install or open the app itself.
- **B.** A separate Supabase project per platform, since one redirect allow list cannot mix web URLs with app link schemes.
- **C.** The app's deep link added to the redirect allow list, since Supabase only redirects to URLs you have explicitly listed.  ✅
- **D.** An Edge Function that intercepts the email links and rewrites them into platform push notifications for the app.

> **Answer:** C

### Q23. A teammate asks why the auth module matters when Module 3's RLS already locks down the data. What is the module's answer?

- **A.** Every RLS policy keys off auth.uid(), so if the auth layer accepts bad signups those policies stand on weak ground.  ✅
- **B.** RLS only applies to authenticated roles, so auth exists mainly to route users into the role RLS expects to observe.
- **C.** RLS protects reads but not writes, so auth is the layer that stops unauthorized inserts and updates from landing.
- **D.** Auth replaces RLS in production, since checking sessions per route is faster than evaluating policies for each row.

> **Answer:** A

### Q24. A user requests a password reset on a laptop but opens the email on a phone, and the flow fails confusingly. Why does the module put this on the audit checklist?

- **A.** Reset tokens are bound to the requesting device's IP address, so any cross-device open is rejected by Supabase itself.
- **B.** Password resets require the original session cookie, and the module says to sync it across devices via deep links.
- **C.** Opening a reset link in a different browser is a real edge case your audit must cover, not an unsupported user error.  ✅
- **D.** Mobile email clients strip query tokens from links, so resets can only ever be completed inside desktop browsers.

> **Answer:** C

### Q25. Which statement best captures the governing principle of Module 4, Auth and User Management?

- **A.** AI can scaffold an auth flow in minutes, but you supervise it: demand the edge cases and refuse to ship until they hold.  ✅
- **B.** Auth is a solved problem in Supabase, so the builder's job is mostly deciding which providers to switch on for users.
- **C.** Auth belongs entirely in the dashboard; the less auth code your AI writes, the more secure the application becomes.
- **D.** The goal is passwordless everywhere: magic links and OAuth should fully replace passwords in production applications.

> **Answer:** A


---
_Take it in the browser: https://the-faction.mn.co/posts/106187567_
