# Folder hygiene: Adventurers Podcast

**Date:** 2026-11-07 · **By:** `Claude Apps/scripts/tidy-folders.py`, run from the estate root — not from this project's folder. Rule 6 below needs every project mounted at once, which is the one thing a run inside a single folder cannot have.
**Nothing was deleted, built, published or deployed.**  **This was a `--check` run: nothing moved.**

Answers `FOLDER_HYGIENE_PROMPT.md` (28 Oct 2026). Every keep and every refusal below is the result of a search, not of recognising a filename.

| | |
|---|---|
| entries in the root, counted before this pass (dotfiles included) | 9 |
| archived by this pass | 0 |
| **would** move to `_to_delete/` (nothing moved) | 0 |
| already waiting in `_to_delete/` beforehand | 5 |
| kept in place as the newest two of their group | 0 |
| **refused** (something names them) | **0** |
| **could not be established** | **0** |

The root count is a measurement taken at one moment, not a target: macOS writes `.DS_Store` back whenever anybody opens the folder, so it moves on its own between this pass and your reading of it.

1 piece(s) of debris in this folder could not move, because something of the same name is already waiting in `_to_delete/`. That is the normal settled state, not a fault: the file stays where macOS put it.

## Already in `_to_delete/` before this pass ran

**Not this pass's work**, and listed only because it is what a person opening the folder will actually find. Some of it is older housekeeping and some of it is not debris at all — a spreadsheet or an archive put aside by hand looks exactly like a `.DS_Store` in a list. Read the names before binning any of it.

- `.DS_Store`
- `_tmp-ep460-q70.webp`
- `_tmp-ep460-q74.webp`
- `_tmp-ep460-q78.webp`
- `index.html.bak-20261008`

## Method

Six refusal rules, each proved by breaking it and watching the pass refuse:

1. this project's own code names the file (ledgers, correspondence and archives excluded — they name files as history, not as dependencies);
2. the file is under a published directory — never a candidate at all;
3. the original no longer exists, so the "backup" is the last copy;
4. it is one of the newest two of its group;
5. `deploy-all.sh` names it;
6. **a sibling project's code names it** — the rule a scheduled mailbox run cannot check, because it is given only its own folder and the Tracker.

Archived files keep their own names and the folder they came from. Nothing was renamed.
