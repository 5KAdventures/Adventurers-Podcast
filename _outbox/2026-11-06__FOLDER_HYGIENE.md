# Folder hygiene: Adventurers Podcast

**Date:** 2026-11-06 · **By:** `scripts/tidy-folders.py`, run from the estate root.
**Nothing was deleted, built, published or deployed.**

Answers `FOLDER_HYGIENE_PROMPT.md` (28 Oct 2026). Every keep and every refusal below is the result of a search, not of recognising a filename.

| | |
|---|---|
| entries in the root now | 7 |
| archived | 0 |
| in `_to_delete/` for a person to decide on | 5 |
| kept in place as the newest two of their group | 0 |
| **refused** (something names them) | **0** |
| **could not be established** | **0** |

## In `_to_delete/`

OS debris. macOS writes `.DS_Store` back whenever a folder is opened, so this is housekeeping rather than a decision.

- `.DS_Store`
- `_tmp-ep460-q70.webp`
- `_tmp-ep460-q74.webp`
- `_tmp-ep460-q78.webp`
- `index.html.bak-20261008`

## Method

Five refusal rules, each proved by breaking it and watching the pass refuse:

1. this project's own code names the file (ledgers, correspondence and archives excluded — they name files as history, not as dependencies);
2. the file is under a published directory — never a candidate at all;
3. the original no longer exists, so the "backup" is the last copy;
4. it is one of the newest two of its group;
5. `deploy-all.sh` names it;
6. **a sibling project's code names it** — the rule a scheduled mailbox run cannot check, because it is given only its own folder and the Tracker.

Archived files keep their own names and the folder they came from. Nothing was renamed.
