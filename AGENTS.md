# AGENTS.md — Sunny the Bunny Goes to Camp

Notes for coding agents (Codex, etc.) working in this repository.

## What this is
A small 3D browser game for a class assignment ("Homework 6: Build a game"), based on the picture book *Sunny the Bunny: Goes to Camp*. The player walks through 10 story chapters as Sunny, meets 12 animal friends who go into a "Camp Crew" sidebar, and can switch to play as any of them.

## Files
- `index.html`: the entire game (HTML, CSS and JavaScript in one file). There's no build step.
- `pages/`: the book's page images (p05 is the cover, p06–p27 are the story pages in order, p28 is the endpapers).
- `lib/three.min.js`: three.js **r128**, loaded as a global `THREE` (a non-module build). Keep this version; the code uses r128 APIs.
- `README.md`: rules, controls and how to start it. This is a graded deliverable, so keep it accurate.
- `CODEX_TASK.md`: the publishing task (repo, GitHub Pages, collaborator invite).

## Run it
- Double-click `index.html`, or
- run `python3 -m http.server 8000` in this folder and open http://localhost:8000

The game must keep working offline from `file://`. Don't add CDN dependencies for code. The Google Fonts link is optional, and the game falls back to system fonts without it.

## Code map (inside the `<script>` in index.html)
- `STORY` (top of the script, marked "THE BOOK PAGES"): for each chapter, which real book pages (`pages/pNN.jpg`) to show and when. `intro` pages show at the start, `end` pages at the finish, and other keys at story moments through `beat(key)`. Also holds the short `how` hint. The pages are the author's book, so don't replace or alter them.
- `SPEC`: the animal designs (colours, ears, tails, jump and speed stats). `makeAnimal(kind)` builds the 3D model.
- `CH`: the chapter list. Each `chN()` function builds one chapter's level (platforms, items, friends, triggers).
- Modes: `fourSquare`, `sailMode`, `zipMode` and `singMode` are the mini-games. `cut()` runs cutscenes. `card()` shows dialogs, `showPages(list)` shows book pages one at a time, `thumb()` sets the read-along page in the corner, and `beat(key)` shows a chapter's pages for that moment.
- Party: `party` (the friends found), `join()`, `swapTo()` and `renderCrew()` (the sidebar portraits).
- `window.__game` exposes a few hooks for testing (for example `__game.startChapter(3)`).

## Checking changes
1. Syntax check: extract the main `<script>` and run `node --check` on it.
2. Open the game, click **Start the story**, and play at least the chapter you changed. Chapters can be opened from the **Chapters** menu, which unlocks as you play. For testing, run `__game.defaultParty(i); __game.startChapter(i)` in the console.
3. Make sure the browser console shows no errors.

## Conventions
- Keep everything in the single `index.html` unless there's a strong reason to split it.
- Keep controls simple: arrows to move, Space to jump or act, C or a click to swap friends.
- Keep it kid-friendly and easy, because it's played live in class.
