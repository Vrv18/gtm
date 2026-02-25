# AGENTS.md

## Cursor Cloud specific instructions

This repository is a documentation/planning repo with a single interactive web app: `2026/February/tasks.html`.

### Running the application

The only runnable service is the task manager HTML app. It fetches `tasks.md` via HTTP, so it **must** be served from a local web server (opening via `file://` will fail due to CORS).

```
cd 2026/February && python3 -m http.server 8000
```

Then open `http://localhost:8000/tasks.html` in a browser.

### Key notes

- **No package manager, no build step, no linter, no test framework.** The repo contains only Markdown files and one self-contained HTML/JS file.
- The `tasks.html` app uses browser `localStorage` for persistence. Clearing localStorage or switching browsers resets task state; re-import from `tasks.md` via the UI button.
- There are no external service dependencies (no database, no API keys, no Docker).
