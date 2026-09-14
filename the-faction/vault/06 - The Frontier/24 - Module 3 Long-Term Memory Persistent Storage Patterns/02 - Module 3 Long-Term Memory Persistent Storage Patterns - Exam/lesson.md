---
course: "The Frontier"
module: "Module 3: Long-Term Memory: Persistent Storage Patterns"
lesson: "Module 3: Long-Term Memory: Persistent Storage Patterns — Exam"
type: "course_quiz"
post_id: 107155307
space_id: 24391596
source: "https://the-faction.mn.co/posts/107155307"
updated: "2026-09-10T19:35:02Z"
---

# Module 3: Long-Term Memory: Persistent Storage Patterns — Exam

> Exam for **Module 3: Long-Term Memory: Persistent Storage Patterns** (The Frontier) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. A builder opens a memory project by asking 'which database is best for agents?' What is the better first question?

- **A.** Which store has the largest ecosystem, since community support outlasts any technical edge
- **B.** Which store costs least at scale, since memory grows without bound in production agents
- **C.** Which store the team already knows, since operational familiarity beats architectural fit
- **D.** How will an agent ask for this data later, since access patterns decide the natural store  ✅

> **Answer:** D

### Q2. An agent must store client records with known fields: plan tier, renewal date, contact. Reads are exact and filtered. Where does this belong?

- **A.** A vector store, since client data benefits from semantic recall as relationships evolve
- **B.** A document store, since client records vary too much for any fixed set of columns
- **C.** Flat files per client, since simple data deserves the simplest possible storage medium
- **D.** Postgres tables: structured facts with known fields get exact retrieval and filtering  ✅

> **Answer:** D

### Q3. State is always fetched by one known key, the session ID, and nothing else. Which storage shape naturally fits?

- **A.** A key-value shape: a keyed Postgres row or JSONB blob fetched directly by that ID  ✅
- **B.** A vector index keyed by embedding, so similar sessions can be fetched together
- **C.** A relational join across session and message tables, resolved fresh on every read
- **D.** An append-only event log, replayed from the start to rebuild state on each fetch

> **Answer:** A

### Q4. An agent needs to find past memories that resemble the current situation, without knowing what keywords they contain. What does this require?

- **A.** A full-text search index, since stemmed keyword matching approximates meaning well enough
- **B.** A wider context window, since resemblance is judged best by the model in the moment
- **C.** Embeddings in a vector store: similarity search retrieves by meaning, not keyword match  ✅
- **D.** A recursive SQL query that walks memory rows until content overlap gets detected

> **Answer:** C

### Q5. A team wants similarity recall but dreads running a second database beside their Supabase project. What does pgvector change?

- **A.** Postgres gains an embedding column type, so similarity search runs in that same database  ✅
- **B.** Supabase proxies queries to an external vector service, hiding the second system entirely
- **C.** Embeddings become unnecessary, since pgvector computes similarity from raw text directly
- **D.** The vector data syncs to Postgres nightly, so both systems stay one backup window apart

> **Answer:** A

### Q6. A reviewer says an agent's memory records are 'content-only' and predicts retrieval trouble. What fields would a complete record add?

- **A.** A compression ratio, an expiry date, a checksum, and the model version that wrote it
- **B.** A title, a category color, an owner avatar, and a sort weight for display ordering
- **C.** Type, subject, source, and timestamp, so records can be scoped, trusted, and aged  ✅
- **D.** The full conversation transcript inline, so every record carries its own evidence

> **Answer:** C

### Q7. 'Why not add Redis and Pinecone now, so we are ready?' a teammate asks at project start. What is the one-database-first argument?

- **A.** Redis and Pinecone charge by seat, so early adoption locks in pricing before growth
- **B.** One Postgres covers all three patterns with a backup story; split only on evidence  ✅
- **C.** Multiple stores confuse the model, which performs best with a single retrieval tool
- **D.** Vendors change APIs often, so committing late means less migration work over time

> **Answer:** B

### Q8. 'What is this client's plan tier?' returns three fuzzy paragraphs instead of a value. The agent stores everything as embedded chunks. What went wrong?

- **A.** The chunks were embedded with the wrong model, so tier data landed far from tier queries
- **B.** The similarity threshold was set too loose, and tightening it would surface the exact value
- **C.** The client name was missing from the chunks, so scoped retrieval had nothing to filter on
- **D.** Vector-first design: an exact lookup was forced through similarity search made for meaning  ✅

> **Answer:** D

### Q9. An agent writes memories as raw JSON blobs into one column with no type, source, or timestamp. Writes succeed. What happens downstream?

- **A.** Storage costs balloon, since untyped blobs cannot be compressed by the database engine
- **B.** Writes eventually fail, since Postgres enforces structure once a table passes a size limit
- **C.** Retrieval starves: with nothing to scope, trust, or order by, queries cannot find much  ✅
- **D.** Nothing changes, since modern query planners infer structure from blob contents anyway

> **Answer:** C

### Q10. A day-one agent stack includes Supabase, Redis, and a dedicated vector service. Nothing has shipped yet. What is the main cost of this setup?

- **A.** Query latency, since three stores must be consulted in sequence on every memory read
- **B.** Vendor lock-in, since three services triple the contracts the project now depends on
- **C.** Data drift, since three stores holding one dataset will always disagree eventually
- **D.** A tripled operational surface before any measured need for anything beyond Postgres  ✅

> **Answer:** D

### Q11. A client changed plans in June, but the memory store returns both the old and new tier with nothing marking which is current. What design gap is this?

- **A.** No update path: facts that change need upserts and updated_at, not an insert-only pile  ✅
- **B.** No embeddings: similarity scoring would have ranked the newer record above the older
- **C.** No archiving: old records belong in cold storage where queries can never reach them
- **D.** No triggers: the database should delete elder rows automatically as new ones arrive

> **Answer:** A

### Q12. Every memory query in an agent returns records about all clients mixed together, no matter who the session concerns. Which schema omission explains it?

- **A.** The subject field: without a client or project reference, memories cannot be scoped  ✅
- **B.** The embedding column: without vectors, queries cannot separate one client's records
- **C.** The confidence score: without it, low-quality records flood every result set returned
- **D.** The session ID: without it, the store cannot tell which conversation wrote each row

> **Answer:** A

### Q13. A builder declares their memory schema finished. It has every field and index planned. What test decides whether that claim holds?

- **A.** Load testing: insert a million synthetic rows and confirm the write path stays fast
- **B.** Peer review: a second builder signs off on naming, types, and index placement choices
- **C.** Migration dry runs: apply and roll back the schema twice on a fresh staging database
- **D.** Write the actual queries that get each memory back out; if you cannot, it is not done  ✅

> **Answer:** D

### Q14. Directing AI to build a long-term layer, a builder wants the correct opening move before schemas or code. What comes first?

- **A.** Pick the embedding model, since vector dimensions constrain every downstream choice
- **B.** Provision the database, since schema work goes faster against live infrastructure
- **C.** Inventory what persists, then classify each item by how it will be asked for later  ✅
- **D.** Write the boot sequence, since startup needs define what storage must contain

> **Answer:** C

### Q15. An agent stores arbitrary per-client preferences: some clients have three, others thirty, with unpredictable shapes. Which storage choice fits?

- **A.** One column per preference, added by migration whenever a new preference type appears
- **B.** JSONB in Postgres: schema freedom for varied shapes while queries still reach inside  ✅
- **C.** Embedded chunks per preference, so unusual shapes are recalled by their similarity
- **D.** A separate database per client, so each schema can evolve without affecting others

> **Answer:** B

### Q16. The agent learns a client moved their billing date. The memories table already holds the old date as a semantic fact. What should the write path do?

- **A.** Insert the new date alongside the old one, letting retrieval logic pick a winner later
- **B.** Upsert: update the existing fact in place and refresh updated_at to mark it current  ✅
- **C.** Delete the record and wait a session before rewriting, avoiding any race condition
- **D.** Write the new date to episodic memory instead, since changes are events, not facts

> **Answer:** B

### Q17. A query needs all memories about client X created since March, ordered newest first. Which storage design serves this well?

- **A.** A vector search using 'client X March' as the query text, ranked by cosine similarity
- **B.** A key-value fetch on the client key, with date filtering applied in application code
- **C.** A relational table with indexed subject and created_at columns doing the filtering  ✅
- **D.** A JSONB scan across all rows, parsing dates from content fields during the query

> **Answer:** C

### Q18. Schema and read paths are built. The builder now wires where new memories actually come from. What feeds the write path?

- **A.** Session close: durable facts, events, and procedures identified as sessions end  ✅
- **B.** A nightly batch that re-reads all transcripts and regenerates every memory row
- **C.** User uploads: memory should only contain documents a human deliberately added
- **D.** The boot sequence, which writes back whatever state it loaded at session start

> **Answer:** A

### Q19. A builder's pgvector setup works, but they wonder when a dedicated vector service like Pinecone becomes worth it. What is the honest trigger?

- **A.** The first paying customer, since production revenue justifies production-grade tooling
- **B.** Any use of similarity search at all, since Postgres was never built for vector work
- **C.** Real scale: embedding count and query volume measurably outgrowing pgvector comfort  ✅
- **D.** The first retrieval mistake, since specialized services rank results more accurately

> **Answer:** C

### Q20. Session lookups have measurably become the latency bottleneck in a shipped agent, confirmed by traces. What does this evidence justify?

- **A.** A bigger Postgres instance, since scaling up always beats adding new infrastructure
- **B.** Adding Redis for hot lookups: the measured need that store exists to serve appeared  ✅
- **C.** Moving all storage to Redis, since a proven bottleneck condemns the current database
- **D.** Denormalizing every table in the schema, since joins usually sit behind slow reads

> **Answer:** B

### Q21. After moving exact lookups to tables and keeping vectors only for research notes, an agent's retrieval quality jumps. What explains the improvement?

- **A.** Each read hits the store shaped for it: exact lookups stopped detouring through vectors  ✅
- **B.** The smaller vector index ranks results better, since fewer embeddings means less noise
- **C.** Postgres caches table reads aggressively, so repeated lookups return from memory faster
- **D.** Cancelling the vector service freed budget for a larger model, which reads more carefully

> **Answer:** A

### Q22. Write and read paths are implemented and the schema looks right. What final step proves the memory layer actually works?

- **A.** Round trips with real data: write real memories, then fetch them through each path  ✅
- **B.** A schema diagram review, confirming every table and index matches the original plan
- **C.** A week of production traffic, since only live users exercise storage realistically
- **D.** Unit tests on the ORM models, confirming field types and constraints all validate

> **Answer:** A

### Q23. A vibecoder is building this storage layer with AI. Which division of labor matches the practice this course teaches?

- **A.** The builder writes all the SQL by hand and has AI review it, since schemas are too risky to delegate
- **B.** The builder specifies access patterns and judges results; AI designs and implements the layer  ✅
- **C.** AI chooses the access patterns and the builder implements them, keeping humans on the code
- **D.** The builder copies a community schema and AI adapts variable names to match the project

> **Answer:** B

### Q24. Two memory records hold the same fact, but only one carries its source and timestamp. In what practical way is that record more useful?

- **A.** It compresses better, since metadata gives the storage engine predictable structure
- **B.** It embeds more accurately, since metadata anchors the vector in a richer space
- **C.** It ranks higher in every query, since databases prefer complete rows by default
- **D.** Its provenance and age can be judged, so staleness and trust become answerable  ✅

> **Answer:** D

### Q25. Underneath tables, JSONB, and vectors, one principle governs every long-term storage decision in this course. Which is it?

- **A.** Prefer the newest storage technology, since agent workloads reward modern engines
- **B.** Fit the store to the retrieval: the question the agent will bring decides where data lives  ✅
- **C.** Persist everything in every store, since redundancy is what makes memory reliable
- **D.** Minimize storage cost above all else, since memory systems fail on economics rather than design

> **Answer:** B


---
_Take it in the browser: https://the-faction.mn.co/posts/107155307_
