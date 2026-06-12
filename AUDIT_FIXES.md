# Audit and production fixes

This project was cleaned after export from Manus and prepared for GitHub/Vercel ownership.

## Fixed

- Added missing route aliases for `/episodes`, `/connect`, `/behind-the-scenes`, and `/quincy-and-coco`.
- Fixed external YouTube Subscribe links so they open outside the SPA router.
- Fixed comment lookup to respect `postId`.
- Fixed event and blog ordering queries.
- Rebuilt `seed-data.mjs` to match the Drizzle schema.
- Added missing `users` table to the first SQL migration.
- Added no-database fallback behavior so local tests and public pages do not fail when `DATABASE_URL` is not configured.
- Added Vercel serverless entrypoints for tRPC and OAuth callback routes.
- Simplified Vite config by removing Manus-only debug/runtime plugins.
- Removed Manus debug collector from public assets.
- Replaced the generic Manus template README with a project-specific production README.
- Removed the stale exported pnpm lockfile because package cleanup changed dependencies and this sandbox could not regenerate it without registry access.

## Still required for full independence

- Replace `/manus-storage/...` image references with files stored in `client/public/assets/` or a stable CDN.
- Add real production database credentials in Vercel if newsletter/blog/events/comments should persist.
- Verify final deployment with `pnpm install`, `pnpm check`, `pnpm test`, and `pnpm build` in an environment with npm registry access.
