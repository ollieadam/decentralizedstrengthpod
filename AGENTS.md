# Decentralized Strength Pod — Agent Context

## Project Overview

The podcast & blog for Decentralized Strength LLC — coaching methods, athletics, and career paths in independent strength & conditioning. Hosted by Adam Oliver, CSCS.

**URL:** https://decentralizedstrengthpod.com (apex canonical, `www` redirected)
**Repo:** `ollieadam/decentralizedstrengthpod` (GitHub Pages, `main/root`)
**Deploy:** push to `main` → auto-deploys via GitHub Pages.

## Domain / DNS
- Cloudflare — must keep `decentralizedstrengthpod.com` **DNS-only** (grey cloud, NOT proxied) or GitHub's SSL can stall:
  - `A @` → `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
  - `www` CNAME → `ollieadam.github.io`
- GitHub Pages settings: custom domain `decentralizedstrengthpod.com`, **HTTPS enforced**.
- GSC token `google7b8121c0c7f5ff2f.html` kept in repo root.

## Structure
- `index.html` — landing page (hero, about, episodes, host, blog, subscribe; podcast mark)
- `blog/` — journal posts (`robust-aging.html`, `pro-level-results-from-a-park.html`)
- `logo.png` — podcast mark (500×500, unchanged brand)
- `logo-cover.png` — social og:image (1200×630, **mark-only**)
- `CNAME` → `decentralizedstrengthpod.com`, `sitemap.xml`, `README.md`

## Brand rules
- Domain string is **`decentralizedstrengthpod.com`** (NOT `decentralizedpod.com`). Grep before shipping.
- The pod site keeps its own podcast logo; the **Decentralized Strength LLC** landing lives separately at `decentralizedstrength.com` with its own evolved-hexagon mark.
- Both DS sites' `/blog/*` URLs are meta-refresh redirect stubs → `decentralizedstrengthpod.com/blog/<same>`.

## Hosting model (all DS sites)
| Site | Repo | Deploy |
|------|------|--------|
| `strengthclubai.com` | `ollieadam/strengthclubai` | Cloudflare tunnel → localhost:8082 |
| `chsstrengthclub.com` | `ollieadam/chsstrengthclub` | GitHub Pages |
| `decentralizedstrength.com` | `ollieadam/decentralizedstrength` | GitHub Pages (LLC links landing) |
| `decentralizedstrengthpod.com` | `ollieadam/decentralizedstrengthpod` | GitHub Pages (**this repo**) |