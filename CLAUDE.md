# soup-tools (website) - notes for maintainers and agents

The public website of SOUP Tools, served by GitHub Pages from `main` at https://zachleolewis.github.io/soup-tools/.
Plain HTML and one stylesheet: `index.html`, `privacy.html`, `terms.html`, `style.css`. No build step; a push to `main` deploys it
(workflow `pages-build-deployment`, about a minute).

## Why it matters

Google's OAuth consent screen for Drive Sync (Google Cloud project `soup-tools`) links the home, privacy and terms pages, and
`zachleolewis.github.io` is its authorized domain. Google and players read these pages as the promise of what Drive Sync does.

## Rules

- **The privacy page must stay true.** Change it in the same change that makes SOUP or Drive Sync do something new with data:
  a new Google scope, a new destination, a new kind of file, team sharing. Today it promises: no SOUP servers, Google data only
  between the PC and Google, `drive.file` + `openid` + `email` only, the token in Windows Credential Manager, the Google API
  Limited Use statement.
- Bump "Last updated" on a page whenever its meaning changes.
- Do not rename the repository, move the pages or change their file names: the Google consent screen and Drive Sync's
  `manifest.json` link them. If you must, update both first.
- Do not add analytics, trackers, cookies or third-party scripts (the privacy page says there are none).
- ASCII text; keep the pages readable without CSS.

## Documentation is part of the work

The SOUP Tools owner's rule (2026-11-02) for every agent and contributor in every SOUP Tools repository: keep the documentation
excellent, tidy and current, so the next person or agent can continue the work cold.

1. **Read before you work**: this repository's handover, index and decisions; do not re-derive or re-ask what is written down.
2. **Write as you go**: findings, measurements (with the command, data and machine), decisions (with the reason and who decided),
   dead ends and why, gotchas, and what you could not verify, in the document that owns the topic.
3. **One home per fact**: other documents link to it. Adding, moving or removing a document updates the index that lists it in the
   same commit.
4. **The owner's words are kept word for word**, then turned into numbered decisions; a decision changes by a new entry that
   supersedes the old one.
5. **Status lines and absolute dates** on every plan and spec; superseded documents are archived with a pointer.
6. **Close every session**: update the handover or progress notes, record what you noticed and left, say plainly what was not verified.
7. **A change that touches another SOUP Tools repository** updates that repository's documentation too.
8. **Tidy**: no stale TODOs, no docs or comments describing code that changed, ASCII text.
