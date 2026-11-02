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
