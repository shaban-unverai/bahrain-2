# Bahrain Real Estate GPT

A Next.js App Router MVP for exploring Bahrain property demo listings, comparing properties, and testing investment assumptions.

## Important data notice

The included listings, rent estimates, market chart values, dashboard metrics, and sample accounts are simulated demonstration data. They are not verified live listings, official market statistics, or financial forecasts. No live Aqari/RERA, property portal, mapping, CRM, authentication, or database connection is configured.

## Requirements

- Node.js 20.9 or later (use a supported Node.js LTS release)
- npm 10 or compatible

## Local setup

```bash
npm ci
cp .env.example .env.local
npm run dev
```

Open http://localhost:3000.

The demo application works without an OpenAI key or database. `.env.local` is optional for demo mode.

## Validation

```bash
npm run typecheck
npm run lint
npm run build
npm run start
```

`npm run start` runs the production server after a successful build. Keep the development server and production server on separate terminals/ports if testing both.

## Optional live AI

The assistant currently uses deterministic local search and calculation responses. The OpenAI SDK is included for a future server-side integration, but a live model route is not enabled in this MVP. Do not set an API key expecting live responses until that route has been implemented and tested.

## GitHub and Vercel

1. Create a Git repository and commit the source files.
2. Push the repository to GitHub.
3. In Vercel, import the correct GitHub repository.
4. Set **Root Directory** to the directory containing this `package.json` and the `app/` folder.
5. Select the Next.js framework preset if it is not detected automatically.
6. No environment variables are required for demo mode.
7. Deploy and inspect the complete build logs if a deployment fails.

Use the same Node.js major version locally and on Vercel when possible. Do not add a custom `vercel.json` unless a specific requirement calls for one.

## Scripts

- `npm run dev` — local development
- `npm run build` — production build
- `npm run start` — production server
- `npm run lint` — ESLint
- `npm run typecheck` — TypeScript validation

## Routes

- `/` — landing page
- `/properties` — searchable sample listings
- `/properties/[id]` — listing detail
- `/compare` — compare sample properties
- `/investments` — yield, net yield, cash-flow, and mortgage calculator
- `/assistant` — deterministic demo assistant
- `/market` — simulated market charts
- `/dashboard` — user dashboard preview
- `/agency` — agency workspace preview
- `/developer` — developer inventory preview
- `/admin` — admin UI preview (not secured)

## Production limitations

Before real public use, implement and test authentication, server-side authorization, persistent storage, data-provider licensing, privacy controls, rate limiting, production AI routes, real source attribution, real viewing-request delivery, and security review. The `/admin`, `/agency`, `/developer`, and `/dashboard` pages are previews, not secure multi-user systems.
