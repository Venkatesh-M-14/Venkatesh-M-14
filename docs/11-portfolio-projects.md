# 💼 10 Portfolio-Worthy React Projects (Recruiter-Ranked)

All use the [enterprise folder structure](04-folder-structure.md); estimated times assume evenings/weekends alongside a job.

---

## 1. SaaS Admin Dashboard ⭐ build first
- **Description:** Multi-page analytics platform: KPIs, charts, data tables, user management, settings, RBAC.
- **Difficulty:** Advanced · **Time:** 4–6 weeks
- **Features:** JWT auth + roles, server-side table ops (sort/filter/paginate), Recharts dashboards, CRUD with optimistic updates, dark mode, CSV export, command palette (⌘K).
- **Tech:** React, TypeScript, MUI, React Query, Redux Toolkit, MSW (mock API), Vitest.
- **Structure:** `features/{auth,analytics,users,settings}` slices.
- **Recruiter value: 10/10** — mirrors the exact work of most React jobs; one screenshot communicates competence.

## 2. E-commerce Storefront
- **Description:** Catalog → cart → checkout, the full purchase funnel.
- **Difficulty:** Advanced · **Time:** 4–5 weeks
- **Features:** faceted filters, debounced search, persisted cart, multi-step checkout (RHF + Zod), Stripe test payments, order history.
- **Tech:** React, TypeScript, Redux Toolkit, React Query, Tailwind.
- **Recruiter value: 9/10** — universally understood scope; cart math and forms show real state-modeling skill.

## 3. Real-Time Chat / Collaboration App
- **Description:** Rooms, DMs, presence, typing indicators.
- **Difficulty:** Advanced · **Time:** 3–4 weeks
- **Features:** Socket.io messaging, optimistic sends with retry, infinite history, reactions, unread badges.
- **Tech:** React, TypeScript, Socket.io, Zustand, Tailwind, small Node server.
- **Recruiter value: 9/10** — websocket + optimistic-UI experience is rare at 3 years and a magnet for interview questions you can ace.

## 4. Custom Hooks Library (npm-published)
- **Description:** 20+ typed, tested hooks published to npm with a docs site.
- **Difficulty:** Intermediate–Advanced · **Time:** 2–3 weeks initial, ongoing
- **Features:** tree-shakeable builds (tsup), 100% test coverage, semantic-release CI, live-example docs.
- **Tech:** TypeScript, Vitest, tsup, Storybook/Docusaurus, semantic-release.
- **Recruiter value: 9/10** — "npm author" on a resume changes the conversation; proves API design, not just API use.

## 5. Next.js Full-Stack Dashboard
- **Description:** The SaaS dashboard idea rebuilt with App Router + server components.
- **Difficulty:** Advanced · **Time:** 3–4 weeks
- **Features:** server actions, streaming + Suspense, NextAuth, Prisma/Postgres, metadata SEO.
- **Tech:** Next.js 15, TypeScript, Tailwind, Prisma.
- **Recruiter value: 9/10** — answers "do you know Next.js?" with a repo instead of "basic".

## 6. Kanban Task Manager
- **Description:** Trello-style board with drag-and-drop.
- **Difficulty:** Intermediate · **Time:** 2–3 weeks
- **Features:** dnd-kit drag-drop with keyboard support, labels/due dates, filters, undo toast, localStorage sync.
- **Tech:** React, TypeScript, dnd-kit, Redux Toolkit, MUI.
- **Recruiter value: 8/10** — drag-and-drop + optimistic persistence is a classic machine-coding interview, pre-solved.

## 7. Expense Tracker PWA
- **Description:** Personal finance with budgets, charts, offline support.
- **Difficulty:** Intermediate · **Time:** 2–3 weeks
- **Features:** category budgets with alerts, monthly trend charts, CSV import/export, installable PWA, IndexedDB offline.
- **Tech:** React, TypeScript, RTK Query, Recharts, Dexie, Workbox.
- **Recruiter value: 7/10** — PWA/offline is a differentiator; relatable demo for non-technical screeners.

## 8. Movie / Media Explorer
- **Description:** TMDB-powered browsing with heavy media UX polish.
- **Difficulty:** Intermediate · **Time:** 1–2 weeks
- **Features:** infinite scroll (React Query infinite queries), debounced autocomplete, trailer modals, watchlist, skeletons, lazy images.
- **Tech:** React, TypeScript, React Query, Tailwind.
- **Recruiter value: 7/10** — quick to build yet demonstrates the performance patterns interviewers probe (debounce, virtualization, caching).

## 9. Component Library + Storybook Design System
- **Description:** Your own themed component kit on top of MUI or headless primitives.
- **Difficulty:** Intermediate · **Time:** 2–3 weeks
- **Features:** design tokens, 15+ components with variants, Storybook docs with a11y checks, visual regression (Chromatic).
- **Tech:** React, TypeScript, MUI/Radix, Storybook.
- **Recruiter value: 8/10** — design-system experience is explicitly requested in many mid/senior postings.

## 10. Developer Portfolio v2 (this one!)
- **Description:** Your personal site as a flagship open-source project.
- **Difficulty:** Intermediate · **Time:** 1–2 weeks to polish
- **Features:** GitHub-API project grid, Framer Motion transitions, contact form, OG images, 95+ Lighthouse, blog (MDX).
- **Tech:** React/Next.js, TypeScript, MUI, Framer Motion.
- **Recruiter value: 8/10** — it's the landing page for every other project; polish here multiplies everything else.

---

### Portfolio composition rule

Aim for: **2 large apps** (1, 2) + **1 real-time** (3) + **1 library** (4 or 9) + **1 Next.js** (5) + quick wins (6–8). That mix proves breadth (apps), depth (library), and currency (Next.js) — the three boxes recruiters mentally tick.
