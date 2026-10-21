# MASTIVERSE — Technical Specification (HTML/CSS/MD edition)

## Goal

Deliver a mobile-first browser prototype with two actually interactive games while restricting the archive to HTML, CSS, and Markdown files only.

## Modules

### Rift Realms
- Board: 5×5 grid.
- Players: Blue (1) and Pink (2).
- Initial positions: Blue at cells 1 and 5; Pink at cells 21 and 25.
- Legal action: move one of your pieces to an adjacent orthogonal neutral tile.
- Portal links: cells 1↔25 and 5↔21.
- Occupied opposing tiles cannot be entered.
- Match limit: 20 turns; higher territory count wins.
- Solo AI: selects a legal move using a simple mobility score and small random tie-breaker.

### Happy Disaster
- Each player chooses one action per round: Build, Dash, or Redirect.
- Choices reveal together after both are locked.
- Calm/slippery/wild hazard cycles across rounds.
- Build: 2 points and restores 1 energy (energy is displayed, capped at 5).
- Dash: 3 points on calm, 1 on slippery, 2 on wild.
- Redirect: 1 point; counters Dash for a bonus.
- Redirect versus Redirect earns a small collision bonus.
- First player to 10 points wins; otherwise the match ends after 7 rounds.
- Solo opponent is labelled AI.

## Interaction requirements
- Touch-sized buttons and board cells.
- Modal dialog can be closed and rematches reset game state.
- Reduced-motion preference is respected.
- Local pass-and-play has separate hidden-choice turns.

## Known limitations
- No authoritative server, online multiplayer, account system, persistent database, matchmaking, telemetry, or moderation backend.
- This edition is a front-end-only prototype; client-side code can be inspected or altered.
- Sound toggle is only a preference indicator; audio assets are not included.
- Balance is a first-pass design and needs playtesting.
