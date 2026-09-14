---
course: "The Frontier"
module: "Module 4: Memory Architecture: Retrieval, Indexing, and Search"
lesson: "Module 4: Memory Architecture: Retrieval, Indexing, and Search — Exam"
type: "course_quiz"
post_id: 107155314
space_id: 24391596
source: "https://the-faction.mn.co/posts/107155314"
updated: "2026-09-10T19:36:35Z"
---

# Module 4: Memory Architecture: Retrieval, Indexing, and Search — Exam

> Exam for **Module 4: Memory Architecture: Retrieval, Indexing, and Search** (The Frontier) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. An agent holds five thousand memories and window space for about five. What does that constraint make retrieval, fundamentally?

- **A.** A caching problem: keep the most used memories warm so fetches cost nothing at run time
- **B.** A storage problem: with better schemas, the right memories would surface on their own
- **C.** A scoring problem: rank everything known and admit only what earns entry to the window  ✅
- **D.** A compression problem: shrink memories until all five thousand fit inside the window

> **Answer:** C

### Q2. A user types 'the client is unhappy about timelines.' The store holds a March complaint about delays, worded completely differently. What retrieves it?

- **A.** A keyword index, since 'timelines' and 'delays' share a word stem that full-text search links
- **B.** A date filter, since complaints cluster in time and March sits inside the default range
- **C.** A subject join, since both records reference the same client and join paths find that
- **D.** Embedding search: both texts land near each other in vector space despite sharing no words  ✅

> **Answer:** D

### Q3. A team wants last week's decision to outrank last year's on the same topic, without deleting anything old. Which mechanism does this?

- **A.** An archive tier: memories older than ninety days move to storage that queries skip
- **B.** Recency scoring: a decay term lowers scores by age, so fresh outranks stale naturally  ✅
- **C.** A versioning rule: new memories overwrite old ones on the same topic automatically
- **D.** Window pinning: recent decisions stay pinned inside context, so ranking never sees them

> **Answer:** B

### Q4. Why does production memory scoring blend similarity, recency, and importance rather than trusting any one of them?

- **A.** Blending keeps a single signal from dominance; each covers the others' blind spots  ✅
- **B.** Blending is cheaper: three light signals cost less to compute than one accurate one
- **C.** Blending is required by pgvector, whose ranking API expects three weighted inputs
- **D.** Blending guarantees deterministic ranking, which single-signal scoring cannot offer

> **Answer:** A

### Q5. A retrieval design runs structured filters first, then merges keyword results with vector results before ranking. What is this pattern called and why use it?

- **A.** Cascade retrieval: each stage discards half of the candidate set until one memory remains
- **B.** Ensemble search: several models embed the query and vote on the final result order
- **C.** Federated search: each store is queried separately and results interleave by score
- **D.** Hybrid retrieval: exact identifiers and paraphrased meaning each get the match they need  ✅

> **Answer:** D

### Q6. A builder who knows RAG asks how agent memory retrieval differs. What is the honest answer?

- **A.** It is RAG pointed at the agent's own past: same embeddings and ranking, different corpus  ✅
- **B.** It is unrelated: RAG grounds answers in documents, while memory works without retrieval
- **C.** It is simpler: memory skips embeddings entirely because agents know their own history
- **D.** It is harder: memory requires a dedicated vector database while RAG runs on Postgres

> **Answer:** A

### Q7. Ordering the steps of a retrieval pass at the top of an agent turn, which sequence is correct?

- **A.** Score all memories, filter the winners, embed the query, then format for the window
- **B.** Build the query, filter candidates, score them, admit under budget, format for the window  ✅
- **C.** Admit recent memories, score them in the window, and filter out any the model ignores
- **D.** Format all stored memories, embed each one, then admit whichever fits the token allowance

> **Answer:** B

### Q8. Two builders debate running the ranker across the entire memory store every turn. What does filtering first actually buy?

- **A.** Nothing at small scale, but it prevents the vector index from fragmenting as data grows
- **B.** Lower storage costs, since filtered candidates can be cached and older rows compressed
- **C.** Speed and quality: ranking runs over relevant candidates instead of drowning in noise  ✅
- **D.** Simpler code, since SQL filters replace the scoring function for most agent queries

> **Answer:** C

### Q9. Scoring is done and thirty memories rank well. The token allowance for memory covers about five. What does a disciplined admit step do?

- **A.** Admits all thirty in compressed form, since every well-ranked memory carries signal
- **B.** Takes the top results that fit the reserved allowance and leaves the rest in storage  ✅
- **C.** Rotates through the thirty across turns, so each memory gets window time eventually
- **D.** Asks the model which memories it wants, since the consumer knows best about what helps

> **Answer:** B

### Q10. An admitted memory enters the window as a raw JSON row: braces, field names, nulls and all. What does this cost?

- **A.** Nothing at all, since models parse JSON natively and structure helps them trust the record
- **B.** Latency only: JSON tokens stream slower but carry the same meaning to the model
- **C.** Tokens and clarity: a compact statement with source and date serves the model better  ✅
- **D.** Security: raw rows may leak internal IDs, which matters more than any token waste

> **Answer:** C

### Q11. A retrieval path filters on subject, orders by timestamp, and ranks by embedding. Which index set does this need?

- **A.** A single covering index spanning all the columns, since one composite outperforms several
- **B.** B-tree indexes on subject and timestamp, plus a vector index on the embedding column  ✅
- **C.** Only the vector index, since similarity ranking makes other lookups unnecessary
- **D.** Full-text indexes on content, since text search underlies all three access styles

> **Answer:** B

### Q12. Retrieval keeps surfacing a vivid memory from last year over a quiet decision made yesterday. The scorer uses cosine similarity only. Diagnosis?

- **A.** The embedding model is stale and re-embedding the full store would fix the ordering
- **B.** The old memory is duplicated, and deduplication would let the new one surface
- **C.** Similarity alone ignores age: without recency in the blend, stale can outrank fresh  ✅
- **D.** The new decision embedded poorly, and richer wording at write time would fix it

> **Answer:** C

### Q13. An agent must find invoice INV-20447. Embedding search returns invoices with similar amounts but wrong numbers. Why, and what fixes it?

- **A.** The vector index is corrupt; rebuilding it restores exact matching for identifiers
- **B.** The query embedded too short; padding it with context would sharpen the match
- **C.** Embeddings mangle identifiers: exact strings want keyword or filtered matching  ✅
- **D.** The invoices need their own collection, so similarity runs only across invoices

> **Answer:** C

### Q14. An agent admits fifteen memories every turn. Responses get vaguer and the conversation itself keeps getting truncated. What went wrong?

- **A.** The memories were formatted too compactly, starving the model of usable detail
- **B.** Fifteen is fine, but they entered unordered, and unordered context reads as noise
- **C.** The model's attention span caps at ten passages, so five memories went unread
- **D.** No memory budget: over-admission crowded out the conversation the window is for  ✅

> **Answer:** D

### Q15. Retrieval was instant in the demo. At fifty thousand memories, every query takes seconds. The embedding column was never indexed. What is happening?

- **A.** Every query full-scans the vector column; a pgvector index turns scans into lookups  ✅
- **B.** Postgres is swapping to disk, and more memory on the instance would mask the issue
- **C.** Cosine similarity slows quadratically with row count, an unavoidable property of it
- **D.** The embeddings drifted apart over time, making nearest-neighbor search work harder

> **Answer:** A

### Q16. After tuning, fresh memories still lose to stale ones on similar topics. Recency uses a 90-day half-life with a small weight. What adjustment fits?

- **A.** Remove similarity from the blend, since meaning matching is what favors old records
- **B.** Re-embed old memories with a weaker model so their similarity scores drop naturally
- **C.** Delete memories older than the half-life, since decay clearly is not strong enough
- **D.** Raise the recency weight or shorten the half-life so freshness cuts through sooner  ✅

> **Answer:** D

### Q17. A standing decision keeps losing rank to chatty recent memories that mention the same words. Which signal is missing from the blend?

- **A.** Importance: a stored weight for critical memories lets them beat casual mentions  ✅
- **B.** Frequency: memories referenced often should accumulate rank with every citation
- **C.** Length: substantive memories run longer, and longer content deserves scoring credit
- **D.** Sentiment: decisions carry neutral tone, and neutral text should outrank casual talk

> **Answer:** A

### Q18. A scoring config sets a 30-day half-life on recency. What does that mean for a memory's score?

- **A.** Memories older than 30 days are excluded from ranking until a user asks for history
- **B.** The recency term halves every 30 days of age, fading old memories without deleting them  ✅
- **C.** Scores reset every 30 days, giving all memories an equal footing at each cycle start
- **D.** A memory must be retrieved at least once per 30 days or it gets archived automatically

> **Answer:** B

### Q19. A team upgrades embedding models a year in. Which write-time habit makes the migration manageable?

- **A.** Storing the embedding model's name with each vector, so re-embedding is trackable  ✅
- **B.** Storing each vector twice at two different dimensions, so either model can read them
- **C.** Keeping vectors immutable, since mixing model outputs in one column is harmless
- **D.** Hashing content into the vector ID, so unchanged text can skip re-embedding runs

> **Answer:** A

### Q20. A builder weighs moving embeddings to a dedicated vector service while filters stay in Postgres. What cost should they weigh first?

- **A.** Vector services cannot store metadata, so importance weights would have to be dropped
- **B.** Postgres locks its tables during external queries, stalling writes while vectors rank
- **C.** Embedding formats differ per vendor, so migration means re-embedding the full store
- **D.** Every hybrid query gains a network hop, since ranking and filtering now live apart  ✅

> **Answer:** D

### Q21. Retrieval latency is climbing in production. In what order should a builder investigate?

- **A.** Add caching first, then shrink embeddings, then reduce the memory store's row count
- **B.** Scale the database first, since hardware fixes buy time to investigate the real cause
- **C.** Move to a vector service first, then revisit indexes if the migration disappoints
- **D.** Indexes first, filter scope second, heavier infrastructure only after both check out  ✅

> **Answer:** D

### Q22. After adding subject filtering to a forty-project agent, answers arrive noticeably faster. What explains the speedup?

- **A.** Filtered queries skip the scoring function, returning candidates in storage order
- **B.** Postgres caches per-subject results, so repeat questions bypass ranking entirely
- **C.** Ranking now runs over one project's candidates instead of the whole store's rows  ✅
- **D.** Subject filters shrink each embedding, making every similarity comparison cheaper

> **Answer:** C

### Q23. A user asks about 'keeping the launch on schedule' and the relevant memory says 'deadline risk flagged for the release.' When is embedding search the right tool?

- **A.** Exactly here: the need is conceptual and worded differently from what was stored  ✅
- **B.** Never here: schedule language is too vague for vectors to embed distinctively
- **C.** Only if keyword search runs first and returns nothing, as a fallback of last resort
- **D.** Only when both texts exceed a length threshold that makes embeddings stable

> **Answer:** A

### Q24. At the start of a retrieval pass, what does building the query actually involve?

- **A.** Selecting the top memories by importance so scoring has a warm starting set
- **B.** Embedding the current situation and extracting hard filters like subject and type  ✅
- **C.** Asking the model to write SQL against the memories table from the conversation
- **D.** Loading the boot sequence state so retrieval knows which of the memories exist already

> **Answer:** B

### Q25. A mentor sums up this entire retrieval layer in one sentence. Which sentence is it?

- **A.** Stored memory the agent cannot surface at the right moment might as well not exist  ✅
- **B.** Store less and you will retrieve better, since small stores cannot return bad results
- **C.** Retrieval is a solved problem once embeddings are enabled on the memory store
- **D.** The best retrieval system is the one with the most signals blended into its score

> **Answer:** A


---
_Take it in the browser: https://the-faction.mn.co/posts/107155314_
