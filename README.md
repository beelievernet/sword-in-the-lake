# Little Legend

A tiny Zelda-style adventure that plays on a phone as an installable PWA.

Live at: https://littlelegend.beeliever.net (Cloudflare Pages, connected to this repo)

## How deploys work

- This repo is the deploy source. Cloudflare Pages builds/deploys on every
  push to `master` — there is no build step, the files at the repo root are
  the site.
- `index.html` is the whole game (single self-contained file, exported from
  the current demo build).
- Every rebuild that changes the game must bump the cache name in `sw.js`
  (currently `little-legend-v2`), or installed copies keep serving the
  previous build.
- Pushes use the per-repo deploy key `github_beelievernet_little_legend`
  over ssh.github.com:443, same arrangement as the salvage-bots repo.
