# Layer 6 of 13 — Cloud & Compute
**Tier 3 — Enterprise** | Matt Murphy Builder Certification Series

> *Builds on Tiers 1-2 (Solopreneur + Growth). Assumes those concepts and tools are already understood.*

---

## What It Covers

Running a cloud operation at enterprise scale. At Tier 3, cloud infrastructure is a major
business expense and a critical dependency. The job is governance: making sure the cloud
operation is cost-effective, compliant, reliable, and recoverable.

**Core goal:** You can run a cloud operation at enterprise scale — multi-cloud strategy, cost
governance with budgets and alerts, reserved capacity planning, compliance controls, and
disaster recovery across regions.

---

## Key Concepts

**Multi-cloud strategy** — Running the app across multiple cloud providers (AWS and GCP, for
example) so you're not locked into one vendor. If AWS has an outage, the app keeps running on
GCP. Adds complexity, but for enterprise apps where downtime costs thousands of dollars per
minute, it's worth the operational investment.

**Reserved capacity and commitment discounts** — Cloud providers offer 30-60% discounts for
committing to a certain amount of compute for one or three years — like signing a lease instead
of paying month-to-month rent. Saves money but loses flexibility; the decision depends on how
predictable usage is.

**Cost governance and FinOps** — FinOps (Financial Operations) is managing cloud spending
like a business function: setting budgets per team or project, tagging every resource so cost
ownership is clear, alerting when spending exceeds thresholds, and regularly reviewing what's
paid for versus what's actually needed.

**Compliance and data residency** — Enterprise clients often require data to stay in specific
geographic regions — European data stays in Europe, healthcare data stays in HIPAA-compliant
environments. The cloud setup must enforce these rules automatically, not rely on someone
remembering to pick the right region.

**Disaster recovery and business continuity** — If the primary cloud region goes down, how
fast can you recover? The plan includes automated failover, recovery time objectives (how long
you can be down), and recovery point objectives (how much data you can afford to lose) — not
theoretical, often written into enterprise client contracts.

---

## Toolkit (adds to Tier 2)

- **Multi-cloud management (Terraform, Pulumi)** — infrastructure-as-code tools that work across AWS, GCP, and Azure so multiple cloud providers can be managed from one configuration
- **FinOps platforms (CloudHealth, Spot by NetApp)** — enterprise cost management tools providing cross-cloud visibility, budget enforcement, and optimization recommendations
- **Compliance frameworks (AWS Config, Azure Policy)** — automated rules that enforce data residency, access controls, and security standards across the cloud environment
- **Disaster recovery tools (AWS Backup, cross-region replication)** — automated backup and failover systems that keep the app running even when an entire cloud region goes offline

---

## Certification Exam Topics

- **Multi-cloud justification** — Your CTO asks why you need two cloud providers instead of one. What business case do you make for multi-cloud, and when is single-cloud acceptable?
- **Reserved capacity** — Your app uses $8,000/month in compute with predictable traffic. A 1-year reserved instance commitment would save 35%. What factors do you evaluate before committing?
- **FinOps implementation** — Three teams are using cloud resources but nobody knows which team is responsible for the $3,000 spike last month. What governance changes do you implement?
- **Data residency** — A European client requires that all their data stays within EU borders. How does this affect your cloud architecture and deployment strategy?
- **Disaster recovery** — Your primary region fails during peak hours. Your recovery time objective is 5 minutes. Describe the systems that need to be in place.
- **Cost anomaly detection** — Your cloud bill increased 40% month-over-month with no traffic increase. What's your investigation process?
- **Compliance audit** — An enterprise client wants proof that your cloud infrastructure meets SOC 2 requirements. What documentation and controls do you need?
- **Vendor lock-in** — Your entire app runs on AWS-specific services. Your new CTO wants a multi-cloud strategy. What are the trade-offs of migrating, and where do you start?

---

## Common Pitfalls

- Never checking the cloud bill until month-end — a runaway function or misconfigured service burns money for weeks unnoticed
- Assuming "serverless" means "free" — it's pay-per-execution, and popularity turns pennies into real money fast
- Letting AI pick cloud services without understanding the pricing model — AI optimizes for working code, not cost-effective code
- Running the same compute resources 24/7 when the app only has traffic 8 hours a day
- Ignoring data transfer costs — moving data between services and out to users often costs more than compute itself
- Not setting up billing alerts before the first surprise bill

---

## Tier 3 Self-Assessment Checklist

- [ ] Can you explain, in plain language, where your app's code actually runs when a user visits your site?
- [ ] Do you know what you're currently paying for cloud services each month, and which services cost the most?
- [ ] Have you set up billing alerts so you'll know if your cloud spending spikes unexpectedly?
- [ ] Can you explain the difference between serverless functions and a traditional server, and why it matters for your bill?
- [ ] Do you know what your app's free-tier limits are and how close you are to exceeding them?
- [ ] If your app suddenly got 10x more traffic tomorrow, do you know what would happen to your costs and performance?
- [ ] Can you identify at least one place in your app where caching or optimization could reduce your cloud bill?

---

## AI Audit Prompt (copy into your AI tool)

```
Review my app's cloud and compute setup and check the following. For each
one, tell me pass or fail with a specific example:
Cost efficiency: Are there any functions, queries, or API calls that run more
frequently than necessary, and could caching or batching reduce the compute
cost?
Resource sizing: Is the app using more compute power or memory than it
actually needs, or is it under-provisioned and at risk of slowdowns?
Serverless configuration: Are serverless function timeouts, memory limits,
and concurrency settings appropriate for the workload?
Data transfer: Are there large assets (images, videos, files) being served
directly from the compute layer instead of through a CDN?
Scaling readiness: If traffic increased 10x, which parts of the
infrastructure would fail first, and what would need to change?
Billing visibility: Are there billing alerts, budget limits, or cost
monitoring dashboards set up to catch spending anomalies?
Give me an overall score out of 6 and list the top 3 things to fix first.
```

---

## What's Next

Once you've gone through this kit and can answer "yes" to the self-assessment checklist,
you're ready for the Layer 6 certification exam at your target tier.

The best way to prepare: look at your actual cloud bill. Open the hosting platform's dashboard
and study what's being paid for. Try the pricing calculator for a new service before adding it.
Ask AI to estimate the cost of a feature at different traffic levels. The exam tests whether you
understand what you're spending and why, and that understanding comes from looking at real
numbers.

---

## Certification pathway

Associate Builder = all 13 layers at Tier 1. Certified Builder = all 13 layers at Tier 1 + Tier 2.
MADE Certified = all 39 tier exams + capstone. 80% to pass each exam, 24-hour retake cooldown.
