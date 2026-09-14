---
course: "The Frontier"
module: "Module 6: Shared Memory Across Multi-Agent Systems"
lesson: "Module 6: Shared Memory Across Multi-Agent Systems — Exam"
type: "course_quiz"
post_id: 107155324
space_id: 24391596
source: "https://the-faction.mn.co/posts/107155324"
updated: "2026-09-10T19:37:46Z"
---

# Module 6: Shared Memory Across Multi-Agent Systems — Exam

> Exam for **Module 6: Shared Memory Across Multi-Agent Systems** (The Frontier) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. For each piece of state in a two-agent system, a builder must decide shared or private. What question draws the line?

- **A.** How large is the record, since bulky state belongs in shared storage where space is cheap
- **B.** Who else needs this to do their job, and who would it merely confuse if they saw it  ✅
- **C.** Which agent wrote it first, since original authorship determines visibility rights
- **D.** How often it changes, since volatile state must stay private to avoid sync churn

> **Answer:** B

### Q2. A research agent produces verified findings, retry attempts, and half-formed reasoning drafts. Which of these stays private, and why?

- **A.** The retries and half-formed drafts: they would bury teammates in noise without helping  ✅
- **B.** The verified findings: conclusions are valuable and value is what most deserves protection
- **C.** All three: nothing an agent produces should be visible until a human reviews it first
- **D.** None: full transparency between agents is what makes multi-agent debugging possible

> **Answer:** A

### Q3. A pipeline passes all state from agent to agent inside messages. One agent crashes mid-run. What does the shared-store pattern fix here?

- **A.** Messages arrive out of order under load, while stores serialize writes automatically
- **B.** Message payloads are capped in size, while stores can hold state of any length needed
- **C.** Messages cost tokens to resend, while store reads are free after the first fetch
- **D.** State in messages dies with the crash; state in the store survives any single failure  ✅

> **Answer:** D

### Q4. An agent loads shared state at boot, works for an hour, then acts on that picture. Meanwhile another agent changed it. What does this illustrate?

- **A.** Sync is about timing: between refresh points, the world can change under any agent  ✅
- **B.** Boot loading is the flaw: agents should read the store before every single response
- **C.** The store failed: shared writes should push instantly into all running sessions
- **D.** One-hour sessions are too long: short sessions are how shared systems stay honest

> **Answer:** A

### Q5. When should a team pick its conflict resolution rule for a shared table?

- **A.** After the first real conflict, since rules designed without cases tend to be abstract
- **B.** Never explicitly: databases already order writes, and that ordering is the fair rule
- **C.** During incident review, when the cost of each option is visible in a concrete failure
- **D.** In advance, at design time: rules chosen mid-incident are the worst rules every time  ✅

> **Answer:** D

### Q6. A shared table holds low-stakes, frequently updated facts like task progress percentages. Which conflict rule fits?

- **A.** Last-write-wins with timestamps: cheap, simple, and adequate when stakes are low  ✅
- **B.** Escalation to a supervisor, since frequent updates mean frequent contradictions
- **C.** Owner-wins, since progress data belongs to whichever agent started the task first
- **D.** Freeze on conflict: lock the row until a human clears the contradiction manually

> **Answer:** A

### Q7. The ops agent is the recognized authority on schedules. The research agent writes a conflicting schedule value. Under source authority, what happens?

- **A.** The newer value wins regardless of author, since freshness beats domain expertise
- **B.** The ops agent's value stands: the domain owner's write outranks the outsider's  ✅
- **C.** Both values persist with flags, and the next reader chooses whichever fits its task
- **D.** The write triggers a merge: both agents negotiate a compromise value via messages

> **Answer:** B

### Q8. Two agents disagree about a fact that, if wrong, ships a legal document with a bad clause. Which resolution style fits this table?

- **A.** Last-write-wins, since timestamps at least make the outcome deterministic and fast
- **B.** Random selection between the two values, since either agent is equally trustworthy
- **C.** Escalation: a human or supervisor decides, because contradictions here are costly  ✅
- **D.** Owner-wins by table default, even though neither agent owns the legal domain yet

> **Answer:** C

### Q9. A design gives each domain exactly one writing agent while every agent may read. What does this buy the system?

- **A.** Faster reads, since single-writer tables can skip locking on every single select query
- **B.** Smaller storage, since one writer produces fewer duplicate records per domain
- **C.** Whole classes of race conditions never exist, since competing writes cannot occur  ✅
- **D.** Simpler prompts, since each agent's instructions only describe its own domain

> **Answer:** C

### Q10. Agent A finishes research; agent B starts drafting. What should the handoff record contain?

- **A.** What was done, what was decided, and what remains, with links to supporting memories  ✅
- **B.** Agent A's full session transcript, so agent B can reconstruct every step of the reasoning
- **C.** Only the final deliverable, since anything else biases agent B's independent work
- **D.** A quality score for agent A's work, so agent B knows how much it can be trusted

> **Answer:** A

### Q11. A handoff passes agent A's entire session transcript into agent B's context. What two costs follow?

- **A.** Duplicate writes and slower queries, since the transcript re-enters the shared store
- **B.** Latency and locking, since transcripts hold table references that must stay open
- **C.** Privacy exposure and drift, since transcripts carry other clients' data forward
- **D.** A blown context budget, and conclusions hidden inside noise agent B must dig through  ✅

> **Answer:** D

### Q12. A team routes every agent's scratch thoughts into the shared store 'for transparency.' What actually happens?

- **A.** Debugging improves at the cost of storage, a tradeoff most teams accept happily
- **B.** Nothing changes: readers simply ignore records they did not personally request
- **C.** Teammates drown in noise and the conflict surface multiplies with every writer  ✅
- **D.** The store self-organizes: retrieval ranking naturally buries the scratch content

> **Answer:** C

### Q13. 'We do not need a shared store; agents just tell each other things.' Which failure mode is this design signing up for?

- **A.** Token exhaustion, since agent-to-agent messages bill at premium completion rates
- **B.** Total state loss on mid-pipeline crash, since nothing durable sits outside talk  ✅
- **C.** Slow rollout, since message schemas take longer to design than database tables
- **D.** Model confusion, since agents cannot distinguish peer messages from user input

> **Answer:** B

### Q14. An incident is live: two agents wrote contradictory client budgets and the pipeline stalled. The team starts debating resolution rules now. What should they expect?

- **A.** The debate will land on escalation, which suits budget data in most deployments
- **B.** A fine outcome: live incidents supply exactly the context good rules require
- **C.** The worst rule every time: mid-incident pressure produces reactive, bad policy  ✅
- **D.** A rollback: without a rule on file, the store reverts to its last clean snapshot

> **Answer:** C

### Q15. An agent booted at 9am and at 10am confidently acts on a fact another agent changed at 9:30. Name the mistake in the design.

- **A.** Missing writer IDs: without authorship, the agent cannot rank fact versions
- **B.** Assumed instant sync: boot-time state was called fresh instead of perishable  ✅
- **C.** Missing escalation: contradictions between times should route to a supervisor
- **D.** Wrong ownership: the 9:30 writer should never have touched that domain's rows

> **Answer:** B

### Q16. Every shared record carries a writer ID and a timestamp, and reviewers insist these are non-negotiable. What do these two fields enable?

- **A.** Billing attribution and quota enforcement across the agents sharing the store
- **B.** Row-level security and per-agent encryption of everything each agent writes
- **C.** Replay of the full write history, so any past store state can be reconstructed
- **D.** Conflict resolution and stale-read detection, the mechanics sharing depends on  ✅

> **Answer:** D

### Q17. Beside the shared tables, each agent gets its own namespace in the same database. What lives there?

- **A.** Copies of shared facts, cached per agent so reads avoid touching shared tables
- **B.** Private working state: scratch reasoning and drafts no teammate needs to see  ✅
- **C.** Conflict backups: losing values from resolved conflicts, kept for later audits
- **D.** Each agent's system prompt, versioned so deployments can roll back cleanly

> **Answer:** B

### Q18. A builder is wiring sync points into a pipeline agent. Which set matches the recommended pattern?

- **A.** On a fixed timer only, refreshing shared state every five minutes regardless of load
- **B.** On user request only, since refreshes should stay under explicit human control
- **C.** At boot, before writes, and at every handoff, so decisions rest on current state  ✅
- **D.** After errors only, since a failed action is the clearest signal that state went stale

> **Answer:** C

### Q19. After moving to shared memory with handoff records, a three-agent pipeline crashes in stage two. What does recovery look like now?

- **A.** The pipeline restarts from zero, but faster, since research results re-derive quickly
- **B.** It resumes from the last handoff record, since durable state survived the crash  ✅
- **C.** The supervisor agent replays stage one's messages to reconstruct lost context
- **D.** Stage three proceeds using stale state while stage two rebuilds in the background

> **Answer:** B

### Q20. Before the rebuild, a review agent kept re-flagging claims the researcher had already verified. What ended the duplicated work?

- **A.** A larger context window let the review agent hold the researcher's full history
- **B.** A politeness rule in the prompt told the reviewer to trust researcher claims
- **C.** Retry limits stopped the reviewer after two verification passes per claim
- **D.** The reviewer began reading verified claims from the shared store before flagging  ✅

> **Answer:** D

### Q21. Agents in one system run with separate credentials against one Supabase project. Which platform feature keeps each agent inside its lane?

- **A.** Row-level security: policies decide which rows each credential can read or write  ✅
- **B.** Connection pooling: separate pools keep each of the agents' queries physically isolated
- **C.** Foreign keys: referential integrity blocks writes that cross domain boundaries
- **D.** Database triggers: procedural checks reject queries from unexpected sources

> **Answer:** A

### Q22. A team uses a message queue between agents and also keeps a shared store. What division of labor is correct?

- **A.** Messages carry notifications; the durable truth lives in the store, not messages  ✅
- **B.** Messages carry all state; the store archives whatever the queue has already sent
- **C.** The two are redundant: mature teams keep whichever one shipped first and drop one
- **D.** Messages carry facts and the store carries opinions, keeping judgment separate

> **Answer:** A

### Q23. A builder is directing AI to set up ownership across research, drafting, and ops agents. What is the right instruction?

- **A.** Let all three write everywhere, and rely on timestamps to sort out the collisions
- **B.** Give ownership of all domains to the supervisor, since neutrality prevents bias
- **C.** Rotate ownership weekly, so no single agent's failures concentrate in one domain
- **D.** Assign each domain one writing agent, and generate rules enforcing single-writer  ✅

> **Answer:** D

### Q24. Handoff records make pipeline stages composable. Why does that matter beyond this course?

- **A.** Composable stages compress better, cutting storage costs across the whole catalog
- **B.** It satisfies audit requirements that apply once systems exceed three agents
- **C.** They become the backbone of larger multi-agent architectures built the same way  ✅
- **D.** It lets stages run on different model providers without any shared conventions

> **Answer:** C

### Q25. Strip the mechanics away. What is shared memory actually for in a multi-agent system?

- **A.** It is what turns a pile of agents into a system: a team with one durable truth  ✅
- **B.** It is a cost optimization: shared storage bills less than per-agent databases
- **C.** It is a safety layer: agents police each other by reading each other's state
- **D.** It is a migration path: shared stores let single agents split without rewrites

> **Answer:** A


---
_Take it in the browser: https://the-faction.mn.co/posts/107155324_
