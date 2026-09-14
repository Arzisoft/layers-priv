---
course: "The Frontier"
module: "Module 2: Short-Term Memory: Conversation and Session State"
lesson: "Module 2: Short-Term Memory: Conversation and Session State — Exam"
type: "course_quiz"
post_id: 107155295
space_id: 24391596
source: "https://the-faction.mn.co/posts/107155295"
updated: "2026-09-10T19:34:31Z"
---

# Module 2: Short-Term Memory: Conversation and Session State — Exam

> Exam for **Module 2: Short-Term Memory: Conversation and Session State** (The Frontier) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. A quickstart tutorial appends every turn to history forever, and a builder ships it unchanged. What principle of short-term memory does this ignore?

- **A.** History should live in a database from the first turn so the window never carries any of it
- **B.** History is a managed, budgeted asset: each replayed turn must earn its place, turn by turn  ✅
- **C.** History should be summarized on every turn so the window holds only compressed content
- **D.** History belongs to the model provider, whose session tools handle retention automatically

> **Answer:** B

### Q2. A team notices each conversation turn costs more than the one before, even though user messages stay short. What is driving the climb?

- **A.** The full history is replayed into the window every call, so input tokens grow with each turn  ✅
- **B.** The model raises per-token pricing as context fills, charging premium rates past the midpoint
- **C.** Tool outputs accumulate in the provider's cache, and cache reads bill higher than fresh input
- **D.** Longer conversations trigger a bigger model tier automatically, which bills at a higher rate

> **Answer:** A

### Q3. An agent tracks its current task only as a sentence buried in conversation prose. Mid-session, it starts working on the wrong thing. What was the design flaw?

- **A.** The task sentence used ambiguous wording, so a clearer phrasing in history would have held up
- **B.** The task should have been repeated by the user every few turns to keep it fresh in the window
- **C.** Task status is structured session state; stored as loose text it can be compressed or misread  ✅
- **D.** The system prompt should carry the task, since instructions there are immune from any drift

> **Answer:** C

### Q4. A builder asks what the simplest history policy actually does. Which description of a sliding window is accurate?

- **A.** It ranks turns by importance scores and keeps whichever turns score above a set threshold
- **B.** It compresses the oldest turns into a summary block while recent turns remain verbatim
- **C.** It splits history across parallel threads and reloads whichever thread matches the topic
- **D.** It keeps the most recent N turns verbatim and silently drops the oldest as new ones arrive  ✅

> **Answer:** D

### Q5. In turn two, a client says the budget cap is firm. At turn 30, an agent using a plain 12-turn sliding window proposes something over budget. Why?

- **A.** The window is blind: the budget slid out of view, so the constraint no longer exists to it  ✅
- **B.** The model weighted recent enthusiasm over old caution, a known bias in long conversations
- **C.** The budget was stored as a pinned item, but pins expire after a fixed number of turns pass
- **D.** Sliding windows keep oldest turns and drop recent ones, so late context was the part missing

> **Answer:** A

### Q6. A builder is specifying a running-summary strategy and asks what the summary must never lose. What belongs on that list?

- **A.** The emotional tone of each exchange, since rapport is what long conversations mostly carry
- **B.** Verbatim wording of every user message, since paraphrase always introduces subtle errors
- **C.** Timestamps for every turn, since ordering is what keeps a compressed history trustworthy
- **D.** Decisions, constraints, and open issues: the commitments that govern the rest of the work  ✅

> **Answer:** D

### Q7. 'Just summarize everything, then nothing gets lost,' a teammate says. What tradeoff does summarization actually carry?

- **A.** It loses detail by design, and the summarization calls themselves cost real tokens to run  ✅
- **B.** It doubles storage needs, since both the summary and transcript must be kept in the window
- **C.** It only works on conversations under ten turns, since longer inputs exceed summarizers
- **D.** It requires a second, larger model to write summaries, which most builders cannot access

> **Answer:** A

### Q8. A production agent's window holds three history layers working together. Which composition matches the hybrid pattern?

- **A.** Three parallel sliding windows of different sizes, voting on which turns should be retained
- **B.** A rolling summary of old turns, verbatim recent turns, and pinned items that never leave  ✅
- **C.** A full transcript, a compressed transcript, and a vector index over both for retrieval
- **D.** Structured state, the system prompt, and whichever past turns the user manually restores

> **Answer:** B

### Q9. A client's non-negotiable requirement was stated once, forty turns ago, and the agent still honors it verbatim. Which mechanism makes that possible?

- **A.** Pinning: marked items stay in the window verbatim regardless of age or compression passes  ✅
- **B.** Recency boosting: the assembly step re-ranks old turns upward when they contain keywords
- **C.** Session caching: the provider preserves early turns of every session in a reserved buffer
- **D.** Echoing: the agent quietly restates old constraints every few turns to keep them recent

> **Answer:** A

### Q10. During the session loop, when should the oldest verbatim turns get folded into the running summary?

- **A.** When a budget check shows history approaching its token allowance, not on a fixed rhythm  ✅
- **B.** After every single turn, so the verbatim layer stays as small as it can possibly be kept
- **C.** Only at session end, so the summary reflects the entire conversation in one clean pass
- **D.** Whenever the user goes idle, since pauses are the only safe moment to rewrite history

> **Answer:** A

### Q11. A builder keeps mixing up two container concepts while designing their app. What correctly separates a thread from a session?

- **A.** A thread is the model's context window; a session is the database row that mirrors it
- **B.** A thread contains one line of work; a session is one continuous run of interaction  ✅
- **C.** A thread is user-facing chat history; a session is the server log kept for debugging
- **D.** A thread belongs to one user; a session can be shared by several users at one time

> **Answer:** B

### Q12. An app lets users run several projects, each with many working conversations. Which state decision reflects sound scoping?

- **A.** Keep everything session-scoped, since sessions are the only container that truly exists
- **B.** Keep everything thread-scoped, so any conversation can reconstruct any other on demand
- **C.** Scope all state to the user account so every project sees every other project's variables
- **D.** Decide per item what is thread-scoped, session-scoped, or longer-lived, before storage  ✅

> **Answer:** D

### Q13. A session is ending. The conversation produced a durable client preference and a pile of routine chit-chat. What does a well-built session close do?

- **A.** Writes the entire transcript to long-term storage so nothing is ever lost at the boundary
- **B.** Hands the durable preference to the long-term layer while all the routine chatter expires  ✅
- **C.** Deletes everything, since the next session's boot sequence will rebuild state from scratch
- **D.** Emails the user a summary so they can paste the important parts into their next session

> **Answer:** B

### Q14. By turn 45 of a long intake, an agent quotes timelines contradicting what the client said in the first five turns. Where should a builder look first?

- **A.** Whether early turns slid out of the verbatim window without being pinned or summarized  ✅
- **B.** Whether the model temperature crept upward, making late responses drift from early ones
- **C.** Whether the client's early statements were ambiguous enough to justify both timelines
- **D.** Whether tool outputs mid-session overwrote the system prompt with conflicting content

> **Answer:** A

### Q15. After a compression pass, an agent's summary says 'client discussed project scope warmly' but the stated 10k budget is gone. What failure is this?

- **A.** A window failure: summaries live outside the window, so the budget was never at risk there
- **B.** A pinning failure: budgets are pins, and pins are the layer that summarization writes to
- **C.** Summarizing away commitments: the flavor survived while a governing number was destroyed  ✅
- **D.** A scoping failure: the budget belonged to a different thread than the one summarized

> **Answer:** C

### Q16. A code review finds an agent whose collected form variables exist only as sentences scattered through history. What is the reviewer's correct objection?

- **A.** Sentences are fine if each variable is restated every ten turns to survive window pressure
- **B.** The variables should be moved into the system prompt where they cannot be compressed
- **C.** History is acceptable storage, but each variable needs a timestamp to remain auditable
- **D.** Variables the agent must act on belong in structured state, not prose that can drop out  ✅

> **Answer:** D

### Q17. An agent runs a summarization pass after every single turn, and token spend on compression now rivals the conversation itself. What is the fix?

- **A.** Move summarization to a cheaper model and keep the every-turn rhythm, since it is safest
- **B.** Drop summarization entirely, since any strategy that costs tokens defeats its own purpose
- **C.** Run compression on thresholds: summarize when the budget check trips, not reflexively  ✅
- **D.** Cache summaries between turns so repeated passes are free after the first compression

> **Answer:** C

### Q18. A user runs three unrelated work streams in one thread, and the running summary now blends them into mush. What architectural rule was broken?

- **A.** Summaries must be written per-turn, since batch compression is what mixes topics together
- **B.** Each work stream needed its own session token so the model could tell the streams apart
- **C.** Each thread should contain one line of work; separate streams belong in separate threads  ✅
- **D.** The window needed to be larger, since blending only happens when history gets truncated

> **Answer:** C

### Q19. A builder's support widget handles conversations that never exceed eight short turns. How much history engineering does this app need?

- **A.** A full hybrid stack with pins and summaries, since production apps deserve real patterns
- **B.** None beyond plain full history: do not engineer machinery the conversation never needs  ✅
- **C.** At minimum a sliding window, since every app eventually meets a chat that overflows
- **D.** Structured state only, with history disabled, since short chats gain nothing from replay

> **Answer:** B

### Q20. Sessions in a journaling app run long, but losing an old detail costs little. The builder wants minimum machinery. What fits?

- **A.** The hybrid pattern, because long sessions always justify summaries and pinned constraints
- **B.** A sliding window alone: losses are tolerable here, so blindness is an acceptable price  ✅
- **C.** Full history with no policy, because journaling users expect every entry in the window
- **D.** A running summary alone, because compression is the only way long sessions stay cheap

> **Answer:** B

### Q21. A builder asks which items deserve pinning in their agent. What is the right selection rule?

- **A.** Pin the most recent turns, since recency is the best available proxy for what matters
- **B.** Pin tool outputs, since regenerated results are the most expensive content to reproduce
- **C.** Pin non-negotiables: constraints, identities, and standing corrections that govern work  ✅
- **D.** Pin nothing by default, since every pin permanently shrinks the space left for history

> **Answer:** C

### Q22. A vibecoder is directing AI to set up session storage in Supabase. Which layout matches the recommended default?

- **A.** One table per conversation, created dynamically, with the summary stored as its final row
- **B.** A single messages table for all users, with session boundaries inferred from timestamps
- **C.** A Redis hash per session mirrored into Postgres nightly, with summaries kept in Redis
- **D.** A sessions table, a messages table, and a JSONB column for structured state per session  ✅

> **Answer:** D

### Q23. 'Let's add Redis now so sessions will be fast later,' a teammate proposes on day one. What is the disciplined response?

- **A.** Agree, since retrofitting a cache after launch is riskier than carrying one from the start
- **B.** Agree, but scope Redis to summaries only, since those are the hottest data in any session
- **C.** Decline: caching layers belong at the framework level, not in application architecture
- **D.** Decline until session reads measurably become a latency problem; add Redis on evidence  ✅

> **Answer:** D

### Q24. After rebuilding its session layer with a hybrid history policy, an agency's intake agent got 40 percent cheaper per session. What explains the savings?

- **A.** Dead history stopped replaying: only summary, recent turns, and pins enter the window  ✅
- **B.** The provider discounts sessions that use summaries, pricing compressed context lower
- **C.** Shorter sessions: the rebuild cut conversations from sixty turns down to around twenty
- **D.** A smaller model became viable once history shrank, and the tier change drove the savings

> **Answer:** A

### Q25. Across sliding windows, summaries, and pins, one rule governs everything in short-term memory. What is it?

- **A.** Recent turns always outrank old ones, so any policy that favors recency will behave well
- **B.** Compression should be maximized, since the smallest window is always the cheapest one
- **C.** Every element in the window is there by policy, not accumulation; none stays by default  ✅
- **D.** History decisions belong to the framework, since hand-rolled policies rarely beat defaults

> **Answer:** C


---
_Take it in the browser: https://the-faction.mn.co/posts/107155295_
