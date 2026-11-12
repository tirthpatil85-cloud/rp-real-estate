# RP Real Estate

A polished single-page business website for RP Real Estate, an industrial real estate agency serving buyers and investors around Hathijan, Ahmedabad.

## Run & Operate

- `pnpm --filter @workspace/api-server run dev` — run the API server (port 5000)
- `pnpm run typecheck` — full typecheck across all packages
- `pnpm run build` — typecheck + build all packages
- `pnpm --filter @workspace/api-spec run codegen` — regenerate API hooks and Zod schemas from the OpenAPI spec
- `pnpm --filter @workspace/db run push` — push DB schema changes (dev only)
- Required env: `DATABASE_URL` — Postgres connection string

## Stack

- pnpm workspaces, Node.js 24, TypeScript 5.9
- API: Express 5
- DB: PostgreSQL + Drizzle ORM
- Validation: Zod (`zod/v4`), `drizzle-zod`
- API codegen: Orval (from OpenAPI spec)
- Build: esbuild (CJS bundle)

## Where things live

- `artifacts/rp-real-estate/src/App.tsx` — single-page marketing site, contact interactions, and inquiry form
- `artifacts/rp-real-estate/src/index.css` — RP Real Estate visual system, responsive styles, motion, and utility classes
- `artifacts/rp-real-estate/public/assets/` — supplied logo, team photography, campaign creatives, and videos
- `artifacts/rp-real-estate/.replit-artifact/artifact.toml` — artifact metadata and managed web workflow

## Architecture decisions

- Presentation-first single-page site; no backend or database is needed for the current marketing and inquiry experience.
- Contact actions use direct phone, WhatsApp, email, website, and Google Maps links so the business can receive leads without an additional service.
- Current business phone and WhatsApp contact: +91 97141 14913.
- The inquiry form is intentionally browser-only with a clear success state; it does not imply that a lead was persisted remotely.

## Product

- Introduces RP Real Estate and its local Ahmedabad focus
- Explains plot, future-development, documentation, and home-loan guidance
- Highlights nearby service areas and customer reviews
- Shows the supplied Gujarat RERA registration certificate
- Includes home-loan/DSA assistance and named lender options
- Uses the supplied brand assets to establish trust and local presence
- Offers direct contact CTAs and a lightweight inquiry flow

## User preferences

No durable preferences recorded.

## Gotchas

- The Vite config requires `PORT` and `BASE_PATH` when running build commands outside the managed workflow.
- Keep supplied asset filenames URL-safe when referencing them from the public assets directory.

## Pointers

- See the `pnpm-workspace` skill for workspace structure, TypeScript setup, and package details
