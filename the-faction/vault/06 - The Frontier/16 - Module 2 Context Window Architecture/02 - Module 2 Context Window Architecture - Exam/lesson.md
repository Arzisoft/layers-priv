---
course: "The Frontier"
module: "Module 2: Context Window Architecture"
lesson: "Module 2: Context Window Architecture — Exam"
type: "course_quiz"
post_id: 106578131
space_id: 24391596
source: "https://the-faction.mn.co/posts/106578131"
updated: "2026-08-28T16:32:07Z"
---

# Module 2: Context Window Architecture — Exam

> Exam for **Module 2: Context Window Architecture** (The Frontier) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. Users report that long answers keep stopping mid-sentence at the worst moments. The window is packed with instructions, documents, and history. What architectural piece is missing?

- **A.** A stronger closing instruction telling the model to always finish its sentences before stopping
- **B.** A protected response reserve, budgeted space the output needs that other layers are invading  ✅
- **C.** A streaming endpoint, since non-streaming calls terminate early when providers balance load
- **D.** A summarization pass on outputs, letting the model compress long answers into the available space

> **Answer:** B

### Q2. A new team member asks what actually competes for room inside one model call. Which list is right?

- **A.** Instructions, long-lived context, retrieved content, conversation history, and the response space all share it  ✅
- **B.** Only the retrieved documents and the response compete, since instructions live in a separate channel
- **C.** Only the conversation history competes, because documents are attached as files outside the window
- **D.** Nothing competes until the hard limit is reached, at which point the whole call fails loudly with an explicit error

> **Answer:** A

### Q3. A builder is writing down which layers survive when a window overflows and which get cut first. What is this artifact called, and what does it do?

- **A.** A truncation script: it compresses every layer by an equal percentage when space runs short
- **B.** A token ledger: it bills each feature team for the window space their layer consumes
- **C.** A fallback chain: it retries the call on progressively larger models until the content fits
- **D.** A priority hierarchy: it decides in advance what stays and what goes when space runs out  ✅

> **Answer:** D

### Q4. After a naive fix for overflow, an assistant suddenly loses all its standing rules in long conversations: no persona, no policies. What did the fix almost certainly do?

- **A.** Compressed the history so hard that the model lost the thread of the conversation topic
- **B.** Raised the temperature during long sessions, washing out the persona with randomness
- **C.** Truncated from the top of the window, deleting the system prompt that held the rules  ✅
- **D.** Moved the standing rules into each user message, where later turns overwrote them

> **Answer:** C

### Q5. A contract excerpt must be shortened to fit its budget slice. One approach is banned outright by good truncation practice. Which one?

- **A.** Cutting the delimited document in the middle, leaving a fragment the model will misread  ✅
- **B.** Excluding the whole excerpt and logging the exclusion so the gap is visible downstream
- **C.** Summarizing the excerpt into a shorter passage that preserves the operative clauses
- **D.** Selecting only the sections relevant to the current question and dropping the rest whole

> **Answer:** A

### Q6. History has outgrown its slice mid-conversation. Per sound truncation strategy, what should the assembly code do?

- **A.** Drop whole oldest messages first, keeping recent turns intact and every message unsplit  ✅
- **B.** Trim a fixed number of tokens off the end of every message so all turns shrink evenly
- **C.** Delete the assistant's own past responses first, since the model can regenerate them on demand
- **D.** Pause the conversation and ask the user to start a new session before continuing further

> **Answer:** A

### Q7. A client asks why the team does not just run everything on the biggest window available. What is the honest tradeoff?

- **A.** Bigger windows are cheaper per token but slower, so the choice is purely about latency tolerance
- **B.** Bigger windows cost more per call and can dilute attention, while smaller ones risk missing content  ✅
- **C.** Bigger windows are identical in cost and quality, so the choice is a matter of provider preference
- **D.** Bigger windows improve quality linearly with size, so budget is the only reason to hold back

> **Answer:** B

### Q8. Two layouts both pass tests: one uses a huge window with everything included, one uses a lean window holding only what the task needs. Which should ship, and why?

- **A.** The huge one, because headroom protects against future growth in documents and history
- **B.** Either one, because passing tests is the only criterion that matters for a production layout
- **C.** The huge one, because retrieval can be removed entirely when everything already fits inside
- **D.** The lean one: the goal is the smallest window that reliably contains what the task requires  ✅

> **Answer:** D

### Q9. A builder wants a layout that survives switching to a model with a different window size, without editing budgets by hand. What design achieves this?

- **A.** Hardcoding generous token counts per layer, sized for the largest model on the market today
- **B.** Removing budgets entirely and letting each call use whatever space it happens to need
- **C.** Defining each layer as a percentage of the available window, with priorities for overflow  ✅
- **D.** Maintaining a separate hand-tuned layout file for every model the system might ever use

> **Answer:** C

### Q10. A 200-page document is uploaded, and the assistant answers well about early chapters but misses facts from the final third. No errors appear anywhere. What is the likely cause?

- **A.** The model read the whole document but weighted early chapters as more authoritative sources
- **B.** Silent truncation: the document exceeded its space and the tail never entered the window  ✅
- **C.** The embedding model indexed only the opening chapters because of a rate limit during upload
- **D.** The document's later sections used tables, which models skip unless told to read them

> **Answer:** B

### Q11. Monthly spend on model calls has doubled while output quality stayed flat. The window has been growing all quarter. What does this pattern usually mean?

- **A.** Low-value layers are hauling dead weight; the fix is shrinking them, not admiring the bill  ✅
- **B.** The provider raised per-token prices mid-quarter, and the contract needs renegotiating
- **C.** Quality improvements from added context arrive on a delay and will show up next quarter
- **D.** The system has hit the model's quality ceiling, and only an upgrade will move outcomes

> **Answer:** A

### Q12. A layer holds background material that is about to be cut for space, but some of its meaning should survive. Which strategy fits?

- **A.** Keep the layer whole anyway and let the response reserve absorb the overflow this once
- **B.** Cut it byte by byte from the bottom until the window fits, accepting whatever remains
- **C.** Summarize the material into a compact digest before discarding the full original text  ✅
- **D.** Move the material into the user message, where truncation rules do not apply to it

> **Answer:** C

### Q13. A builder estimates layer sizes by counting characters and dividing by four. Budgets keep drifting from reality. What should they direct AI to use instead?

- **A.** Word counts multiplied by a safety factor, which track model behavior more closely than characters
- **B.** A fixed 10 percent margin added to every character estimate to absorb the drift over time
- **C.** The visual length of the rendered text, since windows are measured in displayed lines
- **D.** The provider's official token counting, such as tiktoken or the count-tokens endpoint  ✅

> **Answer:** D

### Q14. No layer in an app has a defined budget. The system works fine for weeks, then quality collapses as usage grows. What does the collapse reveal about unbudgeted layouts?

- **A.** They fail loudly at the API level once any single layer exceeds the provider's per-layer cap
- **B.** They let one growing layer silently starve the rest until something important is displaced  ✅
- **C.** They work indefinitely as long as the total stays under the hard limit of the window
- **D.** They shift cost to the provider side, which eventually throttles the offending account

> **Answer:** B

### Q15. A builder is about to direct AI to write the assembly code for a new app. What should exist before any implementation begins?

- **A.** The layout on paper: layers listed, budgets assigned, priorities ranked, overflow rules chosen  ✅
- **B.** A finished test suite covering every edge case the assembly code could possibly encounter
- **C.** A cost ceiling negotiated with the client, since budgets cannot be set without a price
- **D.** A benchmark comparing three candidate models on the application's ten hardest queries

> **Answer:** A

### Q16. Output quality degraded somewhere in yesterday's traffic, and the builder wants to know which layer got squeezed. What makes this question answerable in minutes?

- **A.** The provider dashboard, which breaks down every call by latency, region, and result code
- **B.** User feedback ratings, which correlate strongly enough with layer sizes to locate the issue
- **C.** The git history of the prompt files, which shows every change made during the incident window
- **D.** Per-call allocation logging that records tokens used by each layer on every single request  ✅

> **Answer:** D

### Q17. A truncation pass just ran on a crowded window. Per this module, what single test tells you whether the truncation preserved meaning?

- **A.** The window shrank by at least the targeted number of tokens with no API errors raised
- **B.** The remaining text still scores high on similarity against the original full window
- **C.** The window still tells a coherent story: no orphaned fragments, no missing referents  ✅
- **D.** The model's next response arrives faster, confirming the reduced processing burden

> **Answer:** C

### Q18. Facing overflow problems, a team upgrades to a model with triple the window and the symptoms vanish. Six months later they are back. What did the upgrade actually do?

- **A.** Fixed the problem permanently; the new symptoms must come from an unrelated regression
- **B.** Introduced a subtle incompatibility between the old layout and the new model's tokenizer
- **C.** Bought time while hiding the allocation flaw, which kept growing until it filled the new space  ✅
- **D.** Traded the overflow problem for a latency problem, which users now experience as failure

> **Answer:** C

### Q19. In a research assistant, retrieved sources and long chat history are fighting for the same space. How does an architect settle this?

- **A.** Split the space evenly forever, since fairness between layers keeps behavior predictable
- **B.** Rank the two by priority for this task type, cap the lower one, and enforce the budgets  ✅
- **C.** Let recency decide at runtime: whichever layer grew most recently gets the contested space
- **D.** Alternate by turn: history gets the space on odd messages, retrieval on even messages

> **Answer:** B

### Q20. During overflow, an assembly routine considers cutting the system prompt and the current user message along with everything else. Which architectural rule does this violate?

- **A.** Standing instructions and the live question are normally untouchable; other layers yield first  ✅
- **B.** System prompts may only be edited by the provider, never removed by application code
- **C.** The current message can be dropped only if the user is notified and confirms within the turn
- **D.** All layers must shrink proportionally during overflow so no single layer bears the cut

> **Answer:** A

### Q21. A team fills a giant window with marginally related content, reasoning that the model will simply ignore what it does not need. What does this module say about that assumption?

- **A.** It holds as long as the content is grouped by topic with clear headers between sections
- **B.** It holds for models above a certain size, which learn to route attention past filler
- **C.** It fails only when marginal content exceeds half the window, the documented threshold
- **D.** It fails in practice: filling space with marginal content degrades attention to what matters  ✅

> **Answer:** D

### Q22. An app inherits its history handling from a framework default that keeps a fixed number of recent messages. When should the builder replace this?

- **A.** Never, since framework defaults encode best practices learned across thousands of deployments
- **B.** Once a real layout exists: defaults are generic and history needs a budget within your design  ✅
- **C.** Only after users complain, since premature tuning wastes effort on problems that may not occur
- **D.** When switching providers, since defaults are calibrated per provider and transfer poorly

> **Answer:** B

### Q23. A layout document assigns each layer a budget and a rank. A reviewer says one column is still missing before AI can implement it. Which column?

- **A.** The overflow rule per layer: whether it drops, summarizes, or refuses to yield when space runs out  ✅
- **B.** The model version each layer was tested against, so any regressions can be traced after later upgrades
- **C.** The named team owner of each layer, so budget disputes always have a human to escalate toward
- **D.** The average token price of each layer, so finance can forecast spend as traffic scales

> **Answer:** A

### Q24. The provider ships a new model tier and the team migrates. Every layout built one specific way breaks immediately. Which way?

- **A.** Layouts defined as percentages, which scale their slices to window sizes they never tested
- **B.** Layouts with priority hierarchies, which assume an ordering the new tier does not honor
- **C.** Layouts with response reserves, which the new tier allocates automatically and doubly
- **D.** Layouts built on hardcoded token counts, which silently stopped matching the new window  ✅

> **Answer:** D

### Q25. One idea governs this entire module, from budgets to truncation to reserves. Which statement is it?

- **A.** The window is a queue: content enters in the order it arrives and exits whenever newer content arrives
- **B.** The window is a cache: keep whatever was useful recently and evict whatever has gone cold
- **C.** The window is a floor plan: every layer gets deliberate space and priority, nothing by accident  ✅
- **D.** The window is a commodity: buy the largest one available and allocation takes care of itself

> **Answer:** C


---
_Take it in the browser: https://the-faction.mn.co/posts/106578131_
