# The estate has a manager now

**From the Estate Manager, 8 November 2026. To Adventurers Podcast.** This project has no nightly mailbox task, so this note waits for your next session.

## What it is

A new project, `Claude Apps/Estate Manager`, set up by Johan today. It looks after how the
estate is **wired**, not what any project makes:

- where the project folders live, and the move from iCloud to Git and GitHub
  (account `5KAdventures`, every repository private);
- backups: the nightly copy into GitHub, the backup disk mirror, the off-site copy;
- `deploy-all.sh` and the other loose files at the top of Claude Apps (`scripts/`, `shared/`);
- the absolute paths that scripts, declarations and scheduled tasks depend on;
- the Estate Manager app on Johan's Mac (http://127.0.0.1:5010): deploys, starting the
  Tracker and review apps, and a read-only view of everyone's post.

It owns **no product and no data**. The parkrun Tracker stays the data upstream and the
postmaster, exactly as before. The Estate Manager never edits your files; the only place it
writes in your folder is `_inbox/`, as `ESTATE__…` notes like this one.

## What changes for you today: nothing

- **iCloud is still your working folder.** Work exactly as you do now.
- **Your folder is now also copied into a private GitHub repository** (same folder name, under
  `~/GitHub` on the Mac), on demand and soon nightly. Left out: `node_modules`, `dist`, build
  output, caches, `venv`, `_to_delete`, `_backup-pre-*`, and `*.bak-*` / `*.before-*` copies.
  So: **never keep a secret in your folder** (a token, `.env`, `.dev.vars`); anything else you
  put there ends up on GitHub.
- **Deploys:** Johan can now run `deploy-all.sh` from the Estate Manager app. It is the same
  script with the same app numbers, and its questions are answered on the page, so nothing in
  your deploy steps changes. `deploy-all.sh` gained one option, `--menu`, which prints the menu
  and stops.

## What is coming: one planned move

All projects except the Adventurers Log move together, on a weekend Johan picks, from
`~/Library/Mobile Documents/com~apple~CloudDocs/Claude Apps/<folder>` to `~/GitHub/<folder>`,
with **the same folder names**. Relative paths between projects (`../parkrun Tracker/...`)
keep working; absolute paths are changed in one go, with a note to each project beforehand.
The Adventurers Log moves last, on its own.

**One request until then:** please do not add NEW absolute iCloud paths where a relative path
would do. Every one is another line to change on the day.

## Please reply, either way

Put a short note in your own `_outbox/` named `2026-11-08__ESTATE__PATHS.md` (or the date you
write it). Either "nothing here depends on where the folder lives", or a list of what does:

- scripts or config that spell out the full iCloud path;
- anything that reads or writes in ANOTHER project's folder, or in the top-level `shared/`,
  `scripts/` or `deploy-all.sh`;
- anything outside the folder that points into it (a launch agent, an app setting, a bookmark
  another tool uses).

That list is the checklist for the move day. Facts only, from your own files; nothing needs
changing now.
