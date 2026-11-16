# gustavgelfort.com

Personal site of Gustav Gelfort. This repository is also his GitHub profile repo, so `README.md` is what GitHub shows on the profile page: leave it alone unless asked.

## Layout

- `site/index.html`: the whole site, one self-contained file (HTML, CSS and JS inline, only Google Fonts loaded from outside).
- `site/og.png`: 1200×630 preview image shown when the link is shared on LinkedIn, Instagram, WhatsApp, iMessage. It still shows an older design and should be regenerated from the current page.
- Future posts go in `site/posts/<slug>/index.html`, one page per post, each with its own `og:` tags so it can be shared on its own.

## Deployment

- Domain `gustavgelfort.com` is registered at Cloudflare (Gustav's account) and uses Cloudflare DNS.
- Hosting is meant to be Cloudflare Pages connected to this repo: production branch `main`, no build command, output directory `site`, custom domains `gustavgelfort.com` and `www.gustavgelfort.com`. Every push to `main` goes live; other branches get preview URLs.
- Preview locally with `python3 -m http.server 8080` from `site/`.

## Design language

- Editorial layout inspired by yannickhofmeister.com: narrow 720px column, serif type (Newsreader), small uppercase Inter labels, thin rules, cool off-white background.
- Colours (McKinsey-style blues, but no McKinsey logos or assets): navy `#051c2c` (text, dark-mode background), electric blue `#2251ff`, cyan `#00a9f4`, light background `#f6f7f8`.
- Visual vocabulary is fine 1px lines only: a twisting ribbon of parallel lines flowing across the page (`#ribbon`), contour rings like elevation lines (`#rings`), and small generated pattern tiles (rings, waves, warped grid) for themes and posts. New visuals should reuse this vocabulary.
- Copy is very short. Only say things Gustav can say publicly; don't name his employer or role unless he asks. Don't reuse Yannick's wording (his headline starts "The space between…").
- Light and dark mode both supported (toggle stored in `localStorage`), plus `prefers-reduced-motion`.
- Safari quirk: gradient text (`background-clip: text`) is clipped to each letter's box, so the italic surname letters carry extra padding with matching negative margins. Keep that when changing the heading.

## Open items

- Confirm LinkedIn URL (currently a guess: `linkedin.com/in/gustavgelfort`) and email (currently `gustavgelfort@icloud.com`, read from a truncated screenshot).
- Check in Safari that the tail of the italic "f" in "Gelfort" is no longer cut off; if it still is, make the surname a solid blue instead of a gradient.
- On phones the ribbon crosses the intro paragraph and hurts legibility.
- Regenerate `site/og.png` from the current design.
- Connect Cloudflare Pages (see Deployment).
- Email: planned as iCloud+ Custom Email Domain on `gustavgelfort.com` (DNS records added in Cloudflare). Cloudflare Email Routing is not used because it conflicts with iCloud's MX records.
- `gelfort.net` (bought by Gustav's mother) should be transferred to Gustav's Cloudflare account later and redirected or used for family addresses.
