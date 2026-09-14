---
course: "The Mastery"
module: "Module 3: Multi-File Editing and Codebase Navigation"
lesson: "Module 3: Multi-File Editing and Codebase Navigation — Exam"
type: "course_quiz"
post_id: 107131820
space_id: 24191170
source: "https://the-faction.mn.co/posts/107131820"
updated: "2026-09-10T20:06:15Z"
---

# Module 3: Multi-File Editing and Codebase Navigation — Exam

> Exam for **Module 3: Multi-File Editing and Codebase Navigation** (The Mastery) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. A builder says 'add this to the checkout flow' without naming any files, and the AI finds the right code anyway. What made that possible?

- **A.** Conversation memory, since the AI recalls every file from earlier sessions and no longer ever needs the project to be searchable at all
- **B.** The codebase index, which gives the AI a searchable map of the project so instructions can pull in relevant code the AI finds itself  ✅
- **C.** Filename guessing, since models are trained to predict common project layouts and simply assume where a checkout flow would live
- **D.** The terminal history, since previously run commands reveal the project structure and the AI reconstructs the layout from them

> **Answer:** B

### Q2. A builder writes 'update the cart file like the checkout one' in a project with several similarly named files. What does this module predict, and what is the fix?

- **A.** The AI will ask which files are meant, so vague descriptions are safe because clarifying questions always precede any editing
- **B.** The AI must guess which files are meant; the fix is explicit references, like updating @cart.js to match @checkout.js handling  ✅
- **C.** The AI will update every file containing the word cart, which is the intended behavior for builders working across many files
- **D.** The AI will refuse the instruction entirely, since Cursor blocks any request that does not contain at least one explicit reference

> **Answer:** B

### Q3. A builder changes a form field name but forgets the API expects the old name. The form works; submissions fail. What concept from this module did they miss?

- **A.** Blast radius: a change crossing contracts has more than one side, and AI edits only what it sees, so all of it must be in view  ✅
- **B.** The review order, since diffs must be read starting from the API side and reading the form first is what caused the breakage
- **C.** The index refresh, since renamed fields require rebuilding the codebase index before the API can recognize the new field name
- **D.** The mode split, since renames belong in Chat rather than Composer and using the changing mode is what broke the submission path

> **Answer:** A

### Q4. In a large unfamiliar project, a builder needs to add a log entry where orders are created but has no idea where that happens. Which pattern does this module teach?

- **A.** Open files alphabetically until the code appears, since systematic manual reading is the only reliable discovery method available
- **B.** Add the log entry to every file mentioning orders, since broad application guarantees the right location is covered somewhere
- **C.** Direct discovery first: have the AI search the codebase and report where orders get created before it edits anything at all  ✅
- **D.** Ask another builder who knows the project, since AI discovery is unreliable on codebases the current builder has never read

> **Answer:** C

### Q5. This module says multi-file output arrives as a set of diffs. What review discipline does it require?

- **A.** Read each diff file by file, since consistency errors hide in the file you skip, and use per-file accept and reject controls  ✅
- **B.** Read only the largest diff, since the biggest change carries the most risk and small diffs are safe to accept without reading
- **C.** Accept all diffs then review afterward in Git, since post-acceptance review is equivalent and keeps the workflow moving faster
- **D.** Reject all diffs on the first pass by policy, since a second identical proposal confirms the AI is confident in the changes

> **Answer:** A

### Q6. After accepting a multi-file change, everything works file by file, but the app breaks where the changed files interact. What does this module call the failure zone, and what is the practice?

- **A.** Seams: after accepting, run the app and exercise where the changed files meet, since that is where multi-file edits fail  ✅
- **B.** The index gap: rebuild the codebase index after every multi-file change so interacting files can find each other again
- **C.** The merge zone: multi-file edits must be applied one file per day so interactions surface gradually instead of all at once
- **D.** The cache layer: interacting files fail because of stale caches, so clearing caches after acceptance is the standard practice

> **Answer:** A

### Q7. A builder inherits a 200-file client app with no documentation. What does this module recommend as the day-one move?

- **A.** Rewrite the smallest module first, since replacing code area by area is how a builder converts an unknown project into a known one
- **B.** Print the file tree and study it offline, since structure comprehension must happen away from the editor before any AI involvement
- **C.** Direct the AI to map the codebase: main areas, framework, conventions, and where authentication happens, replacing a week of reading  ✅
- **D.** Ask the client for a walkthrough call, since only the original owners can explain a codebase and AI mapping cannot substitute for it

> **Answer:** C

### Q8. A builder wants to rename a field everywhere it appears: model, API, and every displaying component. Which instruction element does this module add to make the sweep verifiable?

- **A.** A politeness clause, since sweeping changes are risky and respectful framing measurably reduces the error rate of large edits
- **B.** A time limit, since bounded thinking time forces the AI to prioritize the most important occurrences of the renamed field first
- **C.** A file count cap, since limiting the sweep to five files keeps the change reviewable even if some occurrences are left behind
- **D.** A reporting requirement: list the files you changed, so the builder can check the sweep's actual coverage against expectations  ✅

> **Answer:** D

### Q9. This module warns that in long sessions the model's view of files drifts. What is the recommended habit?

- **A.** Paste every file into every message, since complete repetition is the only defense against drift on projects of any real size
- **B.** Restart Cursor every hour, since application restarts are the only way to refresh what the model believes about your files
- **C.** Keep sessions under ten messages, since model drift begins at message eleven and no reference pattern at all can prevent it after that
- **D.** Re-reference files rather than assuming the model still sees them accurately, since trusting memory over the index causes stale edits  ✅

> **Answer:** D

### Q10. A builder plans to change a form component, an API route, and a validation module together. How does this module say to phrase the instruction?

- **A.** Describe only the form change and let the AI infer the rest, since over-specifying related files causes redundant duplicate edits
- **B.** Send three separate one-file instructions in three conversations, since related changes must be isolated to stay reviewable
- **C.** State the radius explicitly: this change affects these three files, update all three consistently, so the whole radius is in view  ✅
- **D.** Ask the AI to choose which files matter, since delegating scope decisions produces better radii than builder-stated ones

> **Answer:** C

### Q11. A builder asks what the @ symbol accomplishes in a Cursor message. What does this module say?

- **A.** It marks text as private, since @-prefixed content is excluded from the model's context for confidentiality during the session
- **B.** It triggers a web search, since @ tells Cursor the reference lives outside the project and must be fetched from documentation
- **C.** It mentions teammates, since @ notifies collaborators that a change affects them, the same way it works in chat applications
- **D.** It references files, folders, and symbols directly, making instructions precise instead of forcing the model to guess which files you mean  ✅

> **Answer:** D

### Q12. A builder wants a new settings page that fits the project's existing patterns. Which pattern-anchoring instruction matches this module?

- **A.** Add a settings page using current industry best practices, since external standards produce more maintainable pages than internal ones
- **B.** Add a settings page however you think is best, since the AI's judgment about structure exceeds any existing pattern in the project
- **C.** Add a settings page copied from a popular open source project, since proven external code beats patterns invented inside this codebase
- **D.** Add a settings page following the structure of @ProfilePage and register the route the same way the other pages are registered  ✅

> **Answer:** D

### Q13. This module contrasts two situations: knowing exactly which files change versus not knowing where something lives. How do the directing patterns differ?

- **A.** Known files get discovery anyway as verification; unknown locations get an immediate edit, since searching wastes the model's effort
- **B.** Known files get explicit references and a directed edit; unknown locations get discovery first, edit second, in that order  ✅
- **C.** Both situations get identical instructions, since the index erases any practical difference between knowing and not knowing
- **D.** Known files get edited by hand without AI; unknown locations are the only case where directing the AI is worth the overhead

> **Answer:** B

### Q14. A builder reviews four diffs carefully and skims the one-line config diff. Production breaks. What does this module say about this?

- **A.** This is the predicted failure: the small diff in the config file is the one that breaks production, which is why every diff gets read  ✅
- **B.** One-line diffs are safe to skim by definition, so the production break must trace to one of the four carefully reviewed files
- **C.** Config files should never appear in AI diffs, so the presence of one signals a Cursor malfunction rather than a review lapse
- **D.** The correct fix is banning config changes from multi-file edits, since no review discipline can ever make config diffs safe to accept

> **Answer:** A

### Q15. A builder wants to understand how a request flows from a booking form to the database. Which navigation instruction does this module model?

- **A.** Walk me through how a request flows from the booking form to the database in this project, naming each file it passes through  ✅
- **B.** Explain how databases work in general, since generic knowledge transfers to this project better than project-specific tracing
- **C.** List every file in the project alphabetically, since complete inventories are the fastest route to understanding request flow
- **D.** Delete the booking form and rebuild it, since reconstruction teaches flow better than any explanation of existing code could

> **Answer:** A

### Q16. This module says to exclude certain folders from indexing. Which exclusions does it name, and why?

- **A.** The largest source folders, since indexing big directories slows the editor and their contents rarely matter to instructions
- **B.** Build output and dependency folders, so the index stays relevant instead of filling with generated and third-party code  ✅
- **C.** The test folders, since test code pollutes the index with duplicated names that collide with the production code's symbols
- **D.** Recently edited folders, since active work areas change too fast to index and stale entries mislead the AI during edits

> **Answer:** B

### Q17. A builder faces a huge project and asks how to keep multi-file work coherent at that scale. What does this module recommend?

- **A.** Work area by area: direct the AI to keep each pass scoped to one region and confirm boundaries, rather than sweeping the whole project  ✅
- **B.** Increase the context window setting to maximum, since a large enough window lets the model hold the entire project in view at once
- **C.** Split the project into separate repositories first, since multi-file coherence is impossible inside any single large repository
- **D.** Avoid multi-file edits entirely, since large projects only stay coherent when every single change is limited to exactly one file at a time

> **Answer:** A

### Q18. A client asks for phone numbers on user profiles. The builder directs discovery and gets six files back. Per this module's application example, what anchors the edit across all six?

- **A.** The alphabetically first file, since consistent sweeps process files in name order and the first file sets the pattern for the rest
- **B.** The largest file, since size indicates importance and the biggest file's conventions should govern the smaller ones during edits
- **C.** The model file, since the data definition is the anchor and the other five files change consistently around that anchor  ✅
- **D.** The newest file, since the most recent code reflects current standards and older files should be updated to match it in the sweep

> **Answer:** C

### Q19. This module describes partial acceptance of multi-file output. When is accepting some diffs and rejecting others the right move?

- **A.** Never, since diff sets are atomic and partial acceptance corrupts the change; the whole set must land or the whole set must not
- **B.** Routinely: partial acceptance is normal, accepting what is right and rejecting or redirecting what is not, using per-file controls  ✅
- **C.** Only when the AI suggests it, since the model tracks inter-diff dependencies and any builder-initiated partial acceptance breaks them
- **D.** Only on solo projects, since teams require all-or-nothing acceptance to keep the shared history clean for every collaborator

> **Answer:** B

### Q20. A builder asks when directing the AI's codebase search beats manually clicking through folders. What does this module say?

- **A.** Only on projects under fifty files, since AI search accuracy degrades with size while manual navigation simply scales without limits
- **B.** Never, since manual navigation builds the mental model that directed search skips, leaving builders dependent and disoriented
- **C.** In large projects generally: asking where something is handled beats clicking through folders and teaches the project as you build  ✅
- **D.** Only when the folder names are unclear, since well-organized projects make manual navigation faster than any directed search

> **Answer:** C

### Q21. This module gives a coherence-check instruction to run after a set of changes. What does it ask the AI to verify?

- **A.** That the changes match the AI's training data conventions, since external consistency matters more than internal consistency
- **B.** That the total line count decreased, since good multi-file changes always shrink a codebase and growth signals inconsistency
- **C.** That every file was modified at least once, since untouched files in a multi-file change indicate the sweep missed its coverage
- **D.** Naming, error handling, and imports across modified files are consistent with the rest of the project, reviewing last changes  ✅

> **Answer:** D

### Q22. A builder batches five unrelated changes into one giant instruction. What does this module say about batching?

- **A.** Bigger batches are better, since every instruction carries overhead and maximal batching minimizes total directing time spent
- **B.** Batch related changes, but split unrelated ones into separate passes, since unrelated edits in a pass muddy review and scope  ✅
- **C.** Never batch anything, since every change of any kind deserves its own instruction and its own conversation for clean review
- **D.** Batching is a model choice, since the AI automatically splits or merges your requests into fully optimal batches regardless of phrasing

> **Answer:** B

### Q23. A builder wants email handling changed and asks for 'every place user email addresses are read or written, listed with file and purpose, changing nothing yet.' What two module patterns does this combine?

- **A.** Pattern anchoring and partial acceptance, since the list anchors the pattern and the no-change clause pre-rejects the diffs
- **B.** Seam testing and index exclusion, since listing files tests the seams while the no-change clause excludes them from indexing
- **C.** Mode switching and re-referencing, since discovery must happen in Chat while the eventual edit then re-references the same files in Composer
- **D.** Discovery-first and explicit blast radius, since the search maps every occurrence before edits and the list defines the radius to change  ✅

> **Answer:** D

### Q24. For a very large mechanical sweep across hundreds of files, how does this module frame the Cursor versus Claude Code choice?

- **A.** Cursor only, since Claude Code cannot perform multi-file edits and mechanical sweeps are outside a terminal tool's capabilities
- **B.** Neither tool, since sweeps at that scale must be done with hand-written scripts rather than any AI directing environment
- **C.** Claude Code suits big mechanical sweeps, while Cursor's visual diff review is the advantage for closely inspected changes  ✅
- **D.** Both simultaneously on the same files, since parallel runs finish the sweep in half the time with no coordination concerns

> **Answer:** C

### Q25. Looking across this whole module, what is the governing principle of multi-file editing and codebase navigation?

- **A.** Control what the AI sees: reference explicitly or direct discovery, put the whole blast radius in view, review every diff, and test the seams  ✅
- **B.** Trust the index completely: once indexing is enabled, references, radius statements, and seam tests become redundant safety theater
- **C.** Minimize the files touched: the best multi-file edit is the one converted into a single-file edit, whatever consistency it costs
- **D.** Let changes accumulate unreviewed and audit weekly, since batch review at the end of the week reliably catches everything individual review would

> **Answer:** A


---
_Take it in the browser: https://the-faction.mn.co/posts/107131820_
