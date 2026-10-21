# MASTIVERSE

A mobile-first board-game universe starter with **two playable games**, solo AI, local pass-and-play, and real private-room WebSocket multiplayer when the Node backend is running.

## Included now
- **Rift Realms:** 7×7 territory strategy, shifting blocked Rift, territory score, three heuristic AI difficulty settings.
- **Happy Disaster:** simultaneous secret choices, energy management, rule-based silly events, solo AI.
- Responsive Android/tablet/desktop UI, game rules, rematches, results and match notes.
- Real private room codes, server-side move validation, state-version checks, reconnect tokens, disconnect grace period, duplicate-choice checks, and room creation rate limits.
- PostgreSQL schema starter, environment example, technical spec, deployment guide, and automated tests.

## Not implemented yet
Chaos Council, Echo Tactics, Goblin Engineers and The Grand Convergence; public matchmaking; account authentication; database-backed persistence; persistent rooms across restarts; ranking/leaderboards; cosmetics inventory; payments; sound assets; player reporting; production security audit. The PostgreSQL migration is not connected to runtime persistence. Rift portal markers are decorative in this release.

## Requirements
Node.js 20 or newer and npm.

## Run locally
```bash
npm install
npm test
npm run check
npm start
```
Open `http://localhost:8080`. For real online play, open the URL in two independent browser sessions. Create a room from one, then join with its six-character code from the other. Local and solo games need no account or database.

## Android/tablet
For online play on Android, deploy the Node server to a host that supports WebSockets and open its HTTPS URL. Static GitHub Pages alone cannot run a persistent backend. See `docs/deployment.md`.

## Project layout
```text
client/index.html
client/styles.css
client/src/main.js
shared/game-rules/rift-realms.js
shared/game-rules/happy-disaster.js
server/src/index.js
server/src/rooms.js
database/migrations/001_initial_schema.sql
tests/
docs/
.env.example
```

## Environment
- `PORT`: HTTP port (default 8080).
- `ALLOWED_ORIGINS`: optional comma-separated exact origins for cross-origin WebSocket clients.
- `DATABASE_URL`: reserved for a future adapter; currently unused.
- `NODE_ENV`: environment label.

See `docs/technical-spec.md` for exact rules and `docs/deployment.md` for deployment. This is a functional starter release, not a claim of production readiness or a completed six-game platform.
