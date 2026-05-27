## Setup

1. `pnpm install`
2. Copy `.env.local.example` to `.env.local`
3. Create a [Supabase](https://supabase.com) project and a storage bucket
4. Fill in `SUPABASE_URL`, `SUPABASE_SERVICE_ROLE_KEY`, and `SUPABASE_BUCKET` in `.env.local`
5. Set `USE_LOCAL_BLOB=true` in `.env.local` for local development

For production, remove `USE_LOCAL_BLOB` and ensure the Supabase env vars are set in your Vercel project settings.
