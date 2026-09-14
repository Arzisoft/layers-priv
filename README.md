# layers-priv

Private reference. Two halves, kept separate on purpose.

## `layer-01…13-*.md` (root) — written

Hand-written condensations of Matt Murphy's **CADE 13-Layer Builder Certification**,
one file per layer per tier:

| file suffix | tier |
|---|---|
| *(none)* | Tier 1 — Solopreneur |
| `-tier2-growth` | Tier 2 — Growth |
| `-tier3-enterprise` | Tier 3 — Enterprise |

Plus `PLATFORM-RELEVANCE-ANALYSIS.md`. These are original summaries, not copies of
anything under `the-faction/` — edit them freely.

## `the-faction/` — harvested

A generated mirror of **The Faction** (`the-faction.mn.co`), synced 2026-09-12 from
`memberships/the-faction` in the local Clief Notes archive. **Never hand-edit** — the
next sync overwrites it. Keep your own notes in root-level files instead.

```
the-faction/
  vault/                      790 rendered markdown files
    00 - Community/           posts from Welcome, The Pit, The Forge, Mentoring Lounge
    00 - Community Videos/    175 video transcripts (no media)
    01 - The Foundation/      13 layers  — CADE 13-Layer Builder Certification
    02 - The Mastery/         Tier 4 Platform Mastery
    03 - The Industry/        industry verticals
    04 - The Vault/           security foundations
    05 - The Launchpad/       launch / freelance / pricing
    06 - The Frontier/        agent orchestration
  membership.json             space ids, harvest history, API gotchas
  HARVEST-CHECKLIST.md        what's captured, what isn't, and why
```

Each course folder holds `NN - <Module>/01 - … Study Guide/lesson.md` and
`02 - … Exam/lesson.md`. Every exam has its questions inlined **with the answer key
marked**, and lesson/post pages carry their comment threads as a `## Discussion`
section — so `vault/` is the complete readable record on its own.

Not mirrored here: `raw/` (source JSON) and `resources/images/` (690 files, 200 MB)
stay local in the archive.

## Re-syncing

From the Clief Notes archive root:

```
python tools/mighty_harvest.py --discover --harvest --comments --media
python tools/mighty_harvest.py --lean --captions
python tools/mighty_harvest.py --quizzes --http
python tools/mighty_build_vault.py
```

Login is BU SSO with Duo 2FA on a **session** cookie, so discover and harvest must run
in one invocation. Then copy `vault/`, `membership.json` and `HARVEST-CHECKLIST.md`
over `the-faction/` here.

Personal use only — do not redistribute.
