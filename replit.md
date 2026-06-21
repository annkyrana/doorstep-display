# Workspace

## Overview

pnpm workspace monorepo using TypeScript. Each package manages its own dependencies.

## Stack

- **Monorepo tool**: pnpm workspaces
- **Node.js version**: 24
- **Package manager**: pnpm
- **TypeScript version**: 5.9
- **API framework**: Express 5
- **Database**: PostgreSQL + Drizzle ORM
- **Validation**: Zod (`zod/v4`), `drizzle-zod`
- **API codegen**: Orval (from OpenAPI spec)
- **Build**: esbuild (CJS bundle)

## Key Commands

- `pnpm run typecheck` — full typecheck across all packages
- `pnpm run build` — typecheck + build all packages
- `pnpm --filter @workspace/api-spec run codegen` — regenerate API hooks and Zod schemas from OpenAPI spec
- `pnpm --filter @workspace/db run push` — push DB schema changes (dev only)
- `pnpm --filter @workspace/api-server run dev` — run API server locally

See the `pnpm-workspace` skill for workspace structure, TypeScript setup, and package details.

## iFixiCare App

A complete service booking web app for mobile and laptop repair services at your doorstep.

### Frontend (`artifacts/ifixicare`)
- React + Vite app at `/` preview path
- Pages: Home (`/`), Booking (`/book`)
- Blue and white theme, mobile + desktop responsive
- WhatsApp integration with auto-fill: +91 9667669299
- Floating WhatsApp button on all pages

### Backend (`artifacts/api-server`)
- Express 5 + PostgreSQL/Drizzle
- Booking endpoints: POST/GET `/api/bookings`, GET `/api/bookings/stats`

### Database Schema (`lib/db/src/schema/bookings.ts`)
- `bookings` table: id, name, phone, service, problem, address, status, created_at

### Services
- All 4 service types: Mobile Repair, Laptop Repair, Screen Replacement, Battery Replacement
