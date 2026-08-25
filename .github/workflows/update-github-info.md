---
name: update-github-info

on:
  schedule:
    - cron: "17 8 * * *"
  workflow_dispatch:

permissions:
  contents: read

tools:
  github:
    toolsets: [repos]
  edit:
  web-fetch:

network:
  allowed:
    - github.blog
    - github.com
    - awesome-copilot.github.com

safe-outputs:
  create-pull-request:
---

# Update GitHub Info

Refresh Mona's GitHub information page with useful, current updates from official GitHub sources.

## Instructions

1. Read `notes/mona-notes.md` with the GitHub repository API tools. Use GitHub repository API tools, not terminal, CLI, or sandboxed commands, for repository guidance and reference files.
2. Use `web-fetch` to read the external public guidance at https://github.blog/latest/, https://github.blog/changelog/, and the Awesome Copilot workflows at https://awesome-copilot.github.com/workflows/.
3. Identify recent items that fit Mona's editorial guidance. Keep the summaries short, practical, and useful to developers learning GitHub.
4. Update only `site/content/github-info.md` with the selected information. Include the source URL for every added or changed item.
5. Review the diff for accuracy, clarity, and source attribution.
6. Use the `create-pull-request` safe output to open a pull request containing the update for Mona to review. Do not write directly to the default branch.