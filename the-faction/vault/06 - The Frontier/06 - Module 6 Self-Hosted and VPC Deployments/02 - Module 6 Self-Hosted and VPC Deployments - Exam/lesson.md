---
course: "The Frontier"
module: "Module 6: Self-Hosted and VPC Deployments"
lesson: "Module 6: Self-Hosted and VPC Deployments — Exam"
type: "course_quiz"
post_id: 104725971
space_id: 24391596
source: "https://the-faction.mn.co/posts/104725971"
updated: "2026-08-21T00:43:15Z"
---

# Module 6: Self-Hosted and VPC Deployments — Exam

> Exam for **Module 6: Self-Hosted and VPC Deployments** (The Frontier) — 25 questions, pass mark 80%. Correct answers are marked ✅ (read from each question's own post record; no quiz attempt was started to get them).

### Q1. For most builders and most workloads, why does the API route beat self-hosting?

- **A.** APIs are legally safer, since self-hosted inference is prohibited in most regulated industries
- **B.** APIs bill in smaller increments, and billing granularity is the dominant cost factor
- **C.** APIs never change, giving builders a stability that self-hosted models cannot match
- **D.** Frontier capability with zero infrastructure burden: no GPUs, patching, or serving to run  ✅

> **Answer:** D

### Q2. What is a VPC deployment of an AI model?

- **A.** A model running on volunteer personal computers, distributed across all employee home offices
- **B.** The model runs inside your private cloud boundary, so data stays within your network perimeter  ✅
- **C.** A visual programming console that replaces written prompts with drag-and-drop workflow blocks
- **D.** A model licensed per individual city, with usage geofenced to a single approved metropolitan area

> **Answer:** B

### Q3. What is the fundamental hardware constraint when choosing a model to self-host?

- **A.** The model must fit in your GPU memory, which determines what size you can actually run  ✅
- **B.** The model's file name length, since storage systems will truncate long model identifiers
- **C.** Your office's ceiling height, since GPU racks carry strict vertical clearance needs
- **D.** Monitor resolution, since larger models render their outputs at higher pixel densities

> **Answer:** A

### Q4. What are open-weight models in the self-hosting conversation?

- **A.** Models whose behavior changes weekly, staying open to continuous retraining by their provider
- **B.** Models that only run outdoors, named for the open-air data centers they require
- **C.** Models trained exclusively on public data, making them free of any licensing terms
- **D.** Models whose weights are published for download, so you can run them on your own hardware  ✅

> **Answer:** D

### Q5. Beyond the hardware bill, where do self-hosting costs actually accumulate?

- **A.** Nowhere at all; once the GPUs are purchased, self-hosted inference is effectively free forever after
- **B.** Operations: serving, scaling, patching, monitoring, and the engineering time all of it consumes  ✅
- **C.** Printing, since self-hosted deployments require full paper documentation by long convention
- **D.** Travel, since self-hosted models must be physically visited every week for careful calibration

> **Answer:** B

### Q6. What capability trade-off usually comes with self-hosting?

- **A.** None; self-hosted and frontier API models are always identical in capability by definition
- **B.** Self-hosted models are stronger but slower, trading response speed for extra quality
- **C.** Hostable models typically trail the frontier, so you trade some capability for control  ✅
- **D.** Self-hosted models lose the ability to write text, functioning only on structured data

> **Answer:** C

### Q7. A hospital client requires that patient data never leave their infrastructure. What does this requirement drive?

- **A.** An architecture where inference happens inside their boundary — self-hosted or VPC — for that data  ✅
- **B.** Nothing extra; API terms of service already guarantee that data never leaves any customer's control
- **C.** A discount negotiation, since data-sensitive clients get preferential frontier API rates
- **D.** Abandoning AI entirely, since regulated data and AI are incompatible in all designs

> **Answer:** A

### Q8. The model is downloaded. What does model serving mean before the first real request?

- **A.** Presenting the model to company leadership in a formal unveiling ceremony before its activation
- **B.** Uploading the model back to its publisher so they can verify your copy's integrity
- **C.** The infrastructure that loads it, exposes an endpoint, handles requests, and scales under load  ✅
- **D.** The customer support tier you must fully staff before any internal system is allowed to go live

> **Answer:** C

### Q9. How does security responsibility shift when you move from API to self-hosted?

- **A.** It disappears, since models running on your own hardware are unreachable by any outside attacker
- **B.** It lands on you: patching, access control, and monitoring become your operational burden  ✅
- **C.** It transfers to the model's publisher, who insures all of the downstream deployments worldwide
- **D.** It shifts to the GPU manufacturer, whose hardware warranty covers security incidents completely

> **Answer:** B

### Q10. What is a hybrid architecture in this context?

- **A.** A model that alternates hourly between your hardware and the provider's cloud
- **B.** Two identical models voting on every answer, one local and one remote, for accuracy
- **C.** Half the model's layers running locally with the rest streamed from the provider
- **D.** Sensitive workloads run inside your boundary while general work uses frontier APIs  ✅

> **Answer:** D

### Q11. A client demands full self-hosting. What should an AI Directed Engineer do before architecting it?

- **A.** Probe the actual requirement: often a VPC option or API data controls satisfy the real constraint cheaper  ✅
- **B.** Comply immediately, since questioning a stated requirement always damages the client relationship
- **C.** Refuse the engagement outright, since self-hosting demands signal an impossible client lies ahead
- **D.** Triple the quote silently, since unquestioned requirements deserve premium pricing on every engagement

> **Answer:** A

### Q12. Six months after a self-hosted deployment, what maintenance reality has set in?

- **A.** None whatsoever; models are static files, so a deployed system needs no ongoing attention after launch
- **B.** Only dusting, since hardware cleanliness is the dominant factor in long-term model longevity
- **C.** The model is aging while the frontier moved on: updates, security patches, and upgrades are on you  ✅
- **D.** The model has improved itself through daily use, reducing the maintenance burden every month

> **Answer:** C

### Q13. What performance dimensions must self-hosted serving be sized against?

- **A.** Font rendering speed, since slow typefaces are the visible symptom of badly undersized GPUs
- **B.** Office network cable length, since inference speed decays per meter of cabling
- **C.** The number of tabs users keep open, since browser load determines model throughput
- **D.** Latency per request and throughput under concurrent load, at the traffic you actually expect  ✅

> **Answer:** D

### Q14. What is the core promise a properly designed private deployment makes?

- **A.** Perfect accuracy, since local inference removes the errors that networks introduce
- **B.** Prompts and data are processed inside the controlled boundary and never leave it  ✅
- **C.** Zero cost after setup, since electricity is the only recurring expense involved
- **D.** Infinite scale, since owned hardware has no rate limits of any practical kind

> **Answer:** B

### Q15. When can the economics genuinely favor self-hosting over API usage?

- **A.** At high, steady, predictable volume, where utilized hardware beats per-token pricing  ✅
- **B.** Always, since owning anything is cheaper than renting it in every business context
- **C.** Never, since API prices are set below hardware costs to make self-hosting irrational
- **D.** Only for companies with free electricity, since power is the entire cost equation

> **Answer:** A

### Q16. Your chosen model won't fit on the available hardware, and a compressed variant exists. What is the trade?

- **A.** The compressed variant runs slower but produces strictly better quality output
- **B.** No trade; compression is lossless for models exactly the way it is for ordinary archives
- **C.** Compression voids the model license, converting the deployment into infringement
- **D.** It fits and runs cheaper, but with some quality loss you must measure against your bar  ✅

> **Answer:** D

### Q17. What organizational capability should exist before a client takes on self-hosted AI?

- **A.** A marketing team standing ready to announce the deployment across all the client's channels
- **B.** A minimum of five hundred employees, below which self-hosting deployments are never permitted
- **C.** Real operations capacity: people who can run, monitor, and fix infrastructure under pressure  ✅
- **D.** An executive who personally writes code, since leadership involvement determines system uptime

> **Answer:** C

### Q18. Before deploying an open-weight model commercially, what must be checked?

- **A.** The model's birthday, since models may not be deployed within a year of release
- **B.** Its license terms: what commercial use, modification, and redistribution it actually permits  ✅
- **C.** The publisher's stock price, since financial health predicts model quality directly
- **D.** Nothing at all, since downloadable weights are by definition free of every usage restriction

> **Answer:** B

### Q19. A client is ready to buy GPUs for a self-hosted deployment. What should happen first?

- **A.** A pilot on rented capacity: prove the model meets the need before hardware money is committed  ✅
- **B.** The purchase itself, since hardware availability windows close much faster than pilots can ever run
- **C.** A press release, since announced commitments help negotiate better hardware pricing
- **D.** An office expansion, since GPU heat output requires renovated space before delivery

> **Answer:** A

### Q20. The self-hosted model server goes down at 2 AM. What determines how bad this is?

- **A.** The model's size, since larger models restart themselves faster than smaller ones do after failures
- **B.** The weather that night, since overnight outages resolve naturally when temperatures drop
- **C.** The moon phase, since scheduled restarts should always align with the low-gravity windows
- **D.** The planning you did: failover, backups, and an on-call path, or the absence of all three  ✅

> **Answer:** D

### Q21. What should be monitored on a self-hosted model in production?

- **A.** Nothing, since monitoring is an API-era habit that private deployments have completely outgrown
- **B.** Usage, performance, errors, and abuse patterns — you are now the provider, with a provider's duties  ✅
- **C.** Only electricity consumption, since power draw is a complete proxy for the system's overall health
- **D.** Employee sentiment about the model, gathered through anonymous quarterly surveys of the staff

> **Answer:** B

### Q22. A client asks whether they should self-host. What does honest advising look like?

- **A.** Always recommending self-hosting, since bigger engagements naturally follow bigger infrastructure builds
- **B.** Always recommending the API path, since simplicity protects the builder from long support burden
- **C.** Laying out the real trade — control and residency versus capability, cost, and burden — against their need  ✅
- **D.** Recommending whatever their competitor chose, since industry parity is always the safest answer available

> **Answer:** C

### Q23. Which principle should guide self-hosted and VPC deployment decisions?

- **A.** Deploy for the requirement, not the romance: control has real costs, so pay them only when the data demands it  ✅
- **B.** Own everything possible: dependence on any outside provider is a strategic failure to be eliminated
- **C.** Follow the frontier blindly: whatever the very newest model is, that is what must be deployed everywhere it fits
- **D.** Avoid infrastructure forever: no client requirement could ever justify running your own models

> **Answer:** A

### Q24. What is the primary legitimate driver for self-hosting instead of using a frontier API?

- **A.** Data control: privacy, compliance, or residency rules that require inference inside your boundary  ✅
- **B.** Speed of setup, since standing up your own model serving is faster than getting an API key issued today
- **C.** Quality, since self-hosted models consistently outperform the frontier APIs that they mirror
- **D.** Prestige, since clients pay premium rates to vendors who own their own physical hardware racks

> **Answer:** A

### Q25. What does self-hosting an AI model actually mean?

- **A.** Paying a premium API tier that guarantees your requests run on dedicated hardware
- **B.** Downloading a provider's app onto company laptops instead of using the browser version of it
- **C.** Running the model on infrastructure you control, so inference happens inside your boundary  ✅
- **D.** Hiring the provider's staff to sit in your office while they operate their own cloud

> **Answer:** C


---
_Take it in the browser: https://the-faction.mn.co/posts/104725971_
