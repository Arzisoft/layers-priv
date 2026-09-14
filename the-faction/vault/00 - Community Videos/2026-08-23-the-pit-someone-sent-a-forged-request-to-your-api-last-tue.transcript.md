---
type: transcript
lesson: "Someone sent a forged request to your API last Tuesday and your server processed"
course: "The Pit"
author: "Matt Murphy"
post_id: 106195788
published: "2026-08-23T14:00:01Z"
source_url: "https://the-faction.mn.co/posts/106195788"
duration: "2m00s"
words: 287
transcribed_by: "deepgram auto-captions (Mighty)"
---

# Transcript — Someone sent a forged request to your API last Tuesday and your server processed

> Someone sent a forged request to your API last Tuesday and your server processed it without question. Today I walk through HMAC request signing on mutating endpoints, path-based API versioning so you can evolve without breaking consumers, and sunset headers with deprecation monitoring so retired end

Someone sent a forged request to your API last Tuesday. Your server processed it. No questions asked. No request signing. No verification that the request came from a legitimate client.

No check on whether the payload was tampered with in transit. So your server accepted the request, ran the mutation, and returned to two hundred. The attacker now knows your API better than your documentation does because your API is a front door with no lock, no doorbell, and no one watching. So here is how we're gonna fix it. Step one, request signing on every mutating endpoint.

Every post, put, patch, and delete should carry a signature. An HMAC hash of the request body signed with a shared secret. So your server verifies the signature before processing. So unassigned requests, they get rejected. So direct your AI to implement request signing middleware that validates HMAC signatures on all mutating API calls.

That's a win. Step two, API versioning from day one. Your API path includes a version. V one stays stable. V two introduces breaking changes.

Consumers migrate on their schedule. Without versioning though, every schema change is a production incident for every consumer. So direct your AI to implement path based API versioning and a version negotiation strategy. That is definitely a win. And step three, a deprecation policy with sunset headers.

When an endpoint is scheduled for removal, the response includes a sunset header with retirement date. Consumers get warnings. Monitoring tracks usage of deprecating endpoints and when usage hits zero, the endpoint is removed. So Directory AI to implement sunset headers and deprecating monitoring on every endpoint scheduled for retirement. Your API is your contract with every consumer.

It's time to harden it.

---
_Source: https://the-faction.mn.co/posts/106195788_
