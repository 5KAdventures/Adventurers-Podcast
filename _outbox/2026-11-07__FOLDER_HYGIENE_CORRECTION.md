# Correction: the 6 November hygiene report listed files it did not move

**Date:** 2026-11-07 · **By:** the working session, from the estate root
**Corrects:** `_outbox/2026-11-06__FOLDER_HYGIENE.md`, which stays where it is
**Raised by:** Fieldwork, in a correction relayed by Johan on 7 November. Their check was right.

Yesterday's report has a defect, and it is in the one claim the report exists to make.
It was found by Fieldwork checking the report against the folder it describes, and it affects
four projects, not one.

## What went wrong

The report's `_to_delete/` section listed **the contents of that folder**, not what the pass had
put there. Two lines of the generator did it:

- the list was built by reading `_to_delete/` at report time, rather than from the pass's own
  record of what it moved;
- the report was written **before** the moves ran, so every figure in its table — including
  "entries in the root now" — was the state the pass found, printed in the present tense.

A third line dropped anything that was not a file, so a directory sitting in `_to_delete/` was
silently absent from a list and a count that claimed to be complete.

The heading over that list read "OS debris… housekeeping rather than a decision." That sentence is
true of what the pass moves — it only ever moves names macOS or an editor writes by itself — and it
was printed over whatever happened to be in the folder. **A heading that tells a reader not to
think, over a list the pass did not compile, is the worst shape this fault could take.**

## What it actually said, per project

| project | the report listed | the pass really moved there | pre-existing, mislabelled |
|---|---|---|---|
| **5K Utilities** | 14 | **0** | **14** — including a 102 KB `check-fv.py` probe and a 31 KB page backup |
| **Fieldwork** | 5 | 1 | 4 — a spreadsheet, a 6.9 MB zip, a 6.8 MB blob, a stray `.DS_Store` copy |
| **Adventurers Podcast** | 5 | 1 | 4 — three WebP encoding trials and a page backup |
| **Report Writer** | 2 | 1 | 1 |

Blog, Landing, Facts & Figures, Personal Tools and Labs were right by luck: nothing was waiting in
their `_to_delete/` for the bug to pick up.

## Two smaller things, both real

- "**Five** refusal rules" stood above **six** of them. The number was typed, not counted.
- The root count was the figure from **before** the pass, under the word "now".

## Fixed

`scripts/tidy-folders.py`, today. The moves now run before the report is written; the report
separates **"moved to `_to_delete/` by this pass"** from **"already in `_to_delete/` before this
pass ran"**, and says of the second that it is not the pass's work and not necessarily debris;
directories are listed, with a trailing `/`; the rule count is `len(RULES)`; the root count says
when it was taken and that macOS moves it on its own; and the byline gives the script's full path
and why it runs from the estate root.

Proved by running the old and the new generator against a folder built to the same shape:
the old one reported five files it had not touched, the new one reports one move, six waiting, and
names the directory. A `--check` run writes "nothing moved" and moves nothing. The **plan** is
byte-identical between the two scripts across all nine projects — only the reporting changed.

A corrected report for this project is beside this note as
`2026-11-07__FOLDER_HYGIENE.md`. Nothing in any `_outbox/` was altered or removed.
