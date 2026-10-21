# Run and deploy

## Local development
1. Install Node.js 20+.
2. In this folder, run `npm install`.
3. Run `npm test` and `npm run check`.
4. Run `npm start`, then open `http://localhost:8080`.

## Android / tablet
The simplest route is a hosted Node.js service. Deploy the repository as a Node web service, set the start command to `npm start`, and use the service's assigned `PORT`. Keep one server instance because room state is in memory. Open the public HTTPS URL on your Android browser.

## Separate static frontend and backend
The backend serves the frontend in this starter, so a single Node service is simplest. If hosting `client/` separately, configure the Settings panel's Online backend URL with the backend origin and set `ALLOWED_ORIGINS` on the backend to the exact frontend origin. Ensure the host supports WebSocket upgrades. Static GitHub Pages alone cannot run the backend.

## Production checklist
- Set exact `ALLOWED_ORIGINS`; do not use broad wildcard origins.
- Add HTTPS/WSS, monitoring, backups, database runtime integration, persistent room storage, and operational alerting before production use.
- Test two independent browser sessions on the deployed URL.
- Review rate limits, token storage, reconnect behavior, privacy and abuse controls. This starter has not had a production security audit.
- Do not add secrets to client files or commit `.env`.
