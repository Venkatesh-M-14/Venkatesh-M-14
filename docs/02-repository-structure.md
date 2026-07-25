# 📦 Repository Portfolio Plan — 20 Professional Repositories

Every repo below follows the same standards: the [reusable README template](03-readme-template.md), the [enterprise folder structure](04-folder-structure.md), conventional commits, CI via GitHub Actions, a live demo, and 5–10 topics.

**Tier legend:** 🥇 Flagship (pin these, invest most) · 🥈 Strong supporting · 🥉 Learning/knowledge repos

---

## 🥇 1. react-admin-dashboard

- **Purpose:** Enterprise analytics dashboard proving you can build data-heavy, role-aware UIs — the #1 thing product companies hire React devs for.
- **Features:** JWT auth + protected routes, role-based access (admin/manager/viewer), interactive charts (Recharts), server-side paginated/sortable/filterable data tables, dark/light theme, CRUD with optimistic updates, CSV export, responsive sidebar layout, skeleton loading states.
- **Tech Stack:** React 18, TypeScript, MUI v6, React Query, Redux Toolkit (auth/UI state), React Router v7, Recharts, Vite, Vitest + RTL.
- **Folder Structure:** full enterprise layout (see doc 04) with `features/{auth,dashboard,users,reports}` slices.
- **README:** template + architecture diagram, screenshots of every page in both themes, demo credentials table (`admin@demo.com / demo123`).
- **Future Improvements:** websocket live metrics, i18n, audit-log page, E2E suite with Playwright.

## 🥇 2. react-ecommerce

- **Purpose:** The classic "can you build a real product?" proof — most recruiter-recognizable project type.
- **Features:** product catalog with faceted filters + debounced search, product detail with image gallery, cart (persisted to localStorage), multi-step checkout with form validation (React Hook Form + Zod), wishlist, order history, Stripe test-mode payment, auth.
- **Tech Stack:** React, TypeScript, Redux Toolkit (cart), React Query (catalog), Tailwind CSS, React Router, Vite.
- **Folder Structure:** `features/{catalog,cart,checkout,orders,auth}` + shared `components/ui`.
- **README:** template + GIF of the checkout flow, Lighthouse score screenshot.
- **Future Improvements:** product reviews, coupon engine, admin panel, SSR with Next.js.

## 🥇 3. portfolio-v2

- **Purpose:** Your personal site — the link recruiters actually click. (You already have this repo; polish it to flagship level.)
- **Features:** hero with animated intro, projects grid pulling from GitHub API, skills matrix, experience timeline, contact form (EmailJS), dark mode, Framer Motion page transitions, 95+ Lighthouse, SEO meta + OG images.
- **Tech Stack:** React, TypeScript, MUI, Framer Motion, Vite.
- **Future Improvements:** blog section (MDX), analytics, resume-download CTA.

## 🥇 4. react-chat-app

- **Purpose:** Real-time is a differentiator — few 3-year devs show websockets competence.
- **Features:** rooms & DMs, typing indicators, online presence, message reactions, unread counts, infinite scroll history, emoji picker, image sharing.
- **Tech Stack:** React, TypeScript, Socket.io client, Zustand or Redux Toolkit, Tailwind, small Node/Express + Socket.io server in `/server`.
- **Future Improvements:** read receipts, message search, push notifications, voice notes.

## 🥇 5. react-hooks-library

- **Purpose:** A published npm package proves library-author skill: API design, typing, testing, docs.
- **Features:** 20+ hooks (`useDebounce`, `useLocalStorage`, `useFetch`, `useIntersectionObserver`, `useMediaQuery`, `useClickOutside`, `useCopyToClipboard`, `usePrevious`, `useEventListener`…), 100% typed, tree-shakeable, zero deps, docs site with live examples.
- **Tech Stack:** TypeScript, tsup, Vitest, Storybook or Docusaurus, changesets for releases, npm publish via CI.
- **Folder Structure:** `src/hooks/<hookName>/{index.ts, hook.test.ts, README.md}`.
- **Future Improvements:** SSR-safety audit, codemods, benchmark suite.

## 🥇 6. nextjs-dashboard

- **Purpose:** Shows you're ahead of the curve on Next.js App Router / RSC — increasingly a job requirement.
- **Features:** App Router, server components + server actions, streaming with Suspense, route groups, `next/image` optimization, metadata API SEO, Postgres via Prisma (or mock API), auth with NextAuth.
- **Tech Stack:** Next.js 15, TypeScript, Tailwind, Prisma, NextAuth.
- **Future Improvements:** partial prerendering, edge runtime endpoints, multi-tenant theming.

---

## 🥈 7. expense-tracker

- **Purpose:** Relatable domain; shows state modeling, derived data and charts.
- **Features:** income/expense CRUD, categories, monthly budgets with alerts, charts (spend by category/month), recurring transactions, CSV import/export, PWA offline support.
- **Tech Stack:** React, TypeScript, Redux Toolkit + RTK Query, Recharts, MUI, Vite, IndexedDB (Dexie).
- **Future Improvements:** multi-currency, receipt image OCR, shared household budgets.

## 🥈 8. employee-management-system

- **Purpose:** CRUD + forms + tables at scale — the day job of most frontend roles.
- **Features:** employee directory with virtualized table, advanced filters, multi-step onboarding form, org-chart view, leave management, role-based views, bulk actions.
- **Tech Stack:** React, TypeScript, MUI DataGrid, React Query, React Hook Form + Zod, json-server or MSW mock API.
- **Future Improvements:** payroll module, document uploads, audit trail.

## 🥈 9. hospital-management-ui

- **Purpose:** Complex-domain UI (scheduling, dashboards) with accessibility focus — great talking point.
- **Features:** appointment calendar (drag-drop), patient records, doctor availability, triage queue board, stats dashboard, printable prescriptions, WCAG-AA a11y.
- **Tech Stack:** React, TypeScript, MUI, FullCalendar, React Query, MSW.
- **Future Improvements:** bed occupancy heatmap, HL7-style data mock, offline mode.

## 🥈 10. react-food-ordering

- **Purpose:** Consumer UX polish — animations, mobile-first design, cart math.
- **Features:** restaurant list with geolocation mock, menu with variants/add-ons, cart with per-item customization, live order-status tracker (stepper + socket mock), ratings.
- **Tech Stack:** React, TypeScript, Tailwind, Framer Motion, Zustand, Vite.
- **Future Improvements:** delivery map view, split-the-bill, loyalty points.

## 🥈 11. authentication-system

- **Purpose:** Auth is asked about in every interview; this is your reference implementation.
- **Features:** login/register/forgot/reset flows, JWT with silent refresh (interceptors), protected & role-based routes, session expiry handling, OAuth (Google) demo, form validation, rate-limit UX.
- **Tech Stack:** React, TypeScript, React Router, Axios interceptors, React Hook Form + Zod, small Express mock backend.
- **Future Improvements:** MFA/TOTP, passkeys (WebAuthn), device management screen.

## 🥈 12. weather-dashboard

- **Purpose:** Clean API-integration showcase; small but extremely polished.
- **Features:** city search with autocomplete, current + 7-day forecast, hourly chart, geolocation, unit toggle, dynamic backgrounds by condition, request caching with React Query.
- **Tech Stack:** React, TypeScript, React Query, Tailwind, OpenWeather API, Vite.
- **Future Improvements:** radar map layer, severe-weather alerts, PWA install.

## 🥈 13. movie-search

- **Purpose:** Demonstrates infinite scroll, debouncing, and media-heavy UI performance.
- **Features:** TMDB search with debounce, infinite scroll, detail modal with trailers, watchlist (localStorage), genre filters, skeleton loaders, lazy images.
- **Tech Stack:** React, TypeScript, React Query (infinite queries), Tailwind, Vite.
- **Future Improvements:** recommendations row, actor pages, virtualized grids.

## 🥈 14. task-management

- **Purpose:** Drag-and-drop + optimistic updates — a favorite interview topic.
- **Features:** kanban board (dnd-kit), boards/lists/cards, labels & due dates, filters, activity log, keyboard shortcuts, optimistic drag persistence.
- **Tech Stack:** React, TypeScript, dnd-kit, Redux Toolkit, MUI, Vite.
- **Future Improvements:** collaboration cursors, calendar view, recurring tasks.

## 🥈 15. blog-frontend

- **Purpose:** Content rendering, SEO, and pagination patterns.
- **Features:** post list with pagination, markdown/MDX rendering with syntax highlighting, tags & search, reading-time, comments UI, RSS, dark mode.
- **Tech Stack:** Next.js, TypeScript, Tailwind Typography, Contentlayer or REST mock.
- **Future Improvements:** newsletter signup, view counts, related-posts algorithm.

---

## 🥉 16. mui-components

- **Purpose:** Your personal MUI design system — proves theming depth (`createTheme`, component slots, variants).
- **Features:** custom theme with tokens, 15+ extended components (StatCard, ConfirmDialog, FileUpload, Stepper form…), Storybook with controls & a11y addon, visual regression via Chromatic.
- **Tech Stack:** React, TypeScript, MUI v6, Storybook, Vitest.
- **Future Improvements:** Figma token sync, dark-theme audit, npm publish.

## 🥉 17. react-query-examples

- **Purpose:** Teachable-depth recipes for the most-wanted data library.
- **Features:** one runnable example per pattern — pagination, infinite scroll, optimistic updates, dependent queries, prefetching, cache invalidation, mutations with rollback, offline/persist, SSR hydration — each with an explanation README.
- **Tech Stack:** React, TypeScript, TanStack Query v5, MSW, Vite.
- **Future Improvements:** suspense mode examples, devtools walkthrough GIFs.

## 🥉 18. javascript-algorithms

- **Purpose:** Interview-prep credibility + consistent commit activity.
- **Features:** arrays/strings/maps/trees/graphs/DP solutions, each with problem statement, approach notes, complexity analysis, and Jest tests; organized by topic with a progress table in the README.
- **Tech Stack:** JavaScript ES2023, Jest.
- **Future Improvements:** TypeScript variants, LeetCode links index, benchmark comparisons.

## 🥉 19. typescript-practice

- **Purpose:** Proves TS depth beyond annotations — the thing that separates seniors.
- **Features:** generics, conditional & mapped types, template literal types, type-challenges solutions, typed API-client patterns, React+TS patterns (polymorphic components, discriminated-union props).
- **Tech Stack:** TypeScript 5, tsx, Vitest (type-testing via `expectTypeOf`).
- **Future Improvements:** blog-style explanations per topic, tsconfig cookbook.

## 🥉 20. frontend-interview-preparation

- **Purpose:** High-star-potential knowledge repo; shows communication skill.
- **Features:** curated Q&A — JS core (closures, event loop, prototypes), React (reconciliation, hooks rules, performance), TS, CSS layout, browser/networking, plus machine-coding challenges with solutions and a study roadmap.
- **Tech Stack:** Markdown + runnable snippets.
- **Future Improvements:** system-design-for-frontend section, flashcards site, community PRs.

---

## Build order (suggested)

1. **Month 1:** portfolio-v2 polish → react-admin-dashboard → react-hooks-library
2. **Month 2:** react-ecommerce → react-query-examples → typescript-practice
3. **Month 3:** react-chat-app → nextjs-dashboard → remaining repos at 1–2/month

> Quality beats quantity: 6 flagship-grade repos + honest READMEs outperform 20 half-finished ones. Archive or make private anything you won't polish.
