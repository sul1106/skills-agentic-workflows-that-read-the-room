---
name: update-github-info
description: Refresh the GitHub Info page with useful updates from official GitHub publications.
on:
  schedule: daily
  workflow_dispatch:
permissions:
  contents: read
tools:
  edit:
  web-fetch:
network:
  allowed:
    - github.blog
    - github.com
    - awesome-copilot.github.com
safe-outputs:
  create-pull-request:
    base-branch: main
    draft: false
    reviewers: [mona]
---

# Update GitHub Info

Keep `site/content/github-info.md` current with concise, practical GitHub guidance for developers.

1. Read `notes/mona-notes.md` and the current `site/content/github-info.md` before drafting any changes.
2. Use web-fetch to read https://github.blog/latest/, https://github.blog/changelog/, and https://awesome-copilot.github.com/workflows/.
3. Select only recent items that are useful to developers and fit the page's existing themes. Verify details against the fetched official pages; do not invent claims or dates.
4. Update `site/content/github-info.md` in its existing style. Keep summaries short and practical, retain useful existing content, and include a direct source link whenever a change comes from the GitHub Blog, Changelog, or Awesome Copilot workflows.
5. If there are meaningful updates, create one focused pull request targeting `main` and request review from Mona. Explain the changes and cite the official sources in the pull request description. Do not write or push changes directly to `main`.
6. If there are no meaningful updates, leave the file unchanged and do not create an empty pull request.