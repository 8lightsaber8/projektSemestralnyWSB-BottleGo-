# BottleGo

BottleGo is a pickup service for deposit bottles and cans (Polish deposit system, _kaucja_). A customer books a pickup, a courier collects the packaging, and the customer gets the deposit back.

## Repository structure

```
.
├── frontend/   # React + TypeScript + Vite
├── backend/    # ASP.NET Core Web API
└── .github/    # CI workflows and pull request template
```

## Tech stack

| Area     | Technologies                            |
| -------- | --------------------------------------- |
| Frontend | React 19, TypeScript, Vite, CSS Modules |
| Quality  | ESLint, Prettier, GitHub Actions        |
| Backend  | ASP.NET Core Web API                    |

## Running the frontend

Requirements: Node.js 24 (pinned in `.nvmrc`).

```bash
nvm use
cd frontend
npm install
npm run dev
```

| Command                | Description                             |
| ---------------------- | --------------------------------------- |
| `npm run dev`          | Start the dev server with hot reload    |
| `npm run build`        | Type-check and build for production     |
| `npm run lint`         | Run ESLint                              |
| `npm run lint:fix`     | Run ESLint and auto-fix issues          |
| `npm run format`       | Format code with Prettier               |
| `npm run format:check` | Check formatting                        |
| `npm run typecheck`    | Run the TypeScript type check only      |

## Frontend architecture

```
src/
├── app/      # App entry point, providers, global styles
├── pages/    # Pages
├── widgets/  # Large page sections (header, footer, landing sections)
├── features/ # User actions (create order, log in)
├── entities/ # Business entities (Order, User)
└── shared/   # Reusable code: UI components, utilities, API client
```

Imports from `src` use the `@/` alias, e.g. `import { HomePage } from '@/pages/home'`.

## Git workflow

- `main` is protected: changes land only through pull requests.
- One pull request per task.

### Branch names

Format: `<area>/<type>-<short-description>`

| Area       | Used for                                 |
| ---------- | ---------------------------------------- |
| `frontend` | Changes in `frontend/`                   |
| `backend`  | Changes in `backend/`                    |
| `infra`    | Repository-wide config, CI, root docs    |

Types: `feat`, `fix`, `refactor`, `chore`, `docs`, `test`.

Examples: `frontend/feat-landing-header`, `backend/fix-jwt-expiration`, `infra/chore-update-ci`.

### Commit messages

[Conventional Commits](https://www.conventionalcommits.org/) with the area as scope:

```
feat(frontend): add landing page header
fix(backend): handle expired JWT tokens
chore(infra): update CI node version
```

## Team

- Danylo Nykytenko — frontend
- <!-- name --> — backend
