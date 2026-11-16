# 🍓 Fruit Catcher

A browser game built with plain HTML, CSS and JavaScript (no build step, no dependencies).
Catch fruit, dodge bombs, don't let fruit hit the ground. Open `index.html` to play.

**Controls:** ← → or A / D · drag on the canvas · on-screen ◀ ▶ buttons.

## Structure
```
index.html        page + HUD + overlay markup
css/style.css     all styling
js/config.js      constants, fruit list, shared state
js/ui.js          HUD, overlay, high-score (localStorage)
js/renderer.js    canvas drawing
js/input.js       keyboard / touch / buttons
js/game.js        spawning, collisions, scoring, lives, game over
js/main.js        startup
```

## 5-week commit plan

### Week 1 – Project setup & static scene
```
git init -b main
git add README.md && git commit -m "docs: add README"
git add index.html css/style.css && git commit -m "feat: page layout, HUD and overlay styling"
git add js/config.js && git commit -m "feat: add constants, fruit list and game state"
git add js/ui.js && git commit -m "feat: add UI helpers and high-score storage"
git add js/renderer.js && git commit -m "feat: draw background, basket and items on canvas"
git add js/main.js && git commit -m "feat: render idle scene on load"
```
(Before committing index.html, delete the script lines for `input.js` and `game.js` — re-add them in Weeks 2 and 3.)

### Week 2 – Controls
```
git add js/input.js && git commit -m "feat: keyboard controls (arrows / A-D)"
```
Add the `input.js` script tag back to index.html, then commit: `feat: touch drag and on-screen buttons`.
(To make the basket movable before the game loop exists, temporarily call `FC.input.move(0.016)` in a `requestAnimationFrame` loop in main.js, then remove it in Week 3.)

### Week 3 – Core gameplay
Add `js/game.js` in stages (build up the file over several commits):
1. `feat: game loop with delta time`
2. `feat: spawn falling fruit and bombs`
3. `feat: basket collision and scoring`
4. `feat: lives system (missed fruit and bombs)`

Re-add the `game.js` script tag, and restore the `onStart` line in main.js.

### Week 4 – Game flow & difficulty
- `feat: start / game over overlay and play again`
- `feat: persistent best score`
- `feat: difficulty scaling (speed, spawn rate, bomb chance)`
- `fix: frame-rate independent basket movement`

### Week 5 – Polish & release
- `style: responsive tweaks and mobile button polish`
- `refactor: tidy modules and comments`
- `feat: sound effects / pause button` (optional ideas)
- `docs: screenshots and play instructions`
- Deploy: repo **Settings → Pages → Deploy from branch → main / root**
- `git tag v1.0.0`

## Connect to GitHub
```
git remote add origin https://github.com/<you>/fruit-catcher.git
git push -u origin main
```