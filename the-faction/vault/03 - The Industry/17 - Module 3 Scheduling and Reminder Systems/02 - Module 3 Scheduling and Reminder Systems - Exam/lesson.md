---
course: "The Industry"
module: "Module 3: Scheduling and Reminder Systems"
lesson: "Module 3: Scheduling and Reminder Systems — Exam"
type: "course_quiz"
post_id: 105096460
space_id: 24251863
source: "https://the-faction.mn.co/posts/105096460"
updated: "2026-08-10T18:15:43Z"
---

# Module 3: Scheduling and Reminder Systems — Exam

> Exam for **Module 3: Scheduling and Reminder Systems** (The Industry) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. A family medicine practice asks you to build online booking. The lead physician's week includes procedures, admin time, and hospital rounds. What do you model first?

- **A.** The provider's weekly template, encoding visit types, durations, buffers, and blocked time before booking opens.  ✅
- **B.** The patient demand curve from last year, so the busiest request windows determine which open hours patients see.
- **C.** The clinic's phone volume by hour, since the busiest call times reveal when patients most want appointments.
- **D.** The physician's stated preferred hours, since provider preference is what ultimately governs any published schedule.

> **Answer:** A

### Q2. An orthopedic group wants patients to self-book. Surgical consults need 45 minutes and cast checks need 10. How do you direct AI to handle this?

- **A.** Define distinct appointment types with set durations, letting the chosen type determine which slots the patient sees.  ✅
- **B.** Offer uniform 30 minute slots for every visit so the calendar stays simple and providers average out across the day.
- **C.** Let patients pick any open time and have the front desk adjust the duration manually when reviewing each booking.
- **D.** Ask patients to estimate how long they need, since they know their situation better than a preset type list would.

> **Answer:** A

### Q3. A dermatology practice complains that back-to-back bookings leave no time for charting, and providers run late by noon. Which scheduling element addresses this directly?

- **A.** A stricter no-show fee policy so patients arrive promptly and the morning schedule stops slipping into the afternoon.
- **B.** Shorter appointment durations across all visit types, freeing minutes the providers can then use for their charting.
- **C.** An SMS reminder sequence telling patients to arrive fifteen minutes early so intake never delays the provider.
- **D.** Buffer time built into the template between appointments so documentation and turnover are protected by design.  ✅

> **Answer:** D

### Q4. A pediatrician does hospital rounds Tuesday mornings and takes lunch at noon daily. A patient books a 12:15 slot online. What went wrong in the build?

- **A.** The reminder system failed to warn the patient that the provider is typically unavailable during the midday hour.
- **B.** The waitlist claim window ran too long, letting a patient take a slot the front desk meant to reserve.
- **C.** Lunch holds and rounds were never encoded as blocks, so booking logic treated raw open calendar time as bookable.  ✅
- **D.** The PMS calendar sync lagged, so the online tool displayed a slot the front desk had already given away by phone.

> **Answer:** C

### Q5. You are designing a patient-facing booking flow for a multi-specialty group. What should the flow ask before showing any available times?

- **A.** The visit type, because it determines the slot length, the right provider, and sometimes which location applies.  ✅
- **B.** The patient's preferred day and time, since convenience is the strongest driver of whether they actually show up.
- **C.** Insurance details, because eligibility problems cause more lost revenue than any scheduling mistake ever could.
- **D.** The patient's preferred provider, since continuity of care matters more than the stated reason for the visit.

> **Answer:** A

### Q6. A family practice lets a new patient self-book into a 15 minute follow-up slot. The visit needs an hour and the day collapses. Which design rule was violated?

- **A.** Buffers between appointments were too short to absorb the overrun, so one long visit cascaded through the day.
- **B.** New patients should be booked by phone only, since self-service booking cannot handle first-visit complexity.
- **C.** Visit type must be captured first so duration rules assign the right slot length before times are displayed.  ✅
- **D.** The confirmation touch should have asked the patient to verify how much time they expected the visit to take.

> **Answer:** C

### Q7. Dr. Alvarez works the north office on Thursdays and the main office on other weekdays. Your scheduler double-books her across town. What was missing?

- **A.** A confirmation call step for cross-town appointments so the front desk can catch conflicts before they finalize.
- **B.** A longer buffer between appointments giving the provider enough drive time between the two office locations.
- **C.** A waitlist at each office so a conflicting booking can be released and instantly refilled by the next patient.
- **D.** Location-aware availability rules that tie her bookable hours at each office to the days she is actually there.  ✅

> **Answer:** D

### Q8. A five-provider OB/GYN group shares one custom scheduler. Two schedulers at different desks book the same provider for the same hour. What prevents this?

- **A.** A policy assigning each desk specific providers, so no two staff members ever schedule the same physician's day.
- **B.** A morning huddle where staff compare calendars and resolve any overlapping bookings before the patients arrive.
- **C.** Read-only calendar views for all but one senior scheduler, who alone commits every single booking into the system.
- **D.** A single availability source that locks each slot at booking so a taken hour can never be offered a second time.  ✅

> **Answer:** D

### Q9. The front desk at a two-location pediatric group toggles between separate calendars per office and misses conflicts. What do you direct AI to build?

- **A.** An alert digest emailed each evening listing the next day's overlaps so the manager can fix them by phone.
- **B.** A color coding standard for the two existing calendars so staff can spot a provider booked in both places faster.
- **C.** One combined view of every provider across both locations, each provider's day shown once regardless of office.  ✅
- **D.** A rule that each location books only its own providers, removing any need for staff to look across the offices.

> **Answer:** C

### Q10. A primary care clinic sends one email reminder a week ahead and no-shows hold at 14 percent. What reminder sequence do you propose instead?

- **A.** Two additional emails in the final week, since more repetitions of the same message steadily build patient recall.
- **B.** Confirmation at booking, a reminder days ahead, and a final touch the day before, with one asking for a reply.  ✅
- **C.** A single phone call the morning of the visit, since live conversation outperforms any automated message channel.
- **D.** Daily SMS messages for the full week before the visit so the appointment stays at the top of the patient's mind.

> **Answer:** B

### Q11. A dermatology client asks when the final reminder touch should land for maximum no-show impact. What do you recommend?

- **A.** A full week ahead, giving patients the maximum runway to rearrange work and childcare around the appointment.
- **B.** The day before or morning of the visit, close enough to act on but with time to refill the slot if they cancel.  ✅
- **C.** Exactly one hour before the visit, when the appointment is most immediate and the message cannot be forgotten.
- **D.** At booking only, because patients who truly intend to come will remember without any additional prompting later.

> **Answer:** B

### Q12. You are choosing channels for a reminder sequence at a busy family practice. Budget covers one primary channel. Which do you prioritize and why?

- **A.** Email, because it carries full visit details, maps, and attachments that a short text message could never include.
- **B.** Phone calls, because a human voice conveys that the practice is serious about attendance in a way texts cannot.
- **C.** SMS, because it outperforms email on response and a reply-to-confirm touch depends on patients answering.  ✅
- **D.** Portal notifications, because they keep all communication inside the system the practice already owns and runs.

> **Answer:** C

### Q13. A practice's reminders are being read but no-shows barely move. Reviewing the messages, you see they only state the date and time. What is the highest-impact addition?

- **A.** The provider's name and photo, since personalization research shows attendance builds on personal connection.
- **B.** The practice's cancellation fee policy, so patients clearly understand the financial consequence of not appearing.
- **C.** A confirm action and a one-tap reschedule link, so every reminder gives the patient a way to act, not just read.  ✅
- **D.** Driving directions and parking details, since arrival friction is a leading hidden cause of missed appointments.

> **Answer:** C

### Q14. A four-provider group wants to get serious about no-shows but has no data. What tracking foundation do you direct AI to build first?

- **A.** A practice-wide monthly no-show percentage, one clean number leadership can watch trend on a simple dashboard.
- **B.** A list of patients who missed their most recent visit, refreshed weekly for the front desk to follow up with.
- **C.** Anonymous aggregate counts only, since storing per-patient attendance history creates avoidable privacy exposure.
- **D.** No-show history recorded per patient and per appointment type, so patterns and rates become visible and usable.  ✅

> **Answer:** D

### Q15. A pediatric practice with a 12 percent no-show rate asks which defense to deploy first. How do you order the stack?

- **A.** Fees first, since a financial deterrent changes behavior faster than any messaging or workflow improvement can.
- **B.** Reminder sequences first, then easy self-rescheduling, then waitlist backfill, then flags on repeat no-shows.  ✅
- **C.** Waitlist backfill first, since recovered slots offset the losses even if patient behavior never changes at all.
- **D.** Repeat offender flags first, because a small group of patients typically drives most of the missed visits.

> **Answer:** B

### Q16. You built no-show risk scoring from appointment history for an internal medicine group. The manager asks what the tool should do when a patient scores high. What is your answer?

- **A.** Automatically cancel and refill high risk bookings from the waitlist so the slot is protected before it is lost.
- **B.** Apply whatever response the practice sets as policy, such as a confirmation call. The tool predicts, not decides.  ✅
- **C.** Quietly double-book those slots so that a likely absence is covered, following the standard airline overbooking approach.
- **D.** Charge a deposit at booking for high scores, applied by the tool automatically so staff never have to intervene.

> **Answer:** B

### Q17. An orthopedic practice finds a small set of patients with three or more no-shows each this year. Within a stacked defense approach, how are these patients handled?

- **A.** Flag them so their bookings trigger the practice's chosen step, such as a live confirmation call before the visit.  ✅
- **B.** Remove them from self-service booking entirely, since online access is a privilege that repeat absence forfeits.
- **C.** Move their appointments to the last slot of the day so any absence damages the schedule as little as possible.
- **D.** Send them the standard sequence like everyone else, since singling patients out risks the care relationship.

> **Answer:** A

### Q18. A cancellation comes in at 2 pm for tomorrow's 9 am slot at a dermatology office. In a well-built waitlist workflow, what happens next?

- **A.** The system automatically offers the slot to waitlisted patients in order, with a short window to claim it.  ✅
- **B.** The front desk gets a task to call down the waitlist, since a personal call converts better than any message.
- **C.** The slot returns to the public booking page, where demand from all patients gives it the best odds of filling.
- **D.** The slot holds open for provider catch-up time, since an unplanned gap is a chance to cut charting backlog.

> **Answer:** A

### Q19. Your waitlist offer gives patients 24 hours to claim a cancelled slot, and same-week openings keep expiring unclaimed and unfilled. What is the design fix?

- **A.** Lengthen the window to 48 hours so patients have enough time to check their calendars before they commit.
- **B.** Shorten the claim window so the offer moves quickly down the list before the appointment time arrives.  ✅
- **C.** Skip the waitlist for same-week openings and rely on the public booking page, where demand is broadest.
- **D.** Require a deposit when patients join the waitlist so only serious patients ever receive the slot offers.

> **Answer:** B

### Q20. A family practice's front desk spends hours daily on reschedule calls, and some patients skip visits rather than call. What do you build?

- **A.** A self-service reschedule link in every reminder that lets patients move a visit into valid open slots, no call.  ✅
- **B.** An after-hours voicemail line dedicated to reschedules, transcribed by AI each morning for the front desk queue.
- **C.** A policy that all reschedules require 48 hours of notice, cutting volume by making late changes harder to request.
- **D.** More phone lines with a call-back option, so the existing reschedule workflow scales without process changes.

> **Answer:** A

### Q21. In a scheduling build review, you notice cancelling takes one tap but rescheduling requires logging into a portal. Why is this a revenue problem?

- **A.** The path of least resistance becomes cancelling or not showing up, when an easy reschedule would keep the visit.  ✅
- **B.** Portal logins create support tickets, and support time costs the practice more than an occasional missed visit.
- **C.** Patients who cancel easily flood the waitlist system with churn that staff must then manage by hand each day.
- **D.** The imbalance violates patient communication rules requiring equal effort for all appointment change actions.

> **Answer:** A

### Q22. A practice on a PMS with a capable built-in scheduler asks you for a fully custom booking system. What is the right builder move?

- **A.** Build the full custom system anyway, since owning every layer gives the practice control and you more value.
- **B.** Learn what the PMS scheduler already does and build only what it lacks, extending instead of duplicating it.  ✅
- **C.** Decline the project, since custom work alongside an existing PMS scheduler creates unmanageable data overlap.
- **D.** Replace the PMS scheduler outright so the practice runs one modern system instead of a patchwork of tools.

> **Answer:** B

### Q23. Two weeks after launch, a practice's custom scheduler and PMS calendar show different bookings for the same hour, and staff have gone back to the phones. What core failure occurred?

- **A.** The reminder sequence was never connected to the PMS, so confirmations failed to update either calendar system.
- **B.** Staff were undertrained on the custom tool, and a refresher session would restore their confidence in using it.
- **C.** The build created a second source of truth instead of syncing two ways with the calendar providers check.  ✅
- **D.** The waitlist claim window overlapped with live bookings, letting two patients hold one appointment at once.

> **Answer:** C

### Q24. A frustrated practice owner wants to lead with a 50 dollar no-show fee. Current reminders are a single email and rescheduling requires a phone call. What do you advise?

- **A.** Support the fee, since revenue protection policy is the practice's call and your tools enforce what it sets.
- **B.** Propose a larger fee applied only to repeat offenders, concentrating the deterrent where the behavior lives.
- **C.** Suggest deposits at booking instead of fees after the fact, since prepayment prevents rather than punishes.
- **D.** Fix reminders and rescheduling friction first, since fees punish patients for a workflow the practice controls.  ✅

> **Answer:** D

### Q25. Across every scheduling and reminder decision in this module, what governing principle should drive your builds for practice clients?

- **A.** Automation should replace front desk staff wherever possible, since labor is the largest scheduling cost center.
- **B.** Patient convenience outranks provider preferences, since patients who cannot book easily simply go elsewhere.
- **C.** Every scheduling feature belongs in the custom build, since control over the stack is what clients pay for.
- **D.** The schedule is the revenue engine: protect filled slots with prevention over punishment and one source of truth.  ✅

> **Answer:** D


---
_Take it in the browser: https://the-faction.mn.co/posts/105096460_
