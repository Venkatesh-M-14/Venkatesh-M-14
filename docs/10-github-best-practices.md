# 🧭 GitHub Best Practices

## Branch strategy (recommended: GitHub Flow + dev)

For solo portfolio projects, full Git Flow is overkill. Use a pragmatic middle:

```text
main ──────●────────●──────────●──→   always deployable; releases tagged here
            \      /  \       /
dev ─────────●────●────●─────●───→    integration branch (optional for small repos)
              \  /      \   /
feat/cart ─────●         \ /
fix/login-loop ───────────●
```

- `main` — protected, deployable, release tags only. Enable branch protection: require PR + passing CI.
- `dev` — integration (skip it for tiny repos; branch off `main` directly).
- Working branches: `feat/<slug>`, `fix/<slug>`, `chore/<slug>`, `docs/<slug>` — short-lived, deleted after merge.
- **Merge style:** *squash and merge* → one clean conventional commit per PR, linear history.

**Classic Git Flow** (know it for interviews): adds `release/x.y.z` and `hotfix/x.y.z` branches between `develop` and `main`. Used by teams with scheduled releases; continuous-deploy teams prefer GitHub Flow.

## Commit standards

Conventional Commits everywhere (see [doc 08](08-commit-conventions.md)), enforced by commitlint + husky. Squash-merge PRs so every commit on `main` is meaningful.

## Pull Request template

`.github/PULL_REQUEST_TEMPLATE.md`:

```markdown
## What
<!-- One-sentence summary of the change -->

## Why
<!-- Link the issue: Closes #123 — and give context -->

## How
<!-- Notable implementation decisions, trade-offs -->

## Screenshots / Recording
<!-- Required for UI changes: before / after -->

## Checklist
- [ ] Follows Conventional Commits
- [ ] Tests added/updated
- [ ] Responsive + dark mode verified (UI changes)
- [ ] No console errors or new lint warnings
- [ ] Docs/README updated if behavior changed
```

## Issue templates

`.github/ISSUE_TEMPLATE/bug_report.yml`:

```yaml
name: 🐛 Bug Report
description: Something isn't working
labels: [bug, triage]
body:
  - type: textarea
    id: description
    attributes: { label: What happened?, description: Also tell us what you expected. }
    validations: { required: true }
  - type: textarea
    id: steps
    attributes: { label: Steps to reproduce, placeholder: "1. Go to…\n2. Click…\n3. See error" }
    validations: { required: true }
  - type: input
    id: environment
    attributes: { label: Environment, placeholder: "Chrome 126 / macOS 15" }
```

`feature_request.yml`: problem statement → proposed solution → alternatives considered.

## Labels (consistent across all repos)

| Label | Use |
|---|---|
| `bug` / `enhancement` / `documentation` | Type |
| `good first issue` / `help wanted` | Contribution funnel |
| `priority: high/medium/low` | Triage |
| `status: blocked` / `status: in progress` | Workflow |
| `a11y` / `performance` / `ui` | Domain |

## Milestones

Group issues into shippable versions: `v1.0 — MVP`, `v1.1 — Dark mode & a11y`, `v2.0 — Realtime`. Each milestone gets a due date and closes with a Release. Recruiters browsing issues see a planned, managed project — rare and impressive in personal repos.

## Releases & Semantic Versioning

`MAJOR.MINOR.PATCH`:

- **MAJOR** — breaking change (`2.0.0`): removed/renamed public API, changed required env vars.
- **MINOR** — new backwards-compatible feature (`1.4.0`).
- **PATCH** — backwards-compatible fix (`1.4.1`).

Pre-1.0 (`0.x.y`) signals "API may change". Tag releases (`v1.4.0`), attach auto-generated notes — or let semantic-release do all of it from your commit types (`fix:` → patch, `feat:` → minor, `!`/`BREAKING CHANGE` → major). See [doc 09](09-github-actions.md).

## Repo hygiene checklist (every public repo)

- [ ] Description + emoji + website link set
- [ ] 5–10 topics
- [ ] README from the template, with screenshots
- [ ] LICENSE (MIT)
- [ ] `.env.example`, no secrets ever committed
- [ ] Branch protection on `main` with required CI
- [ ] Issues enabled; templates in place
- [ ] Social preview image uploaded (Settings → General)
