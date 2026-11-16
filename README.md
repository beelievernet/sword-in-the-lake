# Sword in the Lake

A tiny Zelda-style adventure that plays on a phone as an installable PWA.

Live at: https://swordinthelake.beeliever.net (Cloudflare Pages, connected to this repo)

## How deploys work

- This repo is the deploy source. Cloudflare Pages builds/deploys on every
  push to `master` — there is no build step, the files at the repo root are
  the site.
- `index.html` is the whole game (single self-contained file, exported from
  the current demo build).
- Every rebuild that changes the game must bump the cache name in `sw.js`
  (currently `sword-in-the-lake-v1`), or installed copies keep serving the
  previous build.
- Pushes use the per-repo deploy key `github_beelievernet_sword_in_the_lake`
  over ssh.github.com:443, same arrangement as the salvage-bots repo.

Push-to-deploy pipeline test line, 2026-11-16 16:36 EST. If you can read this on the live site, automatic deploys work.
