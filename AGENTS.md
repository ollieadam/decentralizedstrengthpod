# Decentralized Strength Pod — Agent Context

## Project Overview

The podcast site for Decentralized Strength LLC — show, episodes, and subscribe only. Hosted by Adam Oliver, CSCS. Essays and philosophy live on the parent site.

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
- `index.html` — show landing (hero, about, episodes, host, subscribe; podcast mark). Outbound links to `decentralizedstrength.com` for essays/philosophy.
- `blog/` — noindex meta-refresh stubs to matching parent essay URLs (not the journal itself)
- `logo.png` — podcast mark (500×500, unchanged brand)
- `logo-cover.png` — social og:image (1200×630, **mark-only**)
- `CNAME` → `decentralizedstrengthpod.com`, `sitemap.xml` (homepage only), `README.md`

## Brand rules
- Domain string is **`decentralizedstrengthpod.com`** (NOT `decentralizedpod.com`). Grep before shipping.
- The pod site keeps its own podcast logo; the **Decentralized Strength LLC** landing lives separately at `decentralizedstrength.com` with its own evolved-hexagon mark.
- Palette when touching CSS: warm cream `~#f7f4ef` / ink `#000` / greys. **No red.** Keep this a show site, not a second holdings portal.
- Reading lives on `decentralizedstrength.com`. Do not re-host journal posts here.

## Essay redirects (pod → parent)
| Source | Destination |
|---|---|
| `/blog/` | https://decentralizedstrength.com/ (hub lists essays; delayed refresh) |
| `/blog/the-4-ps.html` | https://decentralizedstrength.com/blog/the-4-ps.html |
| `/blog/robust-aging.html` | https://decentralizedstrength.com/blog/robust-aging.html |
| `/blog/pro-level-results-from-a-park.html` | https://decentralizedstrength.com/blog/pro-level-results-from-a-park.html |

GitHub Pages cannot emit HTTP 301; stubs use meta refresh + canonical + `noindex`.

## Hosting model (all DS sites)
| Site | Repo | Deploy |
|------|------|--------|
| `strengthclubai.com` | `ollieadam/strengthclubai` | Cloudflare tunnel → localhost:8082 |
| `chsstrengthclub.com` | `ollieadam/chsstrengthclub` | GitHub Pages |
| `decentralizedstrength.com` | `ollieadam/decentralizedstrength` | GitHub Pages (LLC links landing + journal) |
| `decentralizedstrengthpod.com` | `ollieadam/decentralizedstrengthpod` | GitHub Pages (**this repo**) |
