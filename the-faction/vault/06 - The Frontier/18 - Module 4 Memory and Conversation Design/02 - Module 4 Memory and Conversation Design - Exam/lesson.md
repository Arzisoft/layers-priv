---
course: "The Frontier"
module: "Module 4: Memory and Conversation Design"
lesson: "Module 4: Memory and Conversation Design — Exam"
type: "course_quiz"
post_id: 106578136
space_id: 24391596
source: "https://the-faction.mn.co/posts/106578136"
updated: "2026-08-28T16:33:28Z"
---

# Module 4: Memory and Conversation Design — Exam

> Exam for **Module 4: Memory and Conversation Design** (The Frontier) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. A client asks where the model keeps what it learned during yesterday's conversation, so they can inspect it. What does the builder have to explain?

- **A.** It lives in the provider's session store, which enterprise accounts can inspect through an admin API console
- **B.** It is folded into the model's weights overnight, which is why its answers improve across days
- **C.** It sits in a hidden scratchpad the model maintains per user, readable only by the model itself
- **D.** Nowhere: the model retains nothing between calls, so the app must re-supply whatever should persist  ✅

> **Answer:** D

### Q2. A new builder asks what short-term memory actually is under the hood of a chat assistant. Which answer is accurate?

- **A.** A fast in-memory database the provider hosts beside the model for the length of a session
- **B.** The model's attention cache, which carries over between calls within the same minute
- **C.** The recent conversation history, replayed back into the window on every single call  ✅
- **D.** A rolling summary the provider generates automatically once chats pass ten messages

> **Answer:** C

### Q3. The same builder asks how long-term memory differs. What separates it from history replay?

- **A.** It is deliberate and selective: stored outside the window, and injected only when the system decides  ✅
- **B.** It is automatic: models gradually promote important history into permanent internal storage
- **C.** It is larger but otherwise identical: the full transcript archive replayed on every call
- **D.** It is provider-managed: enabled by a flag, after which recall happens without app logic

> **Answer:** A

### Q4. A production assistant slows, costs creep up, and answers drift as conversations stretch on. Of the usual suspects, which is the most common culprit in the field?

- **A.** Embedding drift, where the vector store gradually returns worse passages as the index ages
- **B.** Unbounded history replay, which quietly grows until it dominates the entire window  ✅
- **C.** Provider throttling, which reroutes long sessions to smaller models during peak hours
- **D.** Token inflation, where the tokenizer emits progressively more tokens per word over time

> **Answer:** B

### Q5. After compression is added to a long-running chat, what should the window carry into each call?

- **A.** A digest of the distant past, recent messages verbatim, and the current user message  ✅
- **B.** Only the current message, since a well-designed system needs no conversational carryover
- **C.** The full transcript compressed uniformly, every message shortened by the same ratio
- **D.** Recent messages summarized tightly, with the oldest messages preserved word for word

> **Answer:** A

### Q6. Two compression jobs run on the same transcript. One keeps the pleasantries and drops the agreed budget; the other does the reverse. What defines the good one?

- **A.** Neither: compression should never drop content, only shorten each message proportionally
- **B.** The first, because social tone carries the relationship context that models need most
- **C.** Whichever produces the shorter digest, since the point of compression is saving tokens
- **D.** The second: losing chatter is fine, but decisions, facts, and commitments must survive  ✅

> **Answer:** D

### Q7. A builder is writing a memory policy document before implementation. Which three questions form its backbone?

- **A.** Which database to use, which schema to define, and which backup cadence to adopt
- **B.** What to remember, what to forget, and how each remembered item gets recalled  ✅
- **C.** Which model to call, which window size to buy, and which provider tier to select
- **D.** How much memory costs, who owns the data, and how long retention laws allow it

> **Answer:** B

### Q8. During a session a user shares their industry, approves a budget, mentions the weather, and asks an aside that gets resolved. Which items belong in long-term storage?

- **A.** All four, since a complete record protects the builder if disputes ever surface later
- **B.** The weather remark and the aside, since small details personalize future conversations
- **C.** The industry and the approved budget: durable facts and decisions earn persistence  ✅
- **D.** None, until the user explicitly marks specific messages as worth remembering

> **Answer:** C

### Q9. A memory store is filling with greetings, dead-end tangents, and clarifications already resolved. Per the policy this module teaches, what should happen to this class of content?

- **A.** Keep it but compress it monthly, so nothing is ever truly lost from the record
- **B.** Move it to cold storage where it can be recalled by an explicit administrator query
- **C.** Forget it: this is exactly the category a memory policy is designed to exclude  ✅
- **D.** Tag it low-priority and inject it only when the window has spare space available

> **Answer:** C

### Q10. A builder has a small user profile, a large archive of session summaries, and a fresh session starting. Which recall design matches this module's guidance?

- **A.** Inject the profile wholesale, retrieve archive summaries by relevance, and add the last summary at session start  ✅
- **B.** Inject everything available at session start, and let the window architecture truncate whatever happens to overflow
- **C.** Retrieve the profile by relevance like any other memory, and inject the whole archive wholesale for safety
- **D.** Hold all memory back until the user asks about the past, then load the entire summary archive at once

> **Answer:** A

### Q11. One product runs single anonymous tax estimates; another manages months-long client projects. How should their memory architectures differ?

- **A.** Both need persistent memory, since any user might return someday with a follow-up question
- **B.** Both should stay session-only, since persistence adds liability no product truly needs
- **C.** The tax tool needs persistent profiles for compliance; the project tool can stay session-only
- **D.** The tax tool fits session memory that dies with the chat; the project tool justifies persistence  ✅

> **Answer:** D

### Q12. A builder is adding an assistant to a sensitive one-off intake flow and asks whether to wire up persistent memory since the infrastructure already exists. What is the right call?

- **A.** Yes: memory is nearly free to add, and unused profiles cause no harm sitting in storage
- **B.** No: a one-off, privacy-sensitive flow is the textbook case for session-only memory  ✅
- **C.** Yes, but encrypt the profiles, which removes the privacy concern that argues against it
- **D.** No, because persistent memory requires a paid provider tier the project cannot justify

> **Answer:** B

### Q13. An assistant confidently cites a campaign budget that the client cut in half three weeks ago. The stored summary was accurate when written. What is the structural fix?

- **A.** Date every memory, label it as of its date on injection, and give updates a path to supersede it  ✅
- **B.** Stop storing numeric figures entirely, since numbers are the only category that goes stale
- **C.** Shorten the memory retention window to only seven days so stale facts age out very quickly
- **D.** Instruct the model to distrust every stored memory and re-verify each one with the user before use

> **Answer:** A

### Q14. At session end, a system extracts facts and decisions from the transcript into the user profile. The builder wants a safeguard on this step. Which practice fits?

- **A.** Run extraction twice with different prompts and store only the overlapping items from both
- **B.** Show the diff of proposed profile changes for review before they are saved permanently  ✅
- **C.** Extract only on sessions longer than twenty messages, where facts are most reliable
- **D.** Skip the safeguard, since extraction errors wash out over many sessions of averaging

> **Answer:** B

### Q15. Stored memories are being pasted into the window right beside the live conversation, unlabeled. The model has started replying to last month's questions. What practice is missing?

- **A.** Compression, which would shrink old memories until the model stopped noticing them
- **B.** Expiry, which would have deleted the old questions before they reached the window
- **C.** Encryption, which prevents stored content from being read back into conversations
- **D.** Labeling: injected memory must be marked as stored context, distinct from live dialogue  ✅

> **Answer:** D

### Q16. A memory store has grown to thousands of entries, and only a handful matter for any given query. What recall mechanism does this module prescribe?

- **A.** Retrieval over the memories, injecting only what is relevant to the current query  ✅
- **B.** Chronological injection of the most recent hundred entries on every single call
- **C.** A scheduled nightly job that condenses the whole store into one master summary
- **D.** Random sampling of entries per call, which surfaces forgotten context over time

> **Answer:** A

### Q17. A team decides to store every message from every session, reasoning that storage is cheap. Six months later, recall quality has collapsed. Why?

- **A.** The store exceeded the vector database's document limit and silently stopped indexing
- **B.** Old sessions expired and took adjacent entries with them through cascade deletion
- **C.** Storing everything made recall a search through noise instead of a lookup of signal  ✅
- **D.** Users changed topics over time, invalidating embeddings computed on older entries

> **Answer:** C

### Q18. A builder directs AI to implement compression and must specify when it fires and what it does. Which specification matches the standard loop?

- **A.** When history crosses a token threshold, summarize the oldest portion and replace those messages  ✅
- **B.** After every user message, regenerate a fresh summary of the entire conversation from the beginning
- **C.** When the session ends, compress the full transcript and delete the original messages permanently
- **D.** Whenever the model seems confused, pause the conversation and ask the user for a brief recap

> **Answer:** A

### Q19. Two proposals are on the table: session-only memory, or persistent profiles with dates, update paths, and review steps. The client asks why the second costs more. What is the honest answer?

- **A.** Persistent storage prices scale with tokens, and profiles are token-heavy by nature
- **B.** Persistence carries real obligations: accuracy and staleness upkeep are ongoing work  ✅
- **C.** It should not: persistence is a checkbox, and the extra line items are padding
- **D.** Providers charge licensing fees for cross-session recall on business accounts

> **Answer:** B

### Q20. A profile still lists a preference the user stated in March. It is now well past the 90-day mark the builder set. What should the system do with it?

- **A.** Delete it silently, since anything past the review age is more risk than value
- **B.** Inject it as current fact until the user complains, which signals true staleness
- **C.** Promote it to permanent status, since surviving 90 days proves it matters
- **D.** Flag it for confirmation rather than injecting it as if it were still current  ✅

> **Answer:** D

### Q21. An assistant with sharp answers keeps forgetting the client's name by message thirty, and the client calls the whole product broken. What does this reaction teach about memory?

- **A.** Users conflate distinct systems: name recall and answer quality are unrelated components
- **B.** The client is misjudging the product, and the fix is expectation-setting in onboarding
- **C.** Users experience memory as intelligence, so forgetting reads as failure no matter the answers  ✅
- **D.** Names are uniquely hard for models, and the client happened to hit a known edge case

> **Answer:** C

### Q22. A client changes the project deadline in session twelve. The old deadline already sits in memory. What should the memory system do with the new one?

- **A.** Supersede: a new deadline overwrites the old, which stops being injected as current  ✅
- **B.** Append: both deadlines remain side by side so the model can weigh the complete record
- **C.** Hold both until the client confirms twice, since single mentions are unreliable
- **D.** Ignore it until session end, when extraction naturally picks up recent changes

> **Answer:** A

### Q23. A builder assumes memory requires an exotic new stack and budgets weeks for infrastructure. What does this module say about the actual requirements?

- **A.** Memory needs a dedicated graph database, since the relationships between facts drive recall quality
- **B.** Memory needs realtime streaming infrastructure to capture facts the moment they appear
- **C.** Memory needs a fine-tuned model, since base models cannot integrate injected profiles
- **D.** Ordinary parts suffice: summarization calls, a simple database, and the existing retrieval stack  ✅

> **Answer:** D

### Q24. A teammate points at a provider's built-in memory feature and asks why the product needs its own memory layer at all. What is the strongest answer?

- **A.** Provider memory is slower, since recall must round-trip through the provider's network each call
- **B.** Provider features show the pattern but give no control over what your product remembers  ✅
- **C.** Provider memory expires monthly, which no business application could ever tolerate
- **D.** Provider features only remember prompts, never the model's own generated responses

> **Answer:** B

### Q25. One principle organizes everything in this module, from compression to profiles to recall. Which statement captures it?

- **A.** Memory is a storage problem: choose the right database and the rest follows naturally
- **B.** Memory is a model capability: pick a model with strong recall and design disappears
- **C.** Memory is context management: the craft is choosing what re-enters the window, and when  ✅
- **D.** Memory is a compliance artifact: store what regulation requires and surface it on demand

> **Answer:** C


---
_Take it in the browser: https://the-faction.mn.co/posts/106578136_
