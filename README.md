# MASTIVERSE — HTML/CSS/MD Edition

A mobile-first browser game starter built using **only three file types**:
- `.html` — page structure and game entry point
- `.css` — styling and responsive layout
- `.md` — documentation

No `.js`, `.json`, `.sql`, image, or other file types are included. Interactive game logic is embedded in `index.html` as an inline script so the archive stays within the requested file-type restriction. `styles.css` contains the visual system.

## Contents

- `index.html` — home page and playable game logic
- `styles.css` — responsive design, game dialog, board styling
- `docs/technical-spec.md` — rules and architecture notes
- `docs/deployment.md` — hosting instructions
- `games/rift-realms.md` — Rift Realms rule sheet
- `games/happy-disaster.md` — Happy Disaster rule sheet

## Run on Android

1. Extract the ZIP.
2. Open `index.html` in a modern browser.
3. If your file manager does not execute inline scripts from local files, upload the folder to GitHub and enable GitHub Pages, or use any static hosting provider.
4. Tap **Play now** on a game card.
5. Use **Mode** to switch between local pass-and-play and solo practice.

## Current limits

- Rift Realms: playable 5×5 territory game, local two-player and basic solo AI.
- Happy Disaster: playable simultaneous-choice party game, local pass-and-play and solo opponent.
- Online rooms, server backend, accounts, database persistence, matchmaking and the other planned games are not included in this HTML/CSS/MD-only edition.
- Solo opponent logic is lightweight, not a deep search AI.
- No sound effects are shipped; the Sound control is a UI preference placeholder and does not play audio yet.

## Self-check

After opening the page, open browser developer tools if available and run:

```js
MASTIVERSE.runSelfChecks()
```

It prints four basic checks and returns `true` if all pass.
