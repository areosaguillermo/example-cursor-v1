# Example Cursor V1 — Express API

A minimal Node/Express API skeleton with a `/health` endpoint, Jest tests, and GitHub Actions CI.


Deploy

## Requirements
- Node.js 20+
- npm 9+

## Install dependencies
```bash
npm ci
```

If you see npm permission/cache errors on your machine, use a project-local cache:
```bash
npm config set cache .npm_cache --location=project
npm ci
```

## Run locally
- Development (auto-reload):
```bash
npm run dev
```
- Start server:
```bash
npm start
```
- Health check (in another terminal):
```bash
curl http://localhost:3000/health
# -> {"status":"ok"}
```

## Run tests
- Once:
```bash
npm test
```
- Watch mode:
```bash
npm run test:watch
```

## CI on Pull Requests
- Tests run automatically on pull requests targeting `develop` via GitHub Actions (`.github/workflows/test.yml`).

## Gitflow: how to push changes
1. Ensure your `develop` is up to date:
```bash
git checkout develop
git pull origin develop
```
2. Create a feature branch from `develop`:
```bash
git checkout -b feature/<short-kebab-summary>
```
3. Make your changes and commit using Conventional Commits:
```bash
git add -A
git commit -m "feat(api): add new endpoint"
```
4. Push your branch to origin:
```bash
git push -u origin feature/<short-kebab-summary>
```
5. Open a Pull Request into `develop`. Ensure CI checks are green before merging.

For more details, see `.cursorrules` in the repo root.
