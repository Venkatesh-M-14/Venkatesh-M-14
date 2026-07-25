# ✍️ Professional Commit History — Conventional Commits

Format: `<type>(<optional scope>): <imperative, lowercase summary ≤ 72 chars>`

Body (optional): the *why*. Footer (optional): `BREAKING CHANGE:`, `Closes #123`.

## Examples by type

### feat — a new capability
```text
feat(cart): persist cart items to localStorage across sessions
feat(auth): add silent token refresh via axios interceptor
feat(dashboard): add date-range filter to revenue chart
feat(table): support server-side sorting and pagination
```

### fix — a bug fix
```text
fix(checkout): prevent double order submission on rapid clicks
fix(search): cancel stale requests when query changes mid-flight
fix(theme): correct contrast ratio of muted text in dark mode
fix(form): show server validation errors on the matching fields
```

### refactor — behavior-neutral restructuring
```text
refactor(products): extract filtering logic into useProductFilters hook
refactor(api): replace hand-rolled fetch wrapper with axios instance
refactor(store): migrate cart slice from createReducer to createSlice
```

### style — formatting only (no logic)
```text
style: apply prettier to src/features/auth
style(sidebar): normalize spacing scale to 4px grid
```

### docs
```text
docs(readme): add environment variable reference table
docs(hooks): document useDebounce options and SSR caveats
docs: add architecture decision record for state management choice
```

### test
```text
test(cart): cover quantity edge cases and empty-cart totals
test(auth): add MSW handlers for login failure scenarios
test(utils): reach 100% branch coverage on currency formatter
```

### perf
```text
perf(list): virtualize product grid, cutting initial render by 60%
perf(images): lazy-load below-the-fold images with loading="lazy"
perf(bundle): code-split admin routes, reducing main chunk by 84kB
```

### build / ci / chore
```text
build: migrate from CRA to Vite
build(deps): upgrade react-query from v4 to v5
ci: add lint and type-check jobs to pull request workflow
ci: cache node_modules to cut workflow time by 2 minutes
chore: add .nvmrc to pin node version for contributors
chore(release): v1.4.0
```

### Breaking change
```text
feat(api)!: rename VITE_API_URL to VITE_API_BASE_URL

BREAKING CHANGE: update your .env files; the old variable is no longer read.
```

## Rules that make history *look* senior

1. **Imperative mood** — "add", not "added"/"adds" (reads as: *this commit will…*).
2. **One logical change per commit.** If the summary needs "and", split it.
3. **Explain why in the body** when the diff can't: `fix(dates): use UTC when parsing API timestamps` + body explaining the timezone bug it caused.
4. **Reference issues** in the footer: `Closes #42`.
5. **Never commit** `wip`, `fix stuff`, `asdf`, `final final` — squash them before pushing.
6. **Enforce it** with tooling so it's automatic: `commitlint` + `husky` (`commit-msg` hook), and `commitizen` if you want a guided prompt. This also unlocks automated changelogs via semantic-release.
