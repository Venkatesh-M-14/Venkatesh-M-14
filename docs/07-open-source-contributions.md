# 🌍 Open Source Contribution Guide for React Developers

## Beginner-friendly projects that match your stack

| Project | Why it fits you | Where to start |
|---|---|---|
| **MUI (mui/material-ui)** | You use it daily; huge, welcoming community | `good first issue` label; docs fixes; component a11y issues |
| **TanStack Query** | You know the API as a user — docs & examples always need work | `docs` issues, new framework examples, typo/clarity PRs |
| **Redux Toolkit (reduxjs/redux-toolkit)** | Familiar territory; maintainers are responsive | Docs, TypeScript type improvements, reproduction triage |
| **freeCodeCamp** | Largest beginner-friendly repo on GitHub; React codebase | `first timers only` label; curriculum challenge fixes |
| **Storybook** | React + component tooling; lots of scoped issues | `good first issue`; addon docs |
| **react-hook-form** | Small enough to understand end-to-end | Examples folder, TS types, docs |
| **Refine (refinedev/refine)** | React admin framework; actively courts new contributors | `good first issue`; example apps |
| **Appwrite / Supabase docs** | SDK docs for frontend devs; low barrier | Docs + example apps with React |
| **DefinitelyTyped** | Bite-sized TS PRs; great TS practice | Fix/update typings for packages you use |
| **First-timer aggregators** | goodfirstissue.dev, forgoodfirstissue.github.dev, upforgrabs.net | Filter by TypeScript/React |

## How to contribute (the reliable loop)

1. **Use → notice → fix.** The best first issues are papercuts you hit while using the library in your own projects. You already have context; the fix writes itself.
2. **Start with docs/tests, then bugs, then features.** Docs PRs teach you the project's review culture with near-zero risk. Feature PRs come after 3–4 merged PRs.
3. **Read `CONTRIBUTING.md` first.** Every serious repo has one — setup steps, commit conventions, PR rules. Following it exactly is 50% of getting merged.
4. **Claim before coding:** comment "I'd like to work on this" and wait for assignment on repos that require it; otherwise state your intended approach in the issue so maintainers can redirect you early.
5. **Ask in the right channel:** most projects have a Discord — ask setup questions there, not in the issue.

## How to create a proper Pull Request

```bash
# 1. Fork on GitHub, then:
git clone https://github.com/Venkatesh-M-14/<project>.git
cd <project>
git remote add upstream https://github.com/<org>/<project>.git

# 2. Branch off the latest upstream default branch
git fetch upstream
git checkout -b fix/tooltip-focus-trap upstream/main

# 3. Make the change; run THEIR checks locally
npm test && npm run lint

# 4. Commit in their convention (usually Conventional Commits)
git commit -m "fix(Tooltip): restore focus to trigger on Escape"

# 5. Push to your fork and open the PR
git push -u origin fix/tooltip-focus-trap
```

**In the PR description:** link the issue (`Fixes #1234`), explain *why* not just *what*, add before/after screenshots for UI changes, note any tests added, and keep the diff small — one concern per PR. Respond to review feedback within a day or two, and don't take change requests personally: review is the mentorship you're there for.

## How to maintain contribution consistency

- **Schedule it:** one evening per week (e.g., every Wednesday) is enough for 2–4 PRs/month. Consistency over volume — a year of steady green beats a one-month burst.
- **Adopt 1–2 projects** rather than drive-by contributing to twenty. Repeated PRs to the same repo → maintainers recognize you → bigger issues get entrusted to you → eventually triage/commit rights. That trajectory is what impresses interviewers.
- **Keep a contribution log** in a `contributions.md` (or your portfolio): PR link, what it did, what you learned. Gold for interview stories.
- **Mix modes on slow weeks:** triage new issues, reproduce reported bugs, review other PRs, answer questions in Discussions — all of it counts as community credibility (and much of it shows on your graph).
- **Own projects count too:** maintaining `react-hooks-library` with issues/PRs/releases *is* open source. Add `good first issue` labels to your own repos and welcome contributors.
