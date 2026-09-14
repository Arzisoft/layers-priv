---
course: "The Vault"
module: "Module 5: Rotation, Revocation, and Lifecycle Management"
lesson: "Module 5: Rotation, Revocation, and Lifecycle Management — Study Guide"
type: "course_lesson"
post_id: 107142736
space_id: 24302166
source: "https://the-faction.mn.co/posts/107142736"
updated: "2026-09-10T20:01:05Z"
---

# Module 5: Rotation, Revocation, and Lifecycle Management — Study Guide

# Secrets and API Key Management

### T6 The Vault | Module 5 Study Guide

## Module 5: Rotation, Revocation, and Lifecycle Management

> Direct AI to build rotation, revocation, and a living secret inventory before the day you need them in a panic.

## Why This Matters

Every secret you hold gets older and more exposed every day: more machines have seen it, more logs might contain it, more ex-collaborators remember where it lived. Rotation resets that clock on a schedule; revocation slams the door in an emergency; the inventory tells you what you even have. Builders who set these up calmly, in advance, turn the worst secrets days into routine maintenance.

## Core Concepts

**Secrets age like exposure, not like wine.** A key's risk accumulates with time: every deploy, every log line, every teammate laptop is another possible copy. Expiry and rotation exist to cap that accumulation. A secret that never changes is a bet that no copy ever escaped, renewed daily, forever.

**Rotation is replacement without downtime.** The pattern is overlap: create the new credential, deploy it everywhere the old one was used, verify, then revoke the old one. Two valid credentials exist briefly; zero downtime results. Providers that support multiple active keys (Stripe with rolled keys, cloud IAM with two access keys per user) are designed for exactly this dance.

**Revocation is the emergency brake.** Rotation is scheduled; revocation is now. When a key is confirmed or suspected leaked, the sequence inverts: kill the credential first, accept the outage risk, then deploy the replacement. Speed beats grace when someone else may hold the key. Every provider dashboard has the revoke button; knowing where it is before the emergency is the preparation that counts.

**The inventory problem is the real problem.** The frightening question is never "how do I rotate this key," it is "what breaks if I do?" An inventory answers it: every secret, where it is stored, which systems consume it, when it was last rotated, who owns it. Without the inventory, old keys become immortal because nobody dares touch them; with it, rotation is a checklist, not an adventure.

**Automate where offered, schedule where not.** Managed rotation exists: AWS Secrets Manager rotates RDS credentials on schedule; short-lived tokens and workload identity rotate by design. For everything else (Stripe, OpenAI, Supabase keys), rotation is a calendar habit: quarterly for standard keys, immediately on any exposure event, and always at collaborator offboarding.

## How It Works

The rotation runbook, generalized:

1. **Consult the inventory.** What consumes this secret? Which environments? Which platform settings, CI configs, and manager entries hold it?
1. **Create the new credential.** In the provider dashboard or API, with the same or narrower scope. Rotation is the natural moment to tighten permissions.
1. **Deploy alongside.** Update the secrets manager; let sync push it to platforms and CI. With overlap-capable providers, both keys work during the transition.
1. **Verify.** Confirm the app works on the new credential in every environment; check error rates before proceeding.
1. **Revoke the old.** Kill it in the provider dashboard. Watch for anything that breaks: whatever breaks was a consumer your inventory missed. Add it.
1. **Record.** Update the inventory: rotation date, who did it, anything learned. The inventory gets better every cycle.

Emergency revocation runs the same steps in a different order: revoke (step 5) first, then create, deploy, verify, with the app degraded in between. That trade is correct when the alternative is an attacker holding a live key. Module 7 covers the full incident response around it.

## Directing AI

- "Build the secret inventory for this project: every credential, where it is stored, every consumer, last rotation date, owner. Output as a table I can keep in the repo's private docs."
- "Write the rotation runbook for our Stripe keys specifically: the overlap steps, the exact dashboard locations, the verification checks, and the rollback if verification fails."
- "This key must be rotated now due to suspected exposure. Walk me through emergency revocation for this provider: what breaks the moment I revoke, and in what order do I restore service."
- "Set up rotation reminders: which of our secrets have no automated rotation, and generate the quarterly checklist with per-key steps."
- "We are offboarding a collaborator. From this inventory, list every secret they could have seen and the rotation order, highest blast radius first."

## Common Mistakes

- **Rotating nothing until forced.** Years-old keys with unknown copy counts, rotated only after an incident proves the point the schedule would have made cheaply.
- **Rotating without overlap.** Revoking the old key before the new one is deployed, turning routine maintenance into a self-inflicted outage. Scheduled rotation never needs downtime.
- **Rotation theater.** The key changed, but the old value still works because revocation was skipped: both keys now live indefinitely. Rotation ends when the old credential is dead, not when the new one exists.
- **No inventory, so no courage.** Nobody rotates what nobody can predict; the unknown consumer is scarier than the known risk. The inventory is what makes rotation psychologically possible.
- **Forgetting offboarding.** A collaborator leaves with working knowledge of every key they ever touched; the keys outlive the trust. Offboarding is a rotation trigger, every time.
- **Skipping the record.** The rotation happened but the inventory was not updated, so the next rotation starts from archaeology again.

## Real-World Application

A client emails: their previous developer left on bad terms, and they want to know if their app is safe. The builder pulls the inventory equivalent from the codebase using AI, produces the list: Supabase service key, Stripe live keys, OpenAI key, database password, a GitHub deploy token. Rotation order by blast radius: database and Supabase first, Stripe next with overlap so checkout never blinks, OpenAI and the deploy token last. Two hours, zero downtime, every credential the ex-developer ever saw now dead. The builder leaves behind the inventory table and a quarterly rotation checklist. The client's scary afternoon becomes the builder's cleanest demonstration of what professional secrets handling looks like.

## Decision Framework

- **Scheduled rotation due?** Overlap pattern: create, deploy, verify, revoke, record.
- **Confirmed or suspected leak?** Emergency order: revoke first, restore after. Speed beats grace.
- **Collaborator leaving?** Rotate everything they could have seen, blast radius order, same day.
- **Provider offers managed rotation or short-lived credentials?** Turn it on and delete the calendar entry.
- **Afraid to rotate a key?** That fear is the inventory gap talking; fix the inventory, then rotate.
- **Old key still valid after rotation?** Rotation is not done; revoke it and confirm.

## Tool and Platform Notes

- Stripe supports rolling keys with an overlap window, and restricted keys rotate independently of the master key; the dashboard shows when each key was last used, which is inventory gold.
- Supabase allows JWT secret and service key regeneration; database passwords reset from the dashboard; plan for the brief reconnect.
- OpenAI keys revoke instantly from the dashboard; per-project keys mean rotation touches one project, not five.
- AWS IAM supports two access keys per user precisely for overlap rotation; AWS Secrets Manager automates RDS credential rotation end to end.
- GitHub fine-grained tokens carry expiry dates natively: an expiring token is a rotation reminder built into the credential itself.
- Sync-tier managers (Doppler, Infisical) make the deploy step one update; their activity logs double as rotation records.

## Key Takeaways

- Secrets accumulate exposure over time; rotation caps it on a schedule, revocation ends it in an emergency.
- Scheduled rotation uses overlap: create, deploy, verify, revoke, record; zero downtime.
- Emergency revocation inverts the order: kill first, restore after; speed beats grace when a key may be held.
- The inventory (secret, location, consumers, last rotation, owner) is what makes any of this possible.
- Offboarding is always a rotation event; managed rotation and expiring credentials shrink the manual surface.

## What's Next

Your secrets now have lifecycles. Module 6 follows them into the deployment machinery: CI/CD pipelines, build-time versus runtime, and keeping secrets out of logs, artifacts, and containers.

## Exam Prep Notes

Focus on: why secrets age, the overlap rotation pattern and its exact order, how emergency revocation reorders the steps and why, the inventory fields and the fear it removes, offboarding as a trigger, and which platforms automate rotation or support dual keys. Scenarios will present leaks, departures, and rotation plans and ask for the right order of operations.

---

Matt Murphy AI | The Faction Group LLC | mattmurphy.ai

---
_Source: https://the-faction.mn.co/posts/107142736_
