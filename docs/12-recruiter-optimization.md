# 🎯 Recruiter Optimization Review

How a recruiter actually evaluates your GitHub — and what to fix, in priority order. A recruiter spends **30–60 seconds** on first pass: profile photo/bio → pinned repos → one README → gone. Optimize for that path.

## 🔴 Critical (do this week)

1. **Rename the profile repo.** `Venkatesh-M-14/Venkatesh-M` will never render on your profile — GitHub requires the repo name to equal the username exactly: rename it to **`Venkatesh-M-14`** (Settings → General → Rename). Everything else in this kit depends on this.
2. **Complete the profile sidebar:** real photo (clear, friendly, decent lighting — not an avatar), name "Venkatesh M", bio (see [doc 13](13-bonus.md)), location, portfolio URL, and public email. Recruiters filter by location and need a one-click contact path.
3. **Pin 6 repos** per [doc 05](05-pinned-repositories.md) — and give every pinned repo a description + live-demo link + topics *today*, even before READMEs are perfect. An empty description under a pin is the most common credibility leak.
4. **Live demos for everything pinned.** Recruiters click demos, not code. Vercel is free; no pinned repo without a working URL.

## 🟠 High impact (next 2–4 weeks)

5. **README screenshots and GIFs.** A README without visuals gets closed in 5 seconds. Banner + 2–3 screenshots + one GIF of the core flow, using the [template](03-readme-template.md).
6. **Consistent commit history.** Aim for 4–5 active days/week even if small (docs count). A graph with months-long gaps triggers "not currently coding" doubts; a steady graph triggers nothing — which is the goal. Never fake it with scripted commits; devs check timestamps and content, and it's an instant reject.
7. **TypeScript visibly dominant.** Your top-languages card should show TS/JS leading. Old tutorial repos in other languages → make private or archive.
8. **CI badges on pinned repos.** A green check says "this person ships working code" without a single line read.
9. **Kill or archive dead repos.** `test-repo`, `untitled-project`, empty forks — each one dilutes the signal. Fewer, better.

## 🟡 Compounding (1–3 months)

10. **Open-source PRs to libraries you use** (MUI, TanStack Query — see [doc 07](07-open-source-contributions.md)). "Contributor to MUI" in a bio outweighs three side projects.
11. **README depth on flagships:** add an "Architecture decisions" section (why Redux Toolkit *and* React Query, why feature-slicing). This is senior-signal — it shows judgment, not just output.
12. **Cross-link everything:** GitHub bio → portfolio → resume → LinkedIn → back to GitHub. Recruiters should never hit a dead end. Put the portfolio URL in the GitHub profile website field and pin `portfolio-v2`.
13. **Match job-post keywords honestly.** Postings say: React, TypeScript, Redux, REST, testing, responsive, accessibility, performance. Ensure those exact words appear in your bio, repo descriptions, and READMEs where true — recruiters keyword-search GitHub too.

## How each recruiter question maps to your profile

| Recruiter's silent question | Answered by |
|---|---|
| "Is this person a real React dev?" | Pinned apps + TS-dominant language card |
| "Are they current or stale?" | Contribution graph + Next.js repo + recent commits |
| "Can they work on a team?" | Conventional commits, PRs to own repos, issue templates, OSS PRs |
| "Will they need hand-holding?" | README quality, CI, tests, architecture notes |
| "Can I contact them?" | Public email, portfolio link, LinkedIn badge |

## The one-line summary

**Six polished, demo-linked, CI-green, screenshot-rich pinned repos + a steady graph + a rendered profile README** beats any amount of quantity. Everything in this kit serves that sentence.
