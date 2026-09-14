# The Faction — harvest status

**Superseded 2026-08-17: the manual copy-paste workflow is no longer needed.**

The earlier version of this file said lesson bodies "can't be scraped automatically
(confirmed 2026-08-12)" and set out a hand-copy workflow. That conclusion was wrong —
see *Why the first attempt failed* below. The whole curriculum is now harvested
automatically.

```
python tools/mighty_harvest.py --discover --harvest --keep-open 20   # login + pull
python tools/mighty_build_vault.py                                   # raw/ -> vault/
```

## What's on disk

| space | space id | lessons | exams | status |
|---|---|---|---|---|
| The Foundation — CADE 13-Layer Builder Certification | 23777123 | 13 | 13 | ✅ all bodies |
| The Mastery — Tier 4 Platform Mastery | 24191170 | 21 | 21 | ✅ all bodies |
| The Industry — verticals for AI Directed Engineers | 24251863 | 21 | 21 | ✅ all bodies |
| The Vault — Security Foundations for Builders | 24302166 | 7 | 7 | ✅ all bodies |
| The Launchpad — launch what you built | 24388894 | 7 | 7 | ✅ all bodies |
| The Frontier — Agent Orchestration Fundamentals | 24391596 | 7 | 7 | ✅ all bodies |
| **Curriculum total** | | **76** | **76** | ~923k chars |
| Welcome To The Faction | 23776513 | — | — | 61 posts |
| The Pit | 23777071 | — | — | 160 posts |
| The Forge | 23777162 | — | — | 41 posts |
| The Mentoring Lounge | 24188271 | — | — | 9 posts |

505 full post records in `raw/posts/`, 0 thin, 0 fetch errors.
The Foundation's space id was never "TBD" — nothing had asked the API for the space list.

Also harvested: **534/534 comments** (100% — 305 root + 229 replies, in `raw/comments/`,
rendered into each lesson/post as a `## Discussion` section) and **424 images**
(167 MB, `resources/images/`) plus 1 PDF.

## Known gaps

- **Exam questions.** `/spaces/<net>/posts/<id>/quiz_questions` returns **403**, not 404 —
  the route exists but is gated until a quiz *attempt* is started. Starting attempts on all
  76 exams would write to your real course progress, gamification stats and leaderboard
  position, so this was left alone. Say the word if you want them.
- **Videos (123).** All community (The Pit 100, Welcome 23) — **no curriculum videos exist**.
  The post record carries only a thumbnail, and the asset CDN 403s every unsigned path, so
  playback needs a signed URL the app mints at play time. The player doesn't mount on
  `/posts/<id>` either (no `<video>`, empty iframe), so a page probe never sees the stream.

### Comments API — the shape that isn't obvious

`GET /spaces/<net>/posts/<pid>/comments` returns **root comments only**. Each carries
`reply_count` and a `latest_replies` preview that **truncates** (a 4-reply thread ships 1),
so trusting it silently loses ~37% of replies. There is no `/comments/<id>/replies` route
(404) — full replies come from the *same* endpoint with `?reply_to_id=<comment_id>`.

## Why the first attempt failed (so it isn't repeated)

Not bot detection. The 2026-08-12 probe captured 15/15 API responses at HTTP 200.

1. **A false-positive login check.** When the creator made the curriculum free,
   `/spaces/<id>/content` started answering *anonymously*. The old script used that
   endpoint as its "am I signed in?" test, got 200 while logged out, and proceeded to
   scrape an anonymous lesson page — which contains only nav chrome. Only
   `/api/web/v1/users/current` distinguishes anon from authed, and even that is better
   replaced by a capability check: ask for a post and see whether a full record comes back.
2. **DOM scraping instead of the API.** Bodies were being read out of rendered HTML.
   They are served as `description` on the full post record.
3. **The wrong space id.** Bodies hang off the **network** space (23776511), not the
   course space. The course space id returns the thin stub.

`is_thin: true` is an access flag, not a compression option: anonymous callers always get
a stub with no body field. Full details in `membership.json` → `harvest_notes`.

## Prior manual pulls

`C:\Users\wmmb\Desktop\MMurphylessons\MattMurphy` still holds the 8 hand-formatted study
guides (SaaS Build M1–7, Database Design M1) and the Layer 1–13 kit PDFs. Those are kept
as-is — the harvested vault is additive and does not touch them.

## 2026-09-12 — both known gaps closed (read-only)

The *Known gaps* above are superseded. Neither fix writes anything to the account.

- **Exam questions: 4,525 across 181 exams, with the answer key.** Each question is its own
  post (`quiz_question_ids` are post ids), and `/spaces/<net>/posts/<qid>` returns it with
  `choices[].is_correct`. No quiz attempt is started. The course is public, so it runs over
  plain HTTP with no browser: `python tools/mighty_harvest.py --quizzes --http`.
- **Video transcripts: 175 videos (173 unique), 58k words, no video files.** Mighty
  auto-captions uploads with Deepgram; `/videos/<asset_id>/captions` hands out a signed VTT.
  The Vimeo welcome video uses Vimeo's auto-subtitles. `--captions` does both.
  Transcripts are in `vault/00 - Community Videos/` and on each community post.

Full re-sync, incremental and duplicate-free:

```
python tools/mighty_harvest.py --discover --harvest --comments --media   # posts, edits, comments, images
python tools/mighty_harvest.py --lean --captions                         # new video transcripts
python tools/mighty_harvest.py --quizzes --http                          # new exam questions
python tools/mighty_build_vault.py
python tools/mighty_export_mattmurphy.py --dry-run && python tools/mighty_export_mattmurphy.py
                                        # -> Desktop/MMurphylessons/MattMurphy (Matt-only, no dupes)
```

This PC often has ~1 GB of free RAM, and the OS killed two browser runs. Use `--lean` for
browser work and `--http` for questions. A failed caption fetch in a starved run looks like
"no captions"; re-run before concluding a video has none.

**Lesson audit (2026-09-12):** all 181 lessons have full bodies (2.0M chars). The live course
trees match disk. Attachments across all 892 posts total 3:
- `T6-Security-M6-TransportSecurity.pdf` is the whole body of Vault Module 6. It is in
  `resources/pdfs/`, and its text is now inlined into that lesson page.
- `Ashlar-CRM-504-Case-Study.pdf` (The Forge) and a Welcome screen recording both show asset
  `status: "empty"` with no link anywhere — uploads that never completed upstream.

Anonymous lesson fetches return `is_thin: true` with a 120-char preview, so compare bodies
only with the session cookies.
