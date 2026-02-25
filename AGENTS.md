# Repository Guidelines

## Project Structure & Module Organization
This repository is a single-page web app centered on `phonetic-games.html`.
- HTML markup defines layout and game panels.
- The `<style>` block contains all CSS tokens, animations, and component styles.
- The `<script>` block contains state, game logic (bubble/match/eliminate/maze), audio helpers, and `localStorage` persistence.

There is no build output folder or asset pipeline in this repo. Keep related updates close to existing sections in this file, and avoid introducing new modules unless explicitly requested.

## Build, Test, and Development Commands
- `python3 -m http.server 8000`: serve the project locally from repo root.
- `open http://localhost:8000/phonetic-games.html` (macOS): open the app quickly in a browser.
- `git diff -- phonetic-games.html`: review only relevant UI/logic changes before committing.

Because this is static HTML/CSS/JS, no package install or compile step is required.

## Coding Style & Naming Conventions
- Use 4-space indentation in HTML, CSS, and JavaScript to match existing style.
- Prefer `camelCase` for JavaScript identifiers (for example, `startBubbleGame`, `activeRanges`).
- Default to `const`; use `let` only for mutable game state.
- Reuse CSS custom properties in `:root` before adding new color tokens.
- Keep comments minimal and focused on non-obvious logic.

## Testing Guidelines
No automated test framework is currently configured. Run manual checks for every behavior change:
1. Start local server and load `phonetic-games.html`.
2. Verify start/stop and score behavior for all game modes.
3. Verify range filter selection, mission progress updates, and skin unlock flow.
4. Refresh page to confirm `localStorage` data restores correctly.
5. Validate layout at mobile and desktop widths (for example, 390px and 1280px).

## Commit & Pull Request Guidelines
Current history uses short, action-oriented one-line commit subjects in English or Chinese (for example, `Fix phonetic game start controls`, `调整泡泡龙音标布局和交互`). Keep each commit focused on one change.

For pull requests, include:
- A brief summary of what changed and why
- Manual test steps performed
- Before/after screenshots for UI updates
- Linked issue/task ID when available
