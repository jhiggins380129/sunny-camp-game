# Sunny the Bunny Goes to Camp

A 3D storybook platformer based on the children's picture book *Sunny the Bunny: Goes to Camp* by Jace Higgins & Paige Bekish.

**Made by:** Jaycee Dally

**Play online:** [Play Sunny The Bunny Goes to Camp Play-through](https://jhiggins380129.github.io/sunny-camp-game/)

## The goal

Sunny is nervous about her first sleepaway camp. Help her get through all 10 chapters of the story, from packing at home to winning the talent show. You read the real pages of the book as you go: each chapter opens on its page, and then you play that part of the story.

Along the way, find all 12 camp friends. Each friend you meet goes into the **Camp Crew** sidebar, and you can click any of them to play as that animal. Friends you haven't met yet show as silhouettes, so you can see who you missed and play again to find them.

## Controls

| Key | What it does |
| --- | --- |
| ← → (or A / D) | Walk |
| Space (or ↑ / W) | Jump, and do the chapter's action (pass the ball, twirl, sing, pose) |
| C (or Tab) | Swap to the next friend in your crew |
| 1–9, or click a friend in the Camp Crew sidebar | Swap to a specific friend |
| Space / Enter | Close a story card |

On a phone or tablet, on-screen buttons appear instead.

## The chapters

Each chapter opens on the book's own pages, then you play that part of the story:

1. Pack the cupcake, book, lunch box, carrots and beets, then go to Mom and Dad at the door.
2. Get on the bus, then find Cabin 5.
3. Carry 5 sticks to the fire pit.
4. Pick up the letter at the mail house, then play four square: press Space when the red ball comes to you (5 passes).
5. Put on the tutu, hop on stage and twirl 3 times.
6. Collect 6 popcorns, then sit down by the movie screen.
7. Put on a life vest, sail across the lake (← → steer, Space bounces), then eat lunch and nap.
8. Grab a lei and dance by the music, climb the mountain, then ride the zip-line.
9. Walk to the microphone and press Space when each note reaches the yellow circle (5 or more to win).
10. Do warrior pose on a mat, grab your trunk, and find Mom and Dad at the gate.

The end screen shows how many of the 12 camp friends you found.

## How to start it

There's nothing to install.

1. Download or clone this repository.
2. Open `index.html` in Chrome, Edge, Firefox or Safari (double-click it).
3. Click **Start the story**.

The 3D library ([three.js](https://threejs.org), r128) is included in `lib/`, so the game also runs without an internet connection. With internet it also loads the Chewy and Nunito fonts from Google Fonts. Without internet it falls back to system fonts, and everything still works.

Your progress is saved in the browser. Click **Chapters** to jump to any chapter you've already unlocked.

## The book pages

The game tells the story with the real pages of *Sunny the Bunny: Goes to Camp*. Each chapter opens on the matching page or pages of the book, more pages turn as you reach those moments in the story, and the current page stays in the bottom-left corner. Click it to read it again.

The page images are in the `pages/` folder (`p05.jpg` is the cover, then `p06.jpg` to `p27.jpg` in story order, and `p28.jpg` is the endpapers). Which pages show in which chapter is set in the `STORY` block near the top of `index.html`.

## Files

- `index.html`: the whole game (HTML, CSS and JavaScript)
- `pages/`: the book's pages, shown as you play
- `lib/three.min.js`: the three.js 3D library (MIT license, see `lib/three-LICENSE.txt`)
- `AGENTS.md`: notes for AI coding agents working on the code
- `CODEX_TASK.md`: the steps used to publish this repo

## Credits

Story, characters and settings are from *Sunny the Bunny: Goes to Camp* by Jace Higgins & Paige Bekish (Greenleaf Book Group / River Grove Books, 2020). All text and story in the game come from the book's own pages. The 3D models are built in code from simple shapes, based on the book's illustrations.
