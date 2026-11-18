# Codex task: build and publish "Sunny the Bunny Goes to Camp" (Homework 6)

You've been given these files:
- `index.html`: the whole game. **Don't change the game code.**
- `README.md`: the README for the repo
- `AGENTS.md`: notes about the code. Read this first.
- `CODEX_TASK.md`: this file
- `sunny-pages.zip`: the book's page images (p05.jpg–p28.jpg)

Do these steps in order. Stop and ask me if something fails.

1. **Set up the folder.** Make a folder `sunny-camp-game/`. Put `index.html`, `README.md`, `AGENTS.md` and `CODEX_TASK.md` in it.
2. **Add the book pages.** Unzip `sunny-pages.zip` into `sunny-camp-game/pages/`, so you end up with `pages/p05.jpg` through `pages/p28.jpg` (24 images). Don't commit the zip itself.
3. **Add the 3D library.** Download three.js r128 into `sunny-camp-game/lib/three.min.js`:
   `curl -L -o lib/three.min.js https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js`
   (or `npm pack three@0.128.0` and copy `build/three.min.js` out of it). If neither works, skip this step. `index.html` falls back to the online copy automatically.
4. **Test it.** Run `python3 -m http.server 8000` in the folder, then check that `/`, `/pages/p06.jpg` and `/lib/three.min.js` all return HTTP 200.
5. **Fill in my name.** Ask me for my full name (and any group members). In `README.md`, replace `_Your Name Here_` with it.
6. **Create the GitHub repo and push.** Run `gh auth status` first; if I'm not logged in, ask me to run `gh auth login`. Then:
   `git init -b main && git add . && git commit -m "Sunny the Bunny Goes to Camp: Homework 6"`
   `gh repo create sunny-camp-game --public --source=. --remote=origin --push`
   (If that name is taken, use `sunny-the-bunny-camp`.)
7. **Turn on GitHub Pages:**
   `gh api -X POST repos/{owner}/{repo}/pages -f "source[branch]=main" -f "source[path]=/"`
   Then check `gh api repos/{owner}/{repo}/pages` until `status` is `built`, and note the `html_url`.
8. **Add the play link.** In `README.md`, replace `_add your GitHub Pages link here_` with the Pages URL. Commit and push.
9. **Check that it's live.** `<pages-url>`, `<pages-url>pages/p06.jpg` and `<pages-url>lib/three.min.js` should all return 200.
10. **Invite my professor:**
    `gh api -X PUT repos/{owner}/{repo}/collaborators/apostolosfilippas -f permission=push`
11. **Report back** with the repo URL (this is what I submit), the play link, and whether the invite was sent.

Don't commit secrets, tokens or `.env` files.
