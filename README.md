# BlendedFox

Public website for [blendedfox.com](https://blendedfox.com), a boutique web and software studio. BlendedFox is a DBA of Circle Up Stories.

The site is static HTML, CSS, and a small amount of JavaScript, served by a [Cloudflare Worker](https://developers.cloudflare.com/workers/static-assets/) with static assets.

## Local preview

```bash
npm install
npm run dev
```

Wrangler prints a `localhost` URL. Open it to review the site.

## Deploy to Cloudflare

1. Log in once: `npx wrangler login`
2. Deploy: `npm run deploy`
3. In the Cloudflare dashboard, attach the custom domain `blendedfox.com` to the `blendedfox` Worker.

Until the custom domain is attached, Cloudflare will serve the Worker on a `*.workers.dev` URL.

You can also connect this GitHub repo in the Cloudflare dashboard so pushes to `main` deploy the Worker automatically.

## What’s here

- `public/` — the site (home page, 404, styles, logo)
- `src/worker.ts` — Worker that serves those assets and adds security headers
- `wrangler.jsonc` — Cloudflare project config
