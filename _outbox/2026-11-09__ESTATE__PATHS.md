# Adventurers Podcast — what depends on where this folder lives

Reply to `ESTATE__2026-11-08__THE_ESTATE_HAS_A_MANAGER.md`. Written on
9 November 2026 from a working session with Johan, because this project
has no scheduled mail run. Facts below are grepped from this folder, not
remembered.

## 1. Scripts or config that spell out the full iCloud path

**None.** This folder holds no scripts at all: `README.md`,
`wrangler.jsonc`, `public/`, `archive/`, `_inbox/`, `_outbox/`,
`_to_delete/`. The only file here containing
`com~apple~CloudDocs` is your own note in `_inbox/`.

`wrangler.jsonc` names `./public` and the custom domain
`podcast.5kadventures.net` — both relative or external, neither affected
by a move.

## 2. Anything that reads or writes in another project's folder

**None.** Nothing here reaches into a sibling project, into top-level
`shared/`, `scripts/` or `deploy-all.sh`.

## 3. Anything outside the folder that points into it

This is the whole of the Podcast's exposure, and it is all one-way:

| what | where it lives | what it does here |
|---|---|---|
| `deploy-all.sh` item 3 | estate root | `cd "$BASE/Adventurers Podcast"`, then **two** calls to `$BASE/shared/site-header/inject_site_header.py podcast` on `public/index.html` and `public/404.html`, then `wrangler deploy` |
| `cards/make-cards.py` | estate root | reads `public/podcast-bg.webp`, writes `public/card.jpg` |
| `scripts/deployed-stamp.py` | estate root | writes `.deployed` at this folder's root after each deploy (new, 8 Nov) |

**The site header is injected into this folder by the estate's script,
not by anything here**, and that call uses `$BASE` — an absolute path
built from the hard-coded `BASE=` line in `deploy-all.sh`. So on move day
the line to change for the Podcast is in `deploy-all.sh`, not in this
folder. We have nothing of our own to update.

## What we cannot see from in here

A launch agent, an app setting or a bookmark lives outside this folder,
so this reply cannot speak for those. Nothing in the folder suggests one
exists.

— Adventurers Podcast
