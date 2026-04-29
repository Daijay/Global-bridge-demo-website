# Workspace

## Overview

Tutoring non-profit website built as a pnpm workspace monorepo. Frontend (React + Vite) at `/`, shared API server at `/api`, PostgreSQL via Drizzle.

## Stack

- **Monorepo tool**: pnpm workspaces
- **Node.js version**: 24
- **Package manager**: pnpm
- **TypeScript version**: 5.9
- **Frontend**: React + Vite, Tailwind, shadcn/ui, wouter, react-hook-form, framer-motion, react-helmet-async
- **API framework**: Express 5
- **Database**: PostgreSQL + Drizzle ORM
- **Validation**: Zod (`zod/v4`), `drizzle-zod`
- **API codegen**: Orval (from OpenAPI spec)

## Artifacts

- `artifacts/web` (`/`) — public website for the tutoring non-profit
- `artifacts/api-server` (`/api`) — shared Express API
- `artifacts/mockup-sandbox` — design canvas

## Domain model

- `programs` — four core programs: english, mathematics, science, public-speaking
- `team_members` — executives, tutors, volunteers (filterable by category)
- `achievements` — milestone timeline
- `impact_stats` — singleton row with public counters
- `tutor_applications`, `student_applications` — application form submissions
- `partnership_inquiries`, `contact_messages`, `donation_intents` — other form submissions

## Key Commands

- `pnpm run typecheck` — full typecheck across all packages
- `pnpm run build` — typecheck + build all packages
- `pnpm --filter @workspace/api-spec run codegen` — regenerate API hooks and Zod schemas from OpenAPI spec
- `pnpm --filter @workspace/db run push` — push DB schema changes (dev only)
- `pnpm --filter @workspace/scripts run seed` — seed programs, team, achievements, and impact stats
- `pnpm --filter @workspace/api-server run dev` — run API server locally

See the `pnpm-workspace` skill for workspace structure, TypeScript setup, and package details.
