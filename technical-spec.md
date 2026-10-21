# MASTIVERSE technical specification (starter)

## Release scope
Two complete local rulesets: Rift Realms and Happy Disaster. The client is vanilla JavaScript with no build step. The Node HTTP server serves the static client and `/ws` WebSocket endpoint. Online rooms are authoritative in the server process; the browser submits actions, never a claimed final result.

## Rift Realms rules
- Board: 7×7, 49 tiles; center tile starts as the active Rift and is unavailable for the first move.
- Two players alternate claiming one empty tile per turn. The active Rift blocks one tile and shifts by 11 positions every three successful turns, skipping an occupied destination.
- Each claimed tile is one point. First to 12 wins; otherwise the game ends when the board is full or the next player has no legal moves. Highest score wins; equal scores tie.
- Portals are corner markers for visual landmarks only in this release; they do not teleport pieces. This is an intentional scope cut from the broader concept.
- AI Easy chooses randomly; Medium/Hard use a simple positional heuristic with reduced randomness at Hard. This is not deep search.

## Happy Disaster rules
- Seven simultaneous-choice rounds. Choices: Dash costs 1 energy, Trick costs 2, Guard costs 1. Energy starts at 3, maximum 4, and each round restores 1 after resolution.
- Dash vs Trick: Dash scores 2. Trick vs Guard: Trick scores 2. Dash vs Guard: Dash scores 1. Equal Dash/Trick score 1 each; equal Guard restores 1 energy each. Every third round includes a deterministic silly bonus point event.
- Highest points after round 7 wins; ties are allowed. Both choices are validated before resolution.
- Solo AI chooses using simple heuristics; difficulty labels are approximate, not calibrated skill ratings.

## Online protocol
WebSocket JSON messages: `createRoom {game}`, `joinRoom {code}`, `reconnect {code,player,token}`, and `act {code,version,move}` for Rift or `act {code,version,choice}` for Happy. Server broadcasts state with monotonically increasing `version`. Online room state is held in memory, so restart loses rooms. Reconnect tokens are bearer secrets stored client-side. Do not share them.

## Known limitations
No user accounts, database runtime adapter, public matchmaking, ranking, chat, reporting workflow, server clustering, persistent rooms, production security audit, or advanced search AI. The database migration is a schema starter, not connected persistence. Google Fonts is optional and requires internet; local fonts are fallback. Sound controls are not implemented beyond a settings placeholder. Verify all features in the target deployment before public launch.
