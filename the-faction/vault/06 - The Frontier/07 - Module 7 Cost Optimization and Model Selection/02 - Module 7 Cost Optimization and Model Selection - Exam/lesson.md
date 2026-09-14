---
course: "The Frontier"
module: "Module 7: Cost Optimization and Model Selection"
lesson: "Module 7: Cost Optimization and Model Selection — Exam"
type: "course_quiz"
post_id: 104725996
space_id: 24391596
source: "https://the-faction.mn.co/posts/104725996"
updated: "2026-08-10T17:18:21Z"
---

# Module 7: Cost Optimization and Model Selection — Exam

> Exam for **Module 7: Cost Optimization and Model Selection** (The Frontier) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. What is the basic billing unit of AI model usage?

- **A.** The session, with each conversation costing a flat rate regardless of its length
- **B.** The user seat, priced monthly per human regardless of how much they generate
- **C.** The calendar day, since providers meter access by time rather than by volume
- **D.** The token, covering both what you send into the model and what it generates back  ✅

> **Answer:** D

### Q2. What is the honest trade between frontier models and smaller ones?

- **A.** There is none at all; frontier models are better at everything including cost, so the choice is fake
- **B.** Frontier buys peak capability at higher cost and latency; smaller is cheaper and faster but shallower  ✅
- **C.** Smaller models are only legal for internal work, while frontier is required for clients
- **D.** Frontier models are older and proven, while smaller models are the risky newer releases

> **Answer:** B

### Q3. What is model routing?

- **A.** Sending each task to the model that fits it: light work to cheap models, hard work to frontier  ✅
- **B.** The network path tokens travel between your servers and the provider's data centers each call
- **C.** Rotating providers monthly so that no single vendor learns your full usage patterns over time
- **D.** A load balancer that splits every prompt evenly across all available models at once

> **Answer:** A

### Q4. When does batch processing beat real-time calls?

- **A.** Never, since batching is a legacy pattern that modern APIs have made completely obsolete
- **B.** Only for image work, since text requests cannot be grouped together by any major provider
- **C.** When results aren't needed instantly: bulk jobs run cheaper off the interactive path  ✅
- **D.** When the work is urgent, since batches jump ahead of real-time requests in the provider queue

> **Answer:** C

### Q5. You're assigning models to workflow steps. What should determine the choice per step?

- **A.** The difficulty and stakes of that step, matched against what each model reliably handles  ✅
- **B.** Alphabetical order of model names, which removes all human bias from the entire selection process
- **C.** Whatever model the team likes most, since familiarity outweighs actual fit in daily practice
- **D.** Always the newest release, since recency is the only truly reliable signal of model quality

> **Answer:** A

### Q6. Your prompts include pages of boilerplate that rarely changes. Why does this matter financially?

- **A.** It doesn't; providers bill only the model's output, so input length is always completely free
- **B.** Boilerplate is billed at double rate, since repeated content is flagged as spam
- **C.** Long prompts improve quality linearly, so the spending is automatically justified
- **D.** Input tokens cost money on every call, so recurring bulk multiplies across all your volume  ✅

> **Answer:** D

### Q7. Many of your requests reuse the same large context. What mechanism addresses this cost?

- **A.** Sending the context in a compressed archive format that the model unpacks internally itself
- **B.** Caching: providers can reuse recently seen context at a fraction of the original price  ✅
- **C.** Splitting the context across several accounts so that no single bill ever looks alarmingly large
- **D.** Translating the context into a shorter language before each request is submitted to the model

> **Answer:** B

### Q8. What is the flaw in optimizing purely for cost per token?

- **A.** Token prices are identical across all models, making the comparison meaningless
- **B.** Cheaper tokens are lower quality tokens, physically degrading the output text
- **C.** The real metric is cost per successful outcome; cheap tokens that fail are expensive  ✅
- **D.** Per-token math is prohibited by provider terms, which require per-request accounting

> **Answer:** C

### Q9. Which situation genuinely justifies paying frontier prices?

- **A.** Simple formatting tasks, since presentation quality is where frontier models shine the most
- **B.** High-stakes or genuinely hard work: complex reasoning, critical accuracy, novel problems  ✅
- **C.** All internal tooling, since employees deserve the best models the company can buy
- **D.** Tasks with no deadline, since frontier models perform best without time pressure

> **Answer:** B

### Q10. The agent's answers ramble for pages when a paragraph would do. Why fix this beyond style?

- **A.** Output tokens cost money and time; unbounded verbosity is a spend leak on every call  ✅
- **B.** Long outputs crash mobile devices, cutting off a steadily growing share of your user base
- **C.** Providers penalize verbose accounts with slower queues during business hours
- **D.** Rambling outputs age faster, requiring regeneration sooner than concise ones

> **Answer:** A

### Q11. What financial controls belong on any serious AI deployment?

- **A.** None, since usage-based billing is self-limiting and cannot ever produce billing surprises
- **B.** A single annual budget review, since monthly attention to spending signals distrust of the team
- **C.** Manual invoice reading only, since automated alerts desensitize teams to real cost signals
- **D.** Budgets, alerts, and per-workflow spend visibility, so anomalies surface in hours, not invoices  ✅

> **Answer:** D

### Q12. A cheaper model could replace the current one on a workflow. What must happen before switching?

- **A.** Nothing; if the price is lower and the API is compatible, the switch is pure savings already
- **B.** A six-month waiting period, since new pricing tiers often reverse within a quarter
- **C.** Run your evaluation suite on it: the discount only counts if quality holds at your bar  ✅
- **D.** A team vote, since model changes affect morale more than they affect the output

> **Answer:** C

### Q13. Which workload actually needs real-time model responses?

- **A.** Ones where a human or process is actively waiting on the answer to proceed  ✅
- **B.** All workloads, since faster is universally better regardless of who is waiting
- **C.** Overnight report generation, since reports are the most latency-sensitive artifacts
- **D.** Archival summarization, since old data degrades further while queued for batch

> **Answer:** A

### Q14. A transient error caused your system to retry aggressively all night. The bill tripled. What was missing?

- **A.** A cheaper model, since retries running on discount models make runaway loops affordable enough
- **B.** Retry discipline: capped attempts, backoff, and alerts, so failures don't compound into spend  ✅
- **C.** A faster network connection, since retries are caused entirely by connection speed problems
- **D.** Nothing; tripled bills from retries are normal and providers refund them quite promptly on request

> **Answer:** B

### Q15. How does context discipline connect to cost at scale?

- **A.** It doesn't; context size affects quality but has no relationship whatsoever to the billing at all
- **B.** Inversely; larger contexts are discounted per token, rewarding maximal stuffing of every call
- **C.** Every token in context is billed on every call, so lean context compounds into real savings  ✅
- **D.** Only for images; text context is billed at a flat rate regardless of its length in tokens

> **Answer:** C

### Q16. A single agent task fired forty tool calls and model steps. Why does architecture matter to the bill here?

- **A.** It doesn't; multi-step tasks are billed as one call regardless of internal steps
- **B.** Tool calls are free, so step count only matters for the latency budget of the overall task
- **C.** Step count is fixed by the model and cannot be influenced by any design choice
- **D.** Each step bills tokens, so loops and chattiness multiply cost invisibly inside one task  ✅

> **Answer:** D

### Q17. You build AI-powered systems for clients. How should model costs enter your pricing?

- **A.** As accounted overhead: know the run cost of what you ship and price so margins survive it  ✅
- **B.** They shouldn't; model costs are the client's surprise to discover after the handoff
- **C.** As a separate invoice line marked up ten times over, since clients cannot verify token math
- **D.** Absorbed silently forever, since mentioning operating costs weakens the sales story

> **Answer:** A

### Q18. When is the right time to aggressively optimize a workflow's model costs?

- **A.** Before building anything, since architecture should be designed around the cheapest path
- **B.** Never, since optimization energy is always better spent on adding new capabilities
- **C.** After it works: prove quality first, then cut costs where measurements say it's safe  ✅
- **D.** During the client demo, since visible frugality builds trust in the engagement

> **Answer:** C

### Q19. Your workflow hits provider rate limits at peak hours. What are the mature options?

- **A.** Creating dozens of separate accounts to multiply your limits without the provider's knowledge
- **B.** Sending complaints hourly, since limit increases are granted to the persistent customers
- **C.** Abandoning the workflow, since rate limits signal that the provider wants your traffic gone
- **D.** Smoothing load, batching what can wait, requesting higher tiers, or routing across models  ✅

> **Answer:** D

### Q20. The model your system depends on is being deprecated by the provider. What does managed selection look like?

- **A.** Ignoring the notice, since deprecated models continue running indefinitely in actual practice
- **B.** Planned migration: evaluate successors early, test against your suite, switch on your schedule  ✅
- **C.** Litigation, since deprecation of a model your business depends upon is actionable harm to you
- **D.** Instant panic switching on announcement day to whatever model is newest that week

> **Answer:** B

### Q21. You routed a genuinely hard reasoning task to the cheapest model and it failed repeatedly. What did this actually cost?

- **A.** More than frontier would have: retries, rework, and cleanup dwarf the per-call savings  ✅
- **B.** Nothing, since failed calls are automatically refunded by every major provider
- **C.** Exactly the sticker price, since failure and success bill identically per attempt every time
- **D.** Reputation only, since financial cost and quality cost are unrelated dimensions

> **Answer:** A

### Q22. Before committing to a high-volume workflow, what should you estimate?

- **A.** The provider's annual revenue, since vendor financial health determines long-term workflow viability
- **B.** The moon launch window, since compute pricing closely tracks aerospace demand cycles yearly
- **C.** Tokens per run times volume times price: the monthly bill, roughly, before it surprises you  ✅
- **D.** Nothing; estimation is pure guesswork, and real bills are the only trustworthy data available

> **Answer:** C

### Q23. What role should free tiers and trial credits play for a professional builder?

- **A.** None, since free capacity is for hobbyists and signals unseriousness to prospective clients
- **B.** Production hosting, since rotating trial accounts can sustain a client system
- **C.** Permanent operation, since providers rarely audit who is consuming free tiers
- **D.** Prototyping: cheap experiments to validate an approach before real budgets commit  ✅

> **Answer:** D

### Q24. A client asks what their AI system costs to run monthly. What does professional practice look like?

- **A.** Deflecting, since operating costs are proprietary information belonging to the builder
- **B.** A clear answer from real usage data, with the drivers explained and levers identified  ✅
- **C.** A theatrical range spanning two orders of magnitude, protecting you from every case
- **D.** Redirecting to the provider's pricing page, since public rates answer the question

> **Answer:** B

### Q25. Which principle should govern model selection and cost across everything you build?

- **A.** Fit the model to the task, measure cost per outcome, and optimize only what you've proven works  ✅
- **B.** Default everything to frontier, since capability headroom excuses any level of operating cost
- **C.** Default everything to the cheapest model, since spend is the only metric that truly compounds over time
- **D.** Change models weekly, since provider competition rewards only the most restless customers

> **Answer:** A


---
_Take it in the browser: https://the-faction.mn.co/posts/104725996_
