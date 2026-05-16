# Neil's Magic Carpets

Premium website for Neil's Magic Carpets — expert carpet fitting and luxury vinyl flooring across London and the South East. Editorial redesign built from scratch.

## Tech stack

- Vite + React + TypeScript
- Tailwind CSS + Framer Motion
- Supabase (contact form, planned edge functions)
- Deployed on Vercel
- npm for package management

## Operating procedure

This repo follows the website project SOP in `docs/operating-procedure.md`, mirrored from the shared SOP at `https://github.com/charishynds/website-standards`.

Use GitHub Flow:

1. Create a branch from `main`.
2. Work locally and preview the site.
3. Run approved local checks.
4. Open a pull request and review the Vercel Preview Deployment.
5. Merge to `main` for production deployment.

Keep project tasks, launch checks, and owner actions in `docs/repo-admin-checklist.md`.

## Development

```sh
npm install
npm run dev -- --host 0.0.0.0 --port 5173
```

Preview locally at `http://localhost:5173/`.

## Build

```sh
npm run build
```

## Checks

```sh
npm run lint
npm run build
npm run typecheck
```

Run `npm audit --omit=dev` only after approval because it uses the npm registry.

## Environment variables

Copy `.env.example` to a local `.env` file and fill in the values.

Frontend:

- `VITE_SUPABASE_URL`
- `VITE_SUPABASE_PUBLISHABLE_KEY`

Supabase Edge Functions (when deployed):

- `WHATSAPP_PHONE_NUMBER_ID`
- `WHATSAPP_API_TOKEN`
- `WHATSAPP_RECIPIENT_PHONE`
- `GOOGLE_PLACES_API_KEY`
- `GOOGLE_PLACE_ID`

Never commit real secrets. Store preview and production values in Vercel and Supabase as appropriate.

## Supabase

The contact form writes leads to Supabase. Edge functions for WhatsApp notification and Google rating are planned but not yet deployed.

Confirm the Supabase project, RLS policies, table permissions, constraints, and edge function secrets before launch. See `docs/repo-admin-checklist.md`.

## Deployment

Vercel should create Preview Deployments for branches and pull requests. Production should deploy from merges to `main`.

Do not use Vercel "Promote to Production" as the normal release path.

Production domain: `https://www.neilsmagiccarpets.co.uk/`.
