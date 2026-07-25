# ⚙️ GitHub Actions Workflows for React Projects

Drop these into `.github/workflows/` of any project repo. All use Node 20, npm cache, and least-privilege permissions.

## 1. React CI — lint, type-check, test, build (`ci.yml`)

```yaml
name: CI

on:
  push:
    branches: [main, dev]
  pull_request:
    branches: [main, dev]

permissions:
  contents: read

concurrency:
  group: ci-${{ github.ref }}
  cancel-in-progress: true

jobs:
  lint:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with: { node-version: 20, cache: npm }
      - run: npm ci
      - run: npm run lint
      - run: npx prettier --check .

  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with: { node-version: 20, cache: npm }
      - run: npm ci
      - run: npm run test -- --coverage
      - uses: actions/upload-artifact@v4
        if: always()
        with: { name: coverage, path: coverage/ }

  build:
    runs-on: ubuntu-latest
    needs: [lint, test]
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with: { node-version: 20, cache: npm }
      - run: npm ci
      - run: npm run build          # runs tsc -b && vite build → type-check included
      - uses: actions/upload-artifact@v4
        with: { name: dist, path: dist/ }
```

## 2. Deploy to Vercel (`deploy-vercel.yml`)

> Simplest path: connect the repo in the Vercel dashboard (zero YAML). Use this workflow when you want deploys gated behind CI.

```yaml
name: Deploy to Vercel

on:
  push:
    branches: [main]

permissions:
  contents: read

jobs:
  deploy:
    runs-on: ubuntu-latest
    environment: production
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with: { node-version: 20, cache: npm }
      - run: npm i -g vercel
      - run: vercel pull --yes --environment=production --token=${{ secrets.VERCEL_TOKEN }}
      - run: vercel build --prod --token=${{ secrets.VERCEL_TOKEN }}
      - run: vercel deploy --prebuilt --prod --token=${{ secrets.VERCEL_TOKEN }}
```

Secrets needed: `VERCEL_TOKEN` (+ `VERCEL_ORG_ID`, `VERCEL_PROJECT_ID` via `vercel link`).

## 3. Deploy to GitHub Pages (`deploy-pages.yml`)

```yaml
name: Deploy to GitHub Pages

on:
  push:
    branches: [main]
  workflow_dispatch:

permissions:
  contents: read
  pages: write
  id-token: write

concurrency:
  group: pages
  cancel-in-progress: true

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with: { node-version: 20, cache: npm }
      - run: npm ci
      - run: npm run build
        env:
          BASE_URL: /${{ github.event.repository.name }}/   # set Vite `base` from this
      - uses: actions/upload-pages-artifact@v3
        with: { path: dist }

  deploy:
    needs: build
    runs-on: ubuntu-latest
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    steps:
      - id: deployment
        uses: actions/deploy-pages@v4
```

> Remember `base: process.env.BASE_URL ?? '/'` in `vite.config.ts`, and for SPA routing on Pages copy `index.html` → `404.html` in the build.

## 4. Release automation (`release.yml`)

Uses semantic-release: your Conventional Commits drive the version bump, changelog, git tag, and GitHub Release automatically.

```yaml
name: Release

on:
  push:
    branches: [main]

permissions:
  contents: write
  issues: write
  pull-requests: write

jobs:
  release:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
        with: { fetch-depth: 0 }
      - uses: actions/setup-node@v4
        with: { node-version: 20, cache: npm }
      - run: npm ci
      - run: npx semantic-release
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
          # NPM_TOKEN: ${{ secrets.NPM_TOKEN }}   # only for npm packages (react-hooks-library)
```

`.releaserc.json`:

```json
{
  "branches": ["main"],
  "plugins": [
    "@semantic-release/commit-analyzer",
    "@semantic-release/release-notes-generator",
    "@semantic-release/changelog",
    "@semantic-release/github",
    ["@semantic-release/git", { "assets": ["CHANGELOG.md", "package.json"] }]
  ]
}
```

## Which repos get which workflows

| Repo type | ci.yml | deploy | release.yml |
|---|---|---|---|
| Apps (dashboard, ecommerce…) | ✅ | Vercel | optional |
| Library (react-hooks-library) | ✅ | — | ✅ + npm publish |
| Demo/static (weather, movie) | ✅ | GitHub Pages | — |
| Profile repo | snake.yml only | — | — |

A green **CI badge** in each README is the visible payoff — add `[![CI](…/actions/workflows/ci.yml/badge.svg)](…/actions)`.
