---
course: "The Frontier"
module: "Module 5: Memory Management: Pruning, Summarization, and Decay"
lesson: "Module 5: Memory Management: Pruning, Summarization, and Decay — Exam"
type: "course_quiz"
post_id: 107155319
space_id: 24391596
source: "https://the-faction.mn.co/posts/107155319"
updated: "2026-09-10T19:37:17Z"
---

# Module 5: Memory Management: Pruning, Summarization, and Decay — Exam

> Exam for **Module 5: Memory Management: Pruning, Summarization, and Decay** (The Frontier) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. A store doubles in size and retrieval quality drops faster than the bill rises. Why does quality degrade ahead of cost?

- **A.** Databases slow nonlinearly with size, so ranking times out before budgets feel anything
- **B.** Every junk memory is a ranking candidate that can outrank a good one, so noise compounds  ✅
- **C.** Embedding drift accelerates in large stores, scattering old vectors away from queries
- **D.** Providers throttle heavy retrieval users, quietly degrading results before raising rates

> **Answer:** B

### Q2. A team wants to start deleting memories. What separates disciplined pruning from a cleanup spree?

- **A.** Pruning only ever touches episodic records, since facts and procedures must never be removed
- **B.** Pruning happens inside the model's context, while cleanups operate on the database itself
- **C.** Pruning requires user approval per record, while cleanups run in bulk on a maintenance day
- **D.** Pruning runs on rules you define, on a schedule, with logs of every removal it makes  ✅

> **Answer:** D

### Q3. Thirty related episodic records from May become one monthly summary; later, four monthly summaries become a quarterly one. What is this pattern?

- **A.** Cascade compaction: the database engine merges pages of old rows to reclaim physical storage
- **B.** Decay laddering: each summary tier applies a stronger decay rate than the tier before
- **C.** Snapshot rotation: summaries replace backups so old data survives in restore points
- **D.** Progressive summarization: staged compression trading detail for density, keeping the story  ✅

> **Answer:** D

### Q4. During summarization, a builder must choose what happens to the original records. What does the recommended pattern do, and why?

- **A.** Archive them: compression stays reversible, and detail is recoverable when it matters  ✅
- **B.** Delete them: keeping originals defeats the storage savings summarization exists for
- **C.** Re-embed them: summaries need fresh vectors, and originals supply the raw material
- **D.** Duplicate them: one copy backs the summary while the other copy keeps serving retrieval

> **Answer:** A

### Q5. A builder cannot hand-weight thousands of memories. How does workable importance scoring actually get assigned?

- **A.** Seed weights by memory type at write time, then let retrieval frequency adjust them  ✅
- **B.** Sample a hundred memories monthly and extrapolate their hand-set weights to the rest
- **C.** Let the model rate each memory during retrieval, storing whatever score it reports
- **D.** Derive weights from content length, since substantive memories tend to run longer

> **Answer:** A

### Q6. One memory keeps getting retrieved month after month; another has never been fetched. What does usage tell the maintenance layer?

- **A.** Nothing reliable: retrieval frequency mostly reflects query phrasing rather than memory value
- **B.** The popular memory is overexposed and should decay faster to give others window time
- **C.** Frequent retrieval argues for survival; the never-fetched record becomes a pruning flag  ✅
- **D.** Both should be summarized together so the storyline keeps popular and quiet records

> **Answer:** C

### Q7. Under time-based decay, what happens to a memory's score as months pass without any retrieval or citation?

- **A.** It holds steady until the pruning job runs, since only deletion ever changes scores
- **B.** It fades steadily, unless a retrieval, citation, or re-confirmation refreshes it  ✅
- **C.** It transfers to newer memories on the same subject, conserving total score per topic
- **D.** It inverts: long-unretrieved memories gain novelty weight so they resurface for review

> **Answer:** B

### Q8. A decayed memory and a pruned memory both stopped appearing in results. What distinguishes their states?

- **A.** The decayed one still exists and can compete again if refreshed; the pruned one is gone  ✅
- **B.** The decayed one moved to the archive tier; the pruned one stays in place at zero score
- **C.** Nothing practical: both require a manual restore before retrieval can see them again
- **D.** The decayed one lost only its embedding; the pruned one lost both its row and its metadata

> **Answer:** A

### Q9. An agent's memory bill grows every month while the value users get has flattened. What bends that curve?

- **A.** Negotiating volume pricing, since flat value means the workload is now predictable
- **B.** Freezing writes, since a store that stops growing stops costing anything further
- **C.** Switching providers, since embedding and storage margins vary widely between them
- **D.** Maintenance: dedupe, summarization, and pruning cut cost while protecting signal  ✅

> **Answer:** D

### Q10. A dedupe pass finds five near-identical copies of the same client fact. What does a well-built pass do with them?

- **A.** Merges all five into a new composite record and deletes the originals in one step
- **B.** Keeps the best-sourced copy, removes the rest, and logs every removal it performed  ✅
- **C.** Flags all five for the user to resolve, since automated deletion is never acceptable
- **D.** Re-embeds all five, since duplicate vectors are what make copies rank identically

> **Answer:** B

### Q11. A stored fact now has a newer version. The maintenance cycle's supersede step handles this how?

- **A.** Deletes the older fact immediately, since two versions of a fact poison retrieval
- **B.** Keeps both active and lets recency decay decide which one retrieval should favor
- **C.** Archives the old record and points history at the new one, keeping the lineage  ✅
- **D.** Merges both into one record with two dated values for the model to choose from

> **Answer:** C

### Q12. The last step of the monthly cycle reports row counts, storage size, and latency before and after. Why does this step exist?

- **A.** Compliance: storage deltas must be reported wherever client data gets deleted
- **B.** Proof: the cycle must demonstrate its value in numbers, or it will not keep running  ✅
- **C.** Billing: providers price maintenance windows against reported storage movement
- **D.** Safety: the report doubles as the undo log whenever a pruning rule proves too aggressive

> **Answer:** B

### Q13. A pruning rule deletes everything older than six months, and a year-old standing decision vanishes with the trivia. What was wrong with the rule?

- **A.** Six months is too short; an eighteen-month cutoff would have kept the decision safe
- **B.** Standing decisions belong in the system prompt, so pruning should never see them
- **C.** Age was the only signal: old chatter and old cornerstones got treated identically  ✅
- **D.** Deletion ran before summarization, so the decision missed its chance to compress

> **Answer:** C

### Q14. A summarization job compresses old records and destroys the originals in the same pass. What objection should a reviewer raise?

- **A.** It turns a compression decision into an irreversible one; archive originals instead  ✅
- **B.** It wastes compute, since destroyed originals cannot seed the next summary tier
- **C.** It breaks decay, since decay scores are computed against original timestamps
- **D.** It is fine if the summaries are validated first; the objection is only about the ordering

> **Answer:** A

### Q15. 'Every memory should get a hand-assigned importance weight,' a teammate proposes. What is the practical problem?

- **A.** Hand-set weights are biased toward recent memories, skewing retrieval unfairly
- **B.** If every record needs manual weight, none will get it; seed by type and learn  ✅
- **C.** Manual weights cannot be stored in Postgres without a dedicated scoring table
- **D.** Hand-set weights expire under decay, so the effort evaporates within months

> **Answer:** B

### Q16. A memory bug report comes in: a fact the agent once knew is missing. Pruning ran silently last week with no logs. What is the diagnostic problem?

- **A.** The fact cannot be restored, since unlogged deletions bypass the archive tier
- **B.** A pruned memory and a write that never happened are now indistinguishable  ✅
- **C.** The pruning job cannot be rerun safely until its rules are reverse-engineered
- **D.** The bug cannot be assigned, since no one owns unlogged maintenance failures

> **Answer:** B

### Q17. An embedding bill keeps climbing though the memory count is stable. Which pair of silent leaks fits that symptom?

- **A.** Oversized vectors and unindexed columns, which force re-ranking on every query
- **B.** Archive reads and dry-run passes, which each embed the records they touch
- **C.** Decay refreshes and importance updates, which re-embed each scored record
- **D.** Re-embedding unchanged content and embedding trivia never earning retrieval  ✅

> **Answer:** D

### Q18. Two teams face bloated stores. One runs an emergency purge; the other starts a monthly cycle. What outcome difference should be expected?

- **A.** Identical outcomes: what matters is deletion volume, not the schedule it follows
- **B.** The purge wins: one decisive cleanup beats recurring jobs that nibble at the edges
- **C.** The purge deletes carelessly in a panic; the cycle removes deliberately with logs  ✅
- **D.** The cycle wins on cost but loses on quality, since slow cleanup keeps noise longer

> **Answer:** C

### Q19. A new pruning job is ready for production. What does the deployment discipline require before it deletes anything?

- **A.** A full database backup taken immediately before each and every deletion run
- **B.** A signed review from whoever owns the schema, since deletions touch every table
- **C.** Dry-run mode until its logs look right twice in a row; only then live deletion  ✅
- **D.** A one-week pause after deploy, since fresh jobs misfire most in their first days

> **Answer:** C

### Q20. Costs are climbing while retrieval quality holds steady. Where does the decision framework point first?

- **A.** Ranking pollution: prune junk memories and tighten the admission budget per turn
- **B.** The model tier: quality headroom means a cheaper model can absorb the workload
- **C.** Session length: shorter conversations write fewer memories and cut costs upstream
- **D.** Embeddings and storage: dedupe, selective embedding, and archive tiers cut spend  ✅

> **Answer:** D

### Q21. Retrieval quality is falling while costs stay flat. Which target list matches that symptom?

- **A.** Prune junk, refresh importance scores, and tighten what gets admitted per turn  ✅
- **B.** Dedupe embeddings, downsize vectors, and shift old rows into colder storage
- **C.** Raise the token budget, lengthen summaries, and relax every admission filter
- **D.** Re-embed the store, rebuild all the indexes, and upgrade the database tier

> **Answer:** A

### Q22. After a year-long cleanup, an ops agent's store fell from 80,000 to 31,000 memories, yet nothing irreplaceable was lost. What made that possible?

- **A.** The deleted 49,000 were all duplicates, so every unique record survived untouched
- **B.** Users approved each deletion in batches, catching anything that still had value
- **C.** Summaries link back to archived originals, so compressed detail stays recoverable  ✅
- **D.** A full snapshot preceded the cleanup, so the old store exists as a restore point

> **Answer:** C

### Q23. A builder wants the monthly cycle to run without anyone remembering to trigger it. On the default stack, what carries this?

- **A.** A webhook from the model provider, fired whenever token usage crosses a threshold
- **B.** A standing agent session that stays awake and watches the calendar for month end
- **C.** The retrieval path itself, which runs maintenance inline once row counts trip
- **D.** Scheduled functions or cron on Supabase, running the cycle's jobs on a calendar  ✅

> **Answer:** D

### Q24. A memory has low importance, has never been retrieved, and keeps aging. Walk its expected path through the maintenance layer.

- **A.** Decay carries it below the score floor, and the scheduled pruning job removes it  ✅
- **B.** It gets summarized into the monthly rollup, since compression precedes deletion
- **C.** It stays forever, since only duplicates and superseded facts are ever removed
- **D.** Its importance is raised automatically, since neglected records need protection

> **Answer:** A

### Q25. One sentence captures this entire maintenance layer's philosophy. Which is it?

- **A.** Forgetting is a feature to engineer deliberately, not a failure to prevent at all costs  ✅
- **B.** Storage is cheap enough that deletion should always be the maintenance last resort
- **C.** A memory store's health is measured by its size: bigger stores serve agents better
- **D.** Maintenance is temporary: once retrieval is tuned well, the cleanup jobs can retire

> **Answer:** A


---
_Take it in the browser: https://the-faction.mn.co/posts/107155319_
