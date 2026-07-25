# 🏗️ Enterprise React Folder Structure

A feature-first structure that scales from side project to enterprise app. Use it consistently across all repos — consistency itself is a recruiter signal.

```text
my-app/
├── .github/
│   ├── workflows/              # CI/CD pipelines
│   ├── ISSUE_TEMPLATE/
│   └── PULL_REQUEST_TEMPLATE.md
├── public/                     # Static assets served as-is
├── src/
│   ├── main.tsx                # Entry point — providers only
│   ├── App.tsx                 # Root component — router only
│   │
│   ├── assets/                 # Bundled assets
│   │   ├── images/
│   │   ├── fonts/
│   │   └── icons/
│   │
│   ├── api/                    # HTTP layer (no React here)
│   │   ├── client.ts           # Axios instance + interceptors
│   │   ├── endpoints.ts        # Centralized endpoint constants
│   │   └── services/           # userService.ts, orderService.ts…
│   │
│   ├── components/             # SHARED, reusable, dumb components
│   │   ├── ui/                 # Button, Input, Modal, Card, Spinner
│   │   ├── forms/              # FormField, FormSelect, FormDatePicker
│   │   └── feedback/           # ErrorBoundary, EmptyState, Toast
│   │
│   ├── features/               # ⭐ Feature-sliced business logic
│   │   └── auth/               # Everything auth-related lives together
│   │       ├── components/     #   LoginForm.tsx, OtpInput.tsx
│   │       ├── hooks/          #   useLogin.ts, useSession.ts
│   │       ├── api.ts          #   Feature-scoped API calls
│   │       ├── slice.ts        #   Redux slice (if needed)
│   │       ├── types.ts
│   │       └── index.ts        #   Public API of the feature
│   │
│   ├── layouts/                # App shells
│   │   ├── MainLayout.tsx      # Header + Sidebar + Outlet
│   │   └── AuthLayout.tsx      # Centered card for auth pages
│   │
│   ├── pages/                  # Route-level components (thin!)
│   │   ├── HomePage.tsx        # Compose features, no business logic
│   │   ├── DashboardPage.tsx
│   │   └── NotFoundPage.tsx
│   │
│   ├── routes/
│   │   ├── index.tsx           # createBrowserRouter config
│   │   ├── ProtectedRoute.tsx  # Auth guard
│   │   └── paths.ts            # Route path constants
│   │
│   ├── hooks/                  # SHARED custom hooks
│   │   ├── useDebounce.ts
│   │   ├── useLocalStorage.ts
│   │   └── useMediaQuery.ts
│   │
│   ├── store/                  # Redux Toolkit
│   │   ├── index.ts            # configureStore + typed hooks
│   │   └── slices/             # Cross-cutting slices (ui, theme)
│   │
│   ├── context/                # React Context providers
│   │   └── ThemeContext.tsx
│   │
│   ├── services/               # Non-HTTP external services
│   │   ├── storage.ts          # localStorage wrapper
│   │   └── analytics.ts
│   │
│   ├── utils/                  # Pure functions only (easy to test)
│   │   ├── formatters.ts       # dates, currency, numbers
│   │   └── validators.ts
│   │
│   ├── helpers/                # App-specific helpers (need app context)
│   │   └── errorHandler.ts
│   │
│   ├── constants/
│   │   ├── app.ts              # APP_NAME, PAGE_SIZES…
│   │   └── messages.ts         # User-facing strings
│   │
│   ├── config/
│   │   └── env.ts              # Validated env access (zod-parsed)
│   │
│   ├── styles/
│   │   ├── global.css
│   │   └── theme.ts            # MUI createTheme / Tailwind tokens
│   │
│   ├── types/                  # Shared TS types & interfaces
│   │   ├── api.ts              # ApiResponse<T>, Paginated<T>
│   │   └── models.ts           # User, Product…
│   │
│   └── tests/
│       ├── setup.ts            # Vitest setup, jest-dom
│       ├── test-utils.tsx      # Custom render with providers
│       └── mocks/              # MSW handlers
│
├── .env.example
├── .eslintrc.cjs / eslint.config.js
├── .prettierrc
├── tsconfig.json               # With "@/*" path alias
├── vite.config.ts
└── package.json
```

## The rules that make it work

1. **Features are self-contained.** `features/auth` owns its components, hooks, state, and API calls. Delete the folder, delete the feature.
2. **Import direction is one-way:** `pages → features → shared (components/hooks/utils)`. Features never import from other features — lift shared code down to the shared layer.
3. **Each feature exposes a public API** via `index.ts`; nothing outside imports its internals.
4. **Pages are thin** — they compose features and pass route params. Business logic lives in features.
5. **`utils/` is pure** (input → output, no imports from app code) vs **`helpers/`** which may know about the app. Pure utils get tested first.
6. **Path aliases** (`@/components/...`) via tsconfig `paths` — no `../../../` chains.
7. **Types vs interfaces folders:** in practice keep both in `types/` — `interfaces/` as a separate folder is only worth it in very large codebases; prefer one `types/` folder with domain files.
8. **Colocate tests** (`Component.test.tsx` next to `Component.tsx`) for units; keep `src/tests/` for setup, shared utilities, and MSW mocks.
