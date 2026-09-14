---
course: "The Frontier"
module: "Module 1: Why Agents Need Memory Beyond the Context Window"
lesson: "Module 1: Why Agents Need Memory Beyond the Context Window — Exam"
type: "course_quiz"
post_id: 107155290
space_id: 24391596
source: "https://the-faction.mn.co/posts/107155290"
updated: "2026-09-10T19:33:52Z"
---

# Module 1: Why Agents Need Memory Beyond the Context Window — Exam

> Exam for **Module 1: Why Agents Need Memory Beyond the Context Window** (The Frontier) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. A builder calls a frontier model twice through the API with identical setup. The second call shows no trace of the first. What explains this?

- **A.** The API rate limiter isolates calls from each other, so shared state is stripped for security reasons
- **B.** The model weights update only during training runs, so recall appears once the next fine-tune completes
- **C.** The model holds no state between calls; anything memory-like must be replayed into context by the app  ✅
- **D.** The second call routed to a different server region, and session affinity was lost between requests

> **Answer:** C

### Q2. 'The agent was brilliant yesterday and useless this morning,' a client reports after a session restart. Nothing in the code changed. What most likely happened?

- **A.** The context reset wiped decisions, preferences, and completed work, so the agent started from blank  ✅
- **B.** The model provider silently downgraded the underlying model overnight, reducing reasoning quality everywhere
- **C.** The prompt template drifted during deployment, so the agent received weaker instructions today
- **D.** Token limits tightened as usage grew, so the agent saw a truncated view of the client request

> **Answer:** A

### Q3. A teammate points at a chat app and says the model clearly remembers, since it references messages from an hour ago. What is actually happening?

- **A.** The model caches recent embeddings internally and refreshes them each time the same user reconnects
- **B.** The app replays the conversation history into the context window each call; the model retains nothing  ✅
- **C.** The provider fine-tunes a small adapter on each conversation, giving the model lightweight recall
- **D.** The model keeps a short rolling buffer of recent tokens alive between calls until the session formally ends

> **Answer:** B

### Q4. Your agent logs this entry: 'March 4, staging deploy failed with a migration timeout.' Which memory type is this, and why?

- **A.** Semantic, because the entry states a durable fact about the system that stays true across sessions
- **B.** Procedural, because deploy failures encode lessons about how the deployment process should be run
- **C.** Working, because logs exist inside the session window and evaporate whenever the context resets
- **D.** Episodic, because it records a specific event that happened at a specific time: what happened  ✅

> **Answer:** D

### Q5. An agent stores 'this client prefers invoices on the first of the month' with no reference to how it learned this. What kind of memory is that?

- **A.** Semantic memory: a distilled fact about what is true, stripped of the event that originally taught it  ✅
- **B.** Episodic memory: a record tied to the specific conversation in which the client first stated the preference
- **C.** Procedural memory: an operating rule that tells the agent how invoicing work should be carried out
- **D.** Session memory: a preference held in the live window until the conversation ends and context clears

> **Answer:** A

### Q6. A firm wants its agent to run the same escalation steps every time a refund exceeds a threshold, without being re-briefed. Which memory type carries this?

- **A.** Semantic, since the threshold amount is simply a fact the agent can store once and look up when needed
- **B.** Episodic, since past escalations show the agent concrete examples of the steps being followed
- **C.** Procedural, since it encodes how work is done here, making the agent trained rather than briefed  ✅
- **D.** Contextual, since escalation rules belong in the system prompt where they load every session

> **Answer:** C

### Q7. Two builders debate. One says a polished chatbot already counts as an agent. Under this course's distinction, what actually separates the two?

- **A.** An agent runs on a larger model with extensive tool access, while a chatbot is limited to text conversation
- **B.** An agent operates autonomously without human review, while a chatbot always waits for user input
- **C.** An agent is deployed on infrastructure you control, while a chatbot lives inside a vendor product
- **D.** An agent accumulates context across sessions and serves a relationship; a chatbot serves a session  ✅

> **Answer:** D

### Q8. A session just ended and the agent produced three durable client facts during it. In the core memory loop, what should happen next?

- **A.** The facts stay in the transcript, and the next session searches raw history whenever it needs them
- **B.** The facts get appended to the system prompt permanently so every future session sees them by default
- **C.** The facts are summarized into the closing message so the user can paste them back in next time
- **D.** A write step captures them to storage outside the model, such as rows with source and timestamp  ✅

> **Answer:** D

### Q9. At startup, before any user input arrives, a production agent loads its identity, standing instructions, and current state. What is this routine, and what does it solve?

- **A.** A boot sequence: it removes cold starts by making stored state present from the first message  ✅
- **B.** A warmup pass: it primes the model's attention layers so early responses match late quality
- **C.** A health check: it verifies storage connectivity so memory reads cannot fail mid-conversation
- **D.** A context flush: it clears stale leftovers from prior sessions before fresh instructions load

> **Answer:** A

### Q10. A builder studies how the production agent Bertha starts every session identically, with the same identity and current state loaded. What advantage does that pattern deliver?

- **A.** It lowers token spend, since a fixed startup block is cached by the provider and billed one time
- **B.** It removes the need for long-term storage, since each session regenerates state from instructions
- **C.** It guarantees deterministic outputs, since identical boots force identical reasoning paths
- **D.** It makes the agent wake consistent and current every session, so users never feel a cold start  ✅

> **Answer:** D

### Q11. One discipline decides what enters the window and in what shape; another decides what leaves the window and survives. Which pairing is right?

- **A.** Context engineering governs the window's contents; memory systems govern what persists outside  ✅
- **B.** Memory systems govern the window's contents; context engineering governs long-term persistence
- **C.** Both jobs belong to context engineering; memory systems only pick the database technology used
- **D.** Both jobs belong to memory systems; context engineering only compresses text to fit the limits

> **Answer:** A

### Q12. An agent saves every full transcript forever and retrieval quality keeps getting worse. What design principle is being violated?

- **A.** Selectivity: persist what is expensive to lose, not everything; a total archive is a landfill  ✅
- **B.** Durability: transcripts belong in cold storage tiers where growth never affects retrieval speed
- **C.** Normalization: transcripts should be split across relational tables before retrieval happens
- **D.** Recency: older transcripts should simply rank lower, keeping unlimited archives workable

> **Answer:** A

### Q13. Your agent can fetch the current exchange rate from an API in milliseconds. A teammate wants to persist each rate to the memory store. What is the right call?

- **A.** Persist it, because any value the agent has ever seen belongs in memory for future auditing
- **B.** Skip it: state that is cheap to re-derive fresh does not earn a place in persistent memory  ✅
- **C.** Persist it, but only in the vector store where stale numeric values cannot mislead retrieval
- **D.** Skip it for now, but schedule a nightly job snapshotting every rate in case the API vanishes

> **Answer:** B

### Q14. A builder has one hour to improve memory and two candidate items: an internal cache value, and the client details users keep getting re-asked for. Which persists first, and why?

- **A.** The cache value, because internal state failures corrupt sessions more deeply than re-asking
- **B.** Both equally, because a memory layer should treat all state uniformly to keep the schema simple
- **C.** The client details: user-visible forgetting is the highest-priority state to persist in an agent  ✅
- **D.** The cache value, because users tolerate repeated questions far longer than they tolerate slow responses

> **Answer:** C

### Q15. An agent stores its deploy process as a pile of past deploy events and re-reads them to figure out steps each time. What is wrong here?

- **A.** Nothing: procedures learned from real events stay more accurate than rules written by hand once
- **B.** The events should live in the vector store instead, where similarity search can reconstruct the step order
- **C.** The pile should be capped at ten events, since older deploys stop matching the current process
- **D.** A method is procedural memory; stored as events, the agent relives history instead of knowing it  ✅

> **Answer:** D

### Q16. 'Just keep everything in the context window; it holds plenty,' a teammate argues. Why does this fail as a memory strategy?

- **A.** Windows compress older tokens automatically, so early facts come back in a degraded and unreliable form
- **B.** The window is working memory rented per session; it resets, so storage must live outside the model  ✅
- **C.** Window contents are visible to the model provider, so persistent client facts create legal risk
- **D.** Large windows raise latency sharply, so a full window makes every agent response slower each turn

> **Answer:** B

### Q17. An agent has a rich, well-modeled database of client facts, yet every session opens with it knowing nothing. What is the most likely missing piece?

- **A.** A boot sequence: without a startup load, an agent with a full database still wakes up blank  ✅
- **B.** An index: without one, startup queries silently time out and context builds without any data
- **C.** A larger window: the stored facts exceed the token budget, so the loader skips all of them
- **D.** Write permissions: the agent reads its store but cannot refresh it, so state slowly goes stale

> **Answer:** A

### Q18. A client's project status changes daily, and the memory store still shows a value written three weeks ago. What did the design get wrong?

- **A.** Volatile state was written to episodic memory, where entries are immutable by definition
- **B.** Volatile state got a write-once record when it needed an update path built into the design  ✅
- **C.** Status data was persisted at all, when daily values should live only inside session context
- **D.** The store lacked time-based decay, which would have deleted the stale value automatically

> **Answer:** B

### Q19. Before building a memory layer, a builder wants a map of what the agent currently loses at session end. What should they direct AI to do first?

- **A.** Generate the storage schema first, since the table design will reveal which state matters most
- **B.** Interview users about their frustrations, since perceived forgetting matters more than state
- **C.** Log all token flows for one week, since window usage statistics identify what state exists
- **D.** Audit the design, list every piece of state lost at session end, and rank each by cost of loss  ✅

> **Answer:** D

### Q20. A vibecoder is adding memory to their agent stack. What is their actual role in getting the memory layer built?

- **A.** Write the storage layer entirely by hand, since memory code is too foundational to delegate to AI
- **B.** Direct AI to design and implement the layer, then judge the decisions and verify the behavior  ✅
- **C.** Buy a managed memory product, since building custom persistence is beyond any solo builder
- **D.** Copy a reference implementation unchanged, since proven memory code should never be adapted

> **Answer:** B

### Q21. One record says 'the client said on May 2 they want weekly calls.' Another says 'the client wants weekly calls.' How do these differ?

- **A.** They are duplicates: the second is just a compressed copy and one of them should be deleted
- **B.** The first is procedural since it involves scheduling work; the second is semantic since it states a fact
- **C.** The first is episodic, anchored to a moment; the second is semantic, the truth extracted from it  ✅
- **D.** The first is semantic since it carries detail; the second is episodic since it lost its date

> **Answer:** C

### Q22. A team ships an agent with no memory layer, planning to add one once users ask for it. What is wrong with that sequencing?

- **A.** Nothing: memory adds cost and complexity, so demand should always be proven before building
- **B.** It is late: forgetting complaints arrive after trust is damaged; design memory in from day one  ✅
- **C.** It is fine only if transcripts are archived, since a memory layer can be backfilled from logs
- **D.** It is premature either way: memory belongs only in multi-agent systems with shared state needs

> **Answer:** B

### Q23. A bookkeeping firm's agent re-asks every client for their entity type in every conversation. Which fix addresses the root cause?

- **A.** Raise the context limit so longer conversations keep the entity type in view until session end
- **B.** Add a system prompt line telling the agent to ask for the entity type only once per conversation
- **C.** Persist per-client semantic facts like entity type and load them into context at session start  ✅
- **D.** Fine-tune the model on past transcripts so entity types become part of its trained knowledge

> **Answer:** C

### Q24. 'What did we decide?', 'What is true about this client?', and 'How do we do this here?' map to which memory types, in order?

- **A.** Episodic, then semantic, then procedural: events, facts, and methods answer different questions  ✅
- **B.** Semantic, then episodic, then procedural: facts come first because decisions are stored as facts
- **C.** Procedural, then semantic, then episodic: decisions are rules, truths are facts, methods are logs
- **D.** Episodic, then procedural, then semantic: client truths are methods and working habits are facts

> **Answer:** A

### Q25. Strip away the tooling and schemas. What is the governing principle that makes an agent remember anything at all?

- **A.** Memory emerges once the model is large enough, since scale gives frontier models durable recall
- **B.** Memory is a vendor feature: choosing a platform with session persistence removes the problem
- **C.** Memory is a loop you build deliberately: write state out, store it, load it back; none persists alone  ✅
- **D.** Memory is an archive problem: keep every transcript forever and any future question can be answered later

> **Answer:** C


---
_Take it in the browser: https://the-faction.mn.co/posts/107155290_
