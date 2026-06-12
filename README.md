# Taking a Mary Break

Production-ready React/Vite website for the **Taking a Mary Break** podcast brand, including pages for episodes, playlists, events, blog updates, social links, and the Quincy & Coco section.

## Stack

- React 19
- Vite 7
- Tailwind CSS 4
- Express 4
- tRPC 11
- Drizzle ORM
- MySQL/TiDB optional backend
- Vercel-ready serverless API entrypoints

## Local setup

```bash
pnpm install
pnpm dev
```

Open the local URL shown in the terminal, usually `http://localhost:3000`.

## Build and checks

```bash
pnpm check
pnpm test
pnpm build
pnpm start
```

This project supports local development without a database. If `DATABASE_URL` is missing, newsletter submissions, comments, events, and blog content use safe in-memory/fallback data so the site can still run and be tested.

## Production database

Copy `.env.example` to `.env` and set `DATABASE_URL` for persistent newsletter subscribers, blog posts, events, and comments.

```bash
cp .env.example .env
pnpm db:push
pnpm seed
```

## Vercel deployment

The repo includes `vercel.json` plus serverless API entrypoints under `api/`.

Recommended Vercel settings:

- Install command: `pnpm install`
- Build command: `pnpm build`
- Output directory: `dist/public`

Set production environment variables in Vercel before enabling persistent data.

## Notes

Some images still reference `/manus-storage/...`. Those paths work on the original Manus deployment. For a fully independent Vercel/GitHub deployment, move the image files into `client/public/assets/` or host them on a stable CDN, then update the image URLs.

## Push status

The connected GitHub tool did not expose a direct `create repository from local folder` or `git push directory` action, so this repository was initialized and documented from the connector. The fully cleaned source package was generated locally as `taking-a-mary-break-github-ready.zip` for manual upload/import if needed.
