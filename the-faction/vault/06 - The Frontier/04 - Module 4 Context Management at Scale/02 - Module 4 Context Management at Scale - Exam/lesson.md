---
course: "The Frontier"
module: "Module 4: Context Management at Scale"
lesson: "Module 4: Context Management at Scale — Exam"
type: "course_quiz"
post_id: 104725939
space_id: 24391596
source: "https://the-faction.mn.co/posts/104725939"
updated: "2026-08-10T17:18:21Z"
---

# Module 4: Context Management at Scale — Exam

> Exam for **Module 4: Context Management at Scale** (The Frontier) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. What is the context window in practical terms for an AI Directed Engineer?

- **A.** The working memory an agent can attend to at once; everything it acts on must fit inside it  ✅
- **B.** The time period an agent will wait for a response before abandoning the current request entirely
- **C.** The physical screen area an agent can render its answers into during a conversation
- **D.** The number of users allowed to interact with one agent simultaneously in a session

> **Answer:** A

### Q2. What are the classic symptoms of a session whose context has degraded?

- **A.** Faster responses, since a full context lets the agent skip over most of its reasoning steps
- **B.** Louder formatting, since degraded agents compensate with bolding and longer headers
- **C.** Forgotten early instructions, contradictions with prior decisions, and drifting quality  ✅
- **D.** Perfect recall of the start but confusion about the most recent messages exchanged

> **Answer:** C

### Q3. When should a long-running effort rely on summarization?

- **A.** Never, since a summary is always a corrupted version of the record it tries to replace
- **B.** Only at the very end of a project, when a final report needs writing for stakeholders
- **C.** Constantly and randomly, since frequent summarizing keeps every agent maximally alert
- **D.** When history matters but detail doesn't: compress the past so the present stays sharp  ✅

> **Answer:** D

### Q4. Why is retrieval usually better than stuffing every document into the context up front?

- **A.** Retrieval is free while context is billed, making the choice purely a question of cost
- **B.** Pulling only what the current step needs keeps attention focused and capacity available  ✅
- **C.** Documents lose their formatting when placed in context but keep it when retrieved
- **D.** Retrieval systems legally shield you from copyright issues that context inclusion creates

> **Answer:** B

### Q5. What belongs in a persistent memory store rather than in the conversation itself?

- **A.** Nothing; genuine memory can only exist inside the live conversation an agent is having
- **B.** Casual small talk, since pleasantries are the highest-value content worth preserving
- **C.** Durable facts, decisions, and state the work will need across sessions and resets  ✅
- **D.** The agent's opinions of the user, since personalization data outranks project data

> **Answer:** C

### Q6. When is starting a fresh session the right move rather than pushing a long one further?

- **A.** When the current session's quality is visibly degrading and its accumulated history isn't earning its space  ✅
- **B.** Never; abandoning a session throws away the working relationship the agent has painstakingly built with the material
- **C.** Every hour on a fixed schedule, regardless of how well the current session happens to be performing
- **D.** Only when the provider forces it, since voluntary resets discard nuance that can never be replaced

> **Answer:** A

### Q7. You're planning a task that will take many steps and lots of material. What does context budgeting mean?

- **A.** Requesting a spending increase from the finance team before the task's first step is ever executed
- **B.** Trusting the model to manage its own capacity, since self-regulation beats planning
- **C.** Reserving half the window for pleasantries so the working relationship stays healthy
- **D.** Deciding up front what deserves space — instructions, state, materials — so it fits the whole job  ✅

> **Answer:** D

### Q8. Critical rules were stated at the start of a very long session and the agent has begun violating them. What is the practical fix?

- **A.** Threaten the agent with replacement, since consequences reliably restore instruction-following
- **B.** Re-anchor them: restate key rules periodically or in a place the agent always re-reads  ✅
- **C.** Accept it, since rule decay is physics and no design choice can meaningfully slow it
- **D.** Whisper the rules in different words each time, since variety strengthens retention

> **Answer:** B

### Q9. What separates good retrieval from bad retrieval in an agent system?

- **A.** Relevance and precision: surfacing the few pieces the step needs, not everything related  ✅
- **B.** Volume: returning the maximum number of documents so nothing could ever be missed
- **C.** Speed alone: any result set is fine as long as it arrives within one second of being asked for
- **D.** Alphabetical coverage: retrieving evenly across the alphabet to avoid selection bias

> **Answer:** A

### Q10. Where should the authoritative state of a long project live?

- **A.** In the agent's memory of the conversation, since models retain strong impressions across turns
- **B.** Nowhere, since maintaining authoritative state creates a single point of failure
- **C.** In whichever session is currently open, moving homes each time a new thread starts
- **D.** Outside the conversation — in files or systems of record — with sessions reading from it  ✅

> **Answer:** D

### Q11. You summarized a long session to continue in a fresh one, and the new session made a decision that contradicts a key constraint. What happened?

- **A.** The new session is defective and should be reported back to the provider for immediate retraining
- **B.** Nothing avoidable; constraints simply cannot move between separate sessions in any system built today
- **C.** The summary dropped the constraint; compression loses detail, so critical facts need explicit carryover  ✅
- **D.** The constraint expired naturally, since decisions older than one full session lose their binding force over time

> **Answer:** C

### Q12. Why run separate sessions for strategy and for heavy production work?

- **A.** Providers bill strategy tokens at a lower rate than production tokens in most enterprise plans today
- **B.** Bulk production output floods the context, crowding out the judgment the strategy thread needs  ✅
- **C.** Agents develop split personalities whenever one session mixes deep thinking with heavy producing
- **D.** Separate sessions double your allowed usage, since usage limits apply per individual conversation

> **Answer:** B

### Q13. A session accumulated pages of irrelevant tool output along the way. What is the effect?

- **A.** Noise competes for attention; irrelevant bulk dilutes what matters and degrades responses  ✅
- **B.** None, since agents automatically skip over any content that is not useful to the current step
- **C.** Positive, since unused content acts as ballast that stabilizes the agent's reasoning
- **D.** Purely financial, since junk content costs tokens but has no effect on output quality

> **Answer:** A

### Q14. What does memory design mean for an agent that runs for weeks on the same job?

- **A.** Choosing a model with a bigger window, since raw size replaces any memory architecture needed
- **B.** Nothing special, since long-running jobs are just short jobs repeated more times
- **C.** Saving the full transcript daily and reloading all of it into every future session
- **D.** Deciding what gets written down, where, and how sessions load the right slice of it back  ✅

> **Answer:** D

### Q15. Which information should be logged permanently outside any context window?

- **A.** Nothing, since external logs compete with the agent's own memory and cause version conflicts
- **B.** Decisions, outcomes, and key artifacts — the record you'll need when sessions are gone  ✅
- **C.** Only errors, since successful work needs no record once the deliverable has shipped
- **D.** The agent's full reasoning on every turn, preserved verbatim forever for compliance

> **Answer:** B

### Q16. What makes a good handoff summary when one session's work continues in another?

- **A.** Maximum possible length, since a longer handoff necessarily transfers more of the prior state
- **B.** Emotional tone notes, since the next session must match the previous session's mood
- **C.** State, decisions, constraints, and next steps — what the next session needs to act correctly  ✅
- **D.** A riddle format, since encoding the handoff forces the next session to engage deeply

> **Answer:** C

### Q17. Beyond quality, why does context size discipline matter?

- **A.** Tokens are money and time: bloated context raises cost and latency on every single turn  ✅
- **B.** Providers publicly rank customers by context efficiency, affecting your future account status
- **C.** Large contexts wear out models faster, degrading them for other customers' requests
- **D.** Regulators cap total context usage per company, making waste a compliance issue

> **Answer:** A

### Q18. Early in a session a decision was made; hours later it was reversed. The context now holds both. What risk does this create?

- **A.** None, since models always weight the newest information completely over the oldest
- **B.** Legal exposure, since holding contradictory records violates business documentation standards
- **C.** The agent may act on the stale version; superseded decisions should be explicitly retired  ✅
- **D.** Double billing, since contradictory instructions are processed twice by providers

> **Answer:** C

### Q19. How do you evaluate whether a context strategy actually works?

- **A.** By feel, since context quality is subjective and resists any form of measurement
- **B.** Test it: run the same long workload under different strategies and compare output quality  ✅
- **C.** By cost alone, since the cheapest context configuration is by definition the very best one
- **D.** By asking the agent which strategy it prefers, since models know their own needs best

> **Answer:** B

### Q20. What role does a searchable knowledge store play in a context strategy?

- **A.** It replaces the model, answering questions directly without any agent involvement
- **B.** It is a compliance archive only, never actually read during live agent operations
- **C.** It stores content that must never influence outputs, quarantined away from the agent
- **D.** It holds the long tail of material, letting sessions pull relevant pieces on demand  ✅

> **Answer:** D

### Q21. A teammate assumes the agent remembers last month's project details in a brand-new session. What do you tell them?

- **A.** Sessions start empty; anything the agent should know must be provided or retrieved by design  ✅
- **B.** They're right; modern models retain everything across sessions belonging to the same account
- **C.** It remembers only financial details, since numbers persist in memory while words fade away
- **D.** It remembers if asked politely, since retrieval across sessions is a courtesy feature of providers

> **Answer:** A

### Q22. The context is nearly full and something must go. What goes first?

- **A.** The system instructions, since the agent has fully internalized all of them by this point already
- **B.** Stale and low-value bulk — old raw outputs and resolved threads — never active constraints  ✅
- **C.** The most recent messages, since older content has had more time to prove its worth
- **D.** Random selections, since unbiased trimming avoids introducing any systematic gaps

> **Answer:** B

### Q23. Small errors made early in a session keep getting repeated and built upon. What is this failure called and what fixes it?

- **A.** Model fatigue; pausing the session for an hour lets the errors gradually decay out of the context
- **B.** Token drift; switching providers mid-session clears out any accumulated numerical errors
- **C.** Feature creep; freezing the scope prevents any new errors from entering the working record
- **D.** Context poisoning; correct the record explicitly or reset, since errors compound as precedent  ✅

> **Answer:** D

### Q24. Multiple sessions and documents disagree about a project detail. What prevents this class of problem?

- **A.** Majority voting across the sessions, letting the most common version become the truth
- **B.** Avoiding documentation entirely, since fewer records mathematically means fewer conflicts
- **C.** A designated source of truth that every session reads from and updates through one path  ✅
- **D.** Trusting the longest document, since length correlates directly with its authority

> **Answer:** C

### Q25. Which principle should govern context management across every long-running effort?

- **A.** Context is a scarce, expensive workspace: curate what enters, externalize state, reset without fear  ✅
- **B.** Context is unlimited in practice: modern windows are so large that discipline has now become obsolete
- **C.** Context is sacred history: nothing that entered a session should ever be summarized away
- **D.** Context is the model's problem: capable systems manage their own memory without design

> **Answer:** A


---
_Take it in the browser: https://the-faction.mn.co/posts/104725939_
