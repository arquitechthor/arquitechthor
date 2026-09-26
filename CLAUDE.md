# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

Personal "about me" site of Héctor Guzmán (arquitechthor), served by GitHub Pages as a
**project site** at `https://arquitechthor.github.io/arquitechthor/` (repo
`arquitechthor/arquitechthor`, published from `main`, root folder — every push redeploys). Plain
HTML/CSS, no build step, no dependencies. `.nojekyll` disables Jekyll, so `index.html` is served
as-is instead of the README being rendered.

This repo is also the **GitHub profile repo** (same name as the account): `README.md` is what
github.com/arquitechthor shows on the profile page. It is in English and is *not* part of the
site — keep it, and keep its link pointing to the site URL above. `LICENSE` (GPL-3.0) predates
the site.

Absolute URLs in `index.html` (canonical, `og:*`, JSON-LD) must include the `/arquitechthor/`
path. The account has no user site (`arquitechthor.github.io` root is a 404); `aws-cert-study`
is a sibling project site at `https://arquitechthor.github.io/aws-cert-study/`.

```
index.html          # single page: #top (Sobre mí hero) → #kopi → #apuntes-aws → #certificaciones
styles.css          # same palette/tokens as kopi-web and aws-cert-study (copied, not shared)
assets/
  arquitechthor.jpg      # profile photo (also the source of the favicons)
  kopi-mascot.jpg        # 560px downscale of kopi-web/assets/kopi-mascot.png
  insignias/*.png        # Credly badge images, downscaled to 240px
  nav.js                 # mobile menu toggle
```

## Relationship with the other sites

- This page replaced the old `#sobre-mi` section of `kopi-web`. Both `kopi-web` and
  `aws-cert-study` link their "Sobre mí" entries here.
- Kopi's Conocimiento section stays in `kopi-web` (it needs the Kopi backend/DB).

## Certificaciones

Hardcoded from the public Credly profile
(`https://www.credly.com/users/hector-guzman.61ef69dd`). Only **currently valid** badges are
shown (expired ones — e.g. the 2020 Scrum Foundation / Lifelong Learning — are omitted). To
refresh: `curl -s -H "Accept: application/json" "https://www.credly.com/users/hector-guzman.61ef69dd/badges.json"`
lists every badge with `issued_at_date`, `expires_at_date`, template name/image and badge `id`
(public link: `https://www.credly.com/badges/<id>/public_url`). Keep the JSON-LD
`hasCredential` list in `<head>` in sync with the certifications (not the plain badges).

## UI language

All user-facing text is in **Spanish**.
