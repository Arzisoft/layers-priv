---
course: "The Mastery"
module: "Module 5: Debugging and Error Resolution With Cursor"
lesson: "Module 5: Debugging and Error Resolution With Cursor — Exam"
type: "course_quiz"
post_id: 107131823
space_id: 24191170
source: "https://the-faction.mn.co/posts/107131823"
updated: "2026-09-10T20:09:08Z"
---

# Module 5: Debugging and Error Resolution With Cursor — Exam

> Exam for **Module 5: Debugging and Error Resolution With Cursor** (The Mastery) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. A builder tells the AI 'the signup page is broken' and gets a useless response. Per this module, what was missing from the input?

- **A.** The diagnosis package: the full error text, the stack trace, and what they were doing, since the AI diagnoses from what you give  ✅
- **B.** The project history, since debugging requires the complete Git log attached to every message before the AI can reason about breakage
- **C.** A screenshot of the code, since visual context is the primary diagnostic input and text descriptions of errors carry little signal
- **D.** An apology for the interruption, since abrupt error reports produce rushed diagnoses and framing improves the response quality

> **Answer:** A

### Q2. A builder pastes an error and immediately gets a code change back. This module says to insert a step before any fix. Which step, and why?

- **A.** Diagnosis first: ask for the most likely cause before changes, since a fix without a stated cause is a guess you cannot review  ✅
- **B.** A formatting pass, since clean code exposes bugs and most errors resolve themselves as soon as the file is formatted consistently
- **C.** A full backup, since debugging without a complete project copy risks losses that no amount of diagnosis can compensate for
- **D.** A restart of Cursor, since stale editor state causes most reported errors and restarting resolves them without any changes

> **Answer:** A

### Q3. A builder trims a long stack trace before pasting it, keeping only the parts they understand. What does this module say about that habit?

- **A.** It is correct, since irrelevant trace lines dilute the model's attention and curation is the builder's diagnostic contribution
- **B.** It deletes the diagnostic core: the part you would trim is often what names the actual file and line, so paste the full text  ✅
- **C.** It is required, since full stack traces exceed message limits and trimming is the only way to feed errors to the model at all
- **D.** It is harmless either way, since the model reconstructs missing trace lines from the codebase index during its diagnosis

> **Answer:** B

### Q4. This module describes debugging as a loop. Which sequence matches?

- **A.** Guess, change, hope, repeat, since debugging is inherently trial and error and any structure only slows the natural process down
- **B.** Delete, rebuild, test, ship, since removing the broken area and regenerating it beats diagnosing what went wrong inside it
- **C.** Run, capture the error, feed it with context, review the proposed fix, apply, run again, with each pass narrowing the problem  ✅
- **D.** Search the web, copy a fix, apply, move on, since most errors are already solved publicly and local diagnosis wastes effort

> **Answer:** C

### Q5. The AI's proposed fix references a function that does not exist anywhere in the builder's project. What signal is this, per this module?

- **A.** A wrong-suggestion signal: invented functions mean the suggestion should be treated as wrong until verified against the codebase  ✅
- **B.** A feature request, since referencing missing functions is how the AI proposes the new helpers it believes the project should add
- **C.** An index refresh cue, since nonexistent references mean the index is stale rather than the suggestion being wrong in itself
- **D.** A version mismatch, since the function exists in newer releases of Cursor and updating the editor resolves the reference

> **Answer:** A

### Q6. A fix fails, the builder replies 'still broken' with nothing else, and the AI proposes nearly the same fix again. What does this module say about the reply?

- **A.** It was too polite, since firm language is what breaks repetition loops and softened feedback invites the same fix again
- **B.** It was sent too fast, since models need idle time between attempts and rapid replies cause them to repeat prior output
- **C.** It added no information: when the loop stalls change the input, adding new error text and what you observed, not volume  ✅
- **D.** It was correct, and the repeated fix means the AI is confident, so the builder should apply it a second time as directed

> **Answer:** C

### Q7. Two fixes for the same error have failed. This module prescribes a specific stall-breaker. What does the builder direct?

- **A.** Apply both failed fixes together, since fixes that fail individually often succeed in combination and stacking is the next step
- **B.** Take a break and retry tomorrow, since stalls are fatigue phenomena and the same instruction succeeds when the builder is rested
- **C.** Escalate the model temperature, since stalls mean the model is being too conservative and more randomness unlocks new fixes
- **D.** State everything known, then ask for three different possible causes ranked by likelihood with a quick test for each, no repeats  ✅

> **Answer:** D

### Q8. A builder is five code changes deep into a login bug when someone notices the database was never running. Which module habit would have caught this earlier?

- **A.** Reading the code aloud, since verbalizing each function surfaces hidden assumptions including which services must be running
- **B.** Asking what non-code causes would produce this exact error, since the environment can be the bug and deserves early suspicion  ✅
- **C.** Switching to a stronger model, since environment detection is a capability frontier and better models notice missing services
- **D.** Committing between attempts, since Git history review is where environmental problems like stopped services get discovered

> **Answer:** B

### Q9. A builder asks for a fix and receives a forty-line refactor for a one-line error. Which instruction does this module teach to prevent this?

- **A.** A style directive: match my formatting exactly, since format constraints implicitly prevent structural refactors
- **B.** A length limit: keep all fixes under five lines, since correct fixes are always short and length signals wrongness
- **C.** A scope guard: fix only the one error listed, and do not refactor or improve anything else while you are in there  ✅
- **D.** A review request: explain the fix in detail first, since explanation requirements naturally shrink oversized changes

> **Answer:** C

### Q10. After a fix works, this module says the debugging is not quite done. What remains?

- **A.** Documenting the bug in a formal postmortem, since every resolved error requires a written report before work continues
- **B.** Testing around the fix, since fixes can break neighbors and verifying nearby behavior is part of resolving the error  ✅
- **C.** Reverting and reapplying the fix, since a fix that works twice from a clean state is the standard of proof for resolution
- **D.** Deleting the conversation, since resolved debugging context confuses future sessions and cleanup protects later work

> **Answer:** B

### Q11. A builder applies a fix, reruns, and gets a different error than before. How does this module frame that outcome?

- **A.** As a regression, since any new error means the fix made things worse and the correct response is an immediate rollback
- **B.** As a model failure, since competent fixes never surface new errors and a different message means the diagnosis was wrong
- **C.** As progress: a new error means the loop moved forward, and the builder feeds the new error into the next pass  ✅
- **D.** As noise, since consecutive errors are usually unrelated and the builder should rerun several times before reacting

> **Answer:** C

### Q12. This module lists signals that an AI suggestion is wrong. Which set matches the module?

- **A.** It addresses a different error than pasted, invents functions or settings, repeats a failed fix, or grows far beyond the error's scope  ✅
- **B.** Use of new libraries, any config changes, and multi-file fixes, since correct debugging never leaves the file where the error appeared
- **C.** Hedged language and low confidence phrasing, since a model that qualifies its suggestion is signaling the suggestion is wrong
- **D.** Long response time, short answers, and missing code comments, since presentation quality is the reliable proxy for correctness

> **Answer:** A

### Q13. Per this module, why does asking for the cause before the fix make the fix reviewable?

- **A.** The cause slows the model down, since extra reasoning steps reduce error rates regardless of whether anyone reads the cause
- **B.** Causes are shorter than fixes, since reviewing a one-sentence cause is faster than reviewing code and speed is exactly what review needs
- **C.** Stated causes are legally binding, since documented diagnosis shifts responsibility for wrong fixes onto the model provider
- **D.** A correct cause gives you something to check the fix against, since you can judge whether the change actually addresses that cause  ✅

> **Answer:** D

### Q14. A builder's error appears only in production, never locally. Per this module's decision framework, what comes before code changes?

- **A.** Rewriting the deploy pipeline, since production-only errors always trace to deployment scripts rather than configuration
- **B.** Adding logging to every function, since total visibility is the prerequisite for reasoning about environment differences
- **C.** Disabling production, since debugging must happen locally and taking the environment down forces the error to reproduce there
- **D.** An environment check, since an error appearing in only one environment points at configuration, services, or variables first  ✅

> **Answer:** D

### Q15. The module's real-world example resolves a production login failure in eleven minutes. What made the loop that fast?

- **A.** A stronger model tier, since the example's speed came from paying for priority processing during the production incident
- **B.** Information fed early: exact error, full package, diagnose first, and the environment asked before rewriting working code  ✅
- **C.** Luck in the first guess, since the example shows that fast debugging is mostly variance rather than a repeatable process
- **D.** Two builders working in parallel, since the example splits diagnosis and fixing across people to halve the resolution time

> **Answer:** B

### Q16. A builder cannot reproduce an error reliably and wants to start debugging anyway. What does this module say about reproduction?

- **A.** Reproduction is optional on small bugs, since simple errors can be diagnosed from memory of what the screen looked like
- **B.** Reproduction wastes a run, since deliberately triggering errors adds load and the first organic occurrence suffices
- **C.** Reproduction is the AI's job, since a good diagnosis package lets the model simulate the failure without another run
- **D.** Reproduce first: trigger the error on purpose so you know exactly what produces it before feeding anything to the AI  ✅

> **Answer:** D

### Q17. This module gives a template for feeding an error: 'I did X, expected Y, got this error.' What does each part contribute?

- **A.** Action, expectation, and evidence: together they show the gap between intended and actual behavior plus the exact failure  ✅
- **B.** Blame, context, and proof: the structure documents fault for later review while incidentally informing the diagnosis
- **C.** Politeness, clarity, and drama: the structure is rhetorical, easing the model into the problem before the technical payload
- **D.** Time, place, and manner: the structure is chronological so the model can replay the session from its own perspective

> **Answer:** A

### Q18. The error surfaces in the browser console, but the builder keeps pasting terminal output. What does this module say?

- **A.** Terminal output is always sufficient, since browser errors mirror into the terminal on any correctly configured project
- **B.** Capture from wherever the error actually surfaces, including browser consoles and screenshots of rendering issues  ✅
- **C.** Browser errors cannot be debugged in Cursor, since the editor only reasons about errors originating in its own terminal
- **D.** The builder should disable the browser console, since duplicate error sources confuse diagnosis more than they help it

> **Answer:** B

### Q19. A builder accepts fixes without reading them because 'the AI knows the codebase better.' Weeks later the project confuses them. What does this module call this?

- **A.** Unreviewable guesses stacking up into a codebase you no longer understand, the cost of accepting fixes with no stated cause  ✅
- **B.** Model trust calibration, since acceptance rates should rise as the AI proves itself and confusion is the temporary cost
- **C.** Efficient delegation, since builders direct outcomes and reading every fix is the manual habit this course exists to replace
- **D.** Version drift, since the confusion traces to Cursor updates changing generated style rather than to unreviewed acceptance

> **Answer:** A

### Q20. The AI's fix is in a module the builder does not understand at all. Per this module's decision framework, what does the builder direct?

- **A.** A different module, since fixes belong where the builder has expertise and unfamiliar code should be routed to teammates
- **B.** Automatic application, since review requires understanding and skipping review is the honest choice in unfamiliar territory
- **C.** A rewrite of the module into familiar patterns first, since translation into known style is the precondition for any review
- **D.** Explanation first, fix second, so the builder can review what they apply even in code they did not previously understand  ✅

> **Answer:** D

### Q21. This module says to run and verify inside Cursor rather than in a separate terminal app. Why?

- **A.** External terminals are unsupported, since Cursor blocks projects that have been touched by outside processes during a session
- **B.** The whole loop lives in one place: errors surface where the AI can get them, and new versions read terminal output directly  ✅
- **C.** Licensing requires it, since running project commands outside the editor violates the terms most AI providers attach to usage
- **D.** Performance doubles inside Cursor, since the integrated terminal executes commands faster than any standalone terminal can

> **Answer:** B

### Q22. A builder wants to verify a proposed cause before applying the fix. The module's production example shows the pattern. What was it?

- **A.** Asking how to verify, then running one terminal command that confirmed the missing environment variable before any fix  ✅
- **B.** Trusting the stated confidence score, since the model's own probability estimate is the fastest verification available
- **C.** Applying the fix to a copy, since duplicating the project and testing there is the only real verification of a cause
- **D.** Polling three different models, since agreement between independent models is the standard of proof for a diagnosis

> **Answer:** A

### Q23. What does this module say about builders who expect one-shot fixes on real bugs?

- **A.** They are right to expect it, since modern models resolve most real bugs in a single pass and loops are a legacy habit
- **B.** They should lower their standards permanently, since debugging is unpredictable and expectations of any kind cause frustration
- **C.** They should switch to manual debugging, since expectation mismatch signals the AI-directed approach is wrong for that builder
- **D.** They set themselves up to distrust a process that was working, since each pass narrows the problem and the loop is the method  ✅

> **Answer:** D

### Q24. A builder's fix keeps failing and they keep repeating the identical instruction louder. What does this module call this pattern?

- **A.** Persistence, which the module endorses, since determination across identical attempts is what eventually breaks a hard bug
- **B.** Escalation, which works when paired with capital letters, since emphasis changes how the model weighs repeated instructions
- **C.** Repeating the same failed loop: same input, same output, and the fix is adding information or reframing, never volume  ✅
- **D.** Iteration, which is the loop working as intended, since repeated identical passes are how the process narrows the problem

> **Answer:** C

### Q25. Looking across this whole module, what is the governing principle of debugging and error resolution with Cursor?

- **A.** Trust the AI's first suggestion completely, since second-guessing a model that has read the whole codebase wastes the advantage that directed debugging exists to provide
- **B.** Apply fixes as fast as possible and measure success by attempts per hour, since debugging is a numbers game where volume of changes beats quality of any single change
- **C.** Feed real information and demand clear reasoning: exact errors with context, causes before fixes, scoped changes, and a loop that adds information instead of repeating  ✅
- **D.** Avoid touching broken code until a human expert is available, since AI-directed debugging is for cosmetic issues rather than for errors that block real functionality

> **Answer:** C


---
_Take it in the browser: https://the-faction.mn.co/posts/107131823_
