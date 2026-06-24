# AGENTS.md

## Cursor Cloud specific instructions

### What this repo is
- Single static page: `index.html`. No package manager, build step, tests, or lint config.
- `index.html` is a full-page iframe that embeds a Google Apps Script web app (the "One Small Step" Staff Attendance System). The actual application logic lives in that external Apps Script deployment, not in this repo.
- Hosted as a static site on Netlify.

### Running it (dev)
- There are no dependencies to install.
- Serve the file with any static server, for example `python3 -m http.server 8000` from the repo root, then open `http://localhost:8000/index.html`.

### Non-obvious caveats
- The embedded "Sign in with Google" button fails on `localhost` with `Error 400: origin_mismatch` ("Access blocked: Authorization Error"). This is expected: the Apps Script OAuth client allowlists the production Netlify origin, not `localhost`. It is a Google Cloud Console origin configuration matter, not a local environment bug. Full OAuth sign-in only works from the deployed origin.
