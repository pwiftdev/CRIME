# $CRIME

Landing page for **$CRIME**, a memecoin on Solana launched on pump.fun. Holders get paid in $XMR.

Contract: `BN4Z5NtntHhu6p3atEqkeAVi8Bn9Ri2QTv8FD7iupump`

Plain static site: one `index.html`, a `media/` folder, no build step.

## Deploy on Vercel

1. Push this folder to a GitHub repo (the folder contents go at the repo root).
2. In Vercel: **Add New → Project → Import** the repo.
3. Framework preset: **Other**. Leave Build Command and Output Directory empty. Deploy.

Every push to `main` redeploys automatically.

## After the first deploy

- **Link previews:** in `index.html`, replace both `SITE_URL` placeholders with the live domain (for example `https://crime.vercel.app`), so X and Telegram show `og.jpg` when the link is shared.
- **Socials:** near the bottom of `index.html`, fill in `SOCIALS = { "X": "", "Telegram": "" }`. Empty entries stay hidden.
- **Contract address:** set once in `const CA = "..."`. Every button and copy field uses it.

## Edit points in `index.html`

| What | Where |
| --- | --- |
| Contract address | `const CA = ...` |
| X / Telegram links | `const SOCIALS = ...` |
| Meme captions | `const MEMES = [...]` (image, top text, bottom text) |
| Accent colour | `--amber` in the `:root` block |

## Files

```
index.html          the page
og.jpg              1200×630 link preview
apple-touch-icon.png
vercel.json         caching + security headers
media/
  crime-hero.webm   hero animation (VP9)
  crime-hero.mp4    hero animation (H.264 fallback)
  hero-poster.jpg   first frame, shown before the video loads
  hero-final.jpg    final frame (finale background, reduced-motion poster)
  icon.png          favicon
  coin_crime.png    3D coin face, $CRIME side
  coin_xmr.png      3D coin face, XMR side
  memes/m01–m24.jpg meme wall images
```

Three.js r128 and Google Fonts load from public CDNs.
