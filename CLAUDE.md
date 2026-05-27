This is an MVP. The goal is to find out whether the core experience is worth building before investing in the infrastructure around it.

## Philosophy

**Cake, not the bakery.** The goal is to find out if the core experience is worth building. Things like admin interfaces, polished UI, and robust error handling belong to the bakery — don't build them until the cake is proven.

**Seeds, not admin UI.** Interfaces for inputting bootstrap data belong to the bakery. Use a seed script instead.

**No authentication.** Don't get caught building login flows, roles, or permissions for a product that isn't proven yet.

**Emergent schema.** The data model grows from usage. JSON files are easy to reason about and let structure appear naturally.

**Pessimistic updates.** State never changes until the server confirms. Always show a loading indicator while waiting and disable controls until the request resolves.

## Stack

- **Frontend**: Next.js (App Router)
- **Storage**: Local filesystem (dev) / Supabase Storage (prod)
- **Hosting**: Vercel
- **Package manager**: pnpm

## Storage

All storage goes through `lib/blob` — never access the filesystem or Supabase directly elsewhere in the codebase.

All blob pathnames are defined in `lib/paths.ts`. Never hardcode a path inline.

Set `USE_LOCAL_BLOB=true` in `.env.local` for local development. In production, provide `SUPABASE_URL`, `SUPABASE_SERVICE_ROLE_KEY`, and `SUPABASE_BUCKET`.

## Tools

A set of reusable hooks and utilities live in `hooks/` and `lib/`. Use them before writing new ones.
