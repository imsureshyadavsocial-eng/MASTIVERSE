# Deployment Guide

## Simplest: GitHub Pages (static frontend)

1. Create a GitHub repository named `mastiverse`.
2. Upload the complete extracted folder structure, including `index.html`, `styles.css`, `README.md`, `docs/`, and `games/`.
3. In the repository, open **Settings → Pages**.
4. Select **Deploy from a branch**, choose `main` and `/ (root)`, then save.
5. Wait for GitHub Pages to publish the site. Open the provided URL on your phone or tablet.

## Local opening

Open `index.html` in a modern browser. If local-file restrictions prevent inline scripts from running, use GitHub Pages or another static host.

## Important
GitHub Pages only serves static files. This edition has no backend and therefore cannot provide real online rooms, authoritative online moves, accounts, or matchmaking. Those features require a separately deployed server and, for persistent data, a database.
