# AGENTS.md

## Cursor Cloud specific instructions

- This repo is a single static `index.html` (the "One Small Step" Staff Attendance System). There is no package manager, build step, or dependencies to install.
- `index.html` is a thin shell: it embeds an `<iframe>` pointing at an externally hosted Google Apps Script web app. All real application logic lives in that Apps Script, not in this repo. Loading the rendered app therefore requires outbound internet access to `script.google.com`.
- Run locally by serving the repo root as static files, e.g. `python3 -m http.server 8000`, then open `http://localhost:8000/index.html`. There is no separate dev/build/prod distinction.
- No lint or automated test setup exists in this repo.
- The app is deployed as a static site (root as publish dir). Editing app behavior means editing the external Apps Script, not this repo.
