# Muskan Gupta — Product Portfolio

A single-file, recruiter-ready portfolio website. No build step, no dependencies.
The four interactive prototypes are surfaced everywhere — a "try it" strip in the hero
and a live phone demo inside every case study.

## Files
- `index.html` — the whole site (HTML + CSS + JS inline)
- `Muskan_Gupta_Resume.pdf` — linked from the "Download résumé" buttons
- `assets/` — prototype preview screenshots (phonepe, cred, splitwise, zomato)
- `prototypes/` — the interactive prototypes, self-hosted (one folder each)

## Prototypes
Self-hosted in this repo so they ship with the site in a single deploy:
- `prototypes/card-bill-split/` — auto-split a big card spend, settle the bill as money arrives
- `prototypes/group-settle/` — sync group expenses and settle up over UPI
- Zomato Mood-Pulse lives in Figma — https://www.figma.com/make/beCQhD7rH56MnWNqXy4J2u/Mood-Pulse-Widget-Placement

They used to live in separate `muskangupta2328-bot` repos on GitHub Pages. They were
moved here after one of them was taken down (below) — one repo, one deploy, no
dependency on an account this project can't push to.

### De-branding
Every prototype is a concept, so none of them carry another company's name, wordmark
or brand colour, and each shows a fixed "concept prototype / not affiliated" line.
The case-study copy in `index.html` still names the real apps — that's ordinary
referential use and is fine. **Keep it that way when editing a prototype.**

### Offline: PhonePe UPI Recall
GitHub disabled `muskangupta2328-bot/phonepe-payment-recall-` on 2026-08-06 under its
Trademark Policy, which killed the Pages site with it. Case 01 now renders as a
case study only — no launch button, static phone mock, `Case study` chip.
The source was not recoverable (raw, codeload and the Wayback Machine all came back
empty), so restoring it needs a local copy from Muskan.
To restore: drop it in as `prototypes/upi-recall/`, de-branded per above, then re-add
the link in three places in `index.html` — the hero strip thumb (remove the `read`
class), the case CTA, and the phone mock (remove `static`).

## Preview locally
Double-click `index.html`, or run a local server:
```
cd muskan-portfolio && python3 -m http.server 8080
# open http://localhost:8080
```

## Publish for free (get a shareable link)
**Netlify (fastest)** — app.netlify.com → "Add new site" → "Deploy manually" → drag the
`muskan-portfolio` folder in. Instant live URL.

**GitHub Pages** — create a public repo, upload the folder, Settings → Pages →
Deploy from branch → `main` / root.

## Notes
- LinkedIn is wired to the real profile (muskan-gupta-9b29991bb).
- Prototype preview images are static screenshots; the buttons open the *live* demos.
  If you redesign a prototype, re-capture its screenshot into `assets/` to keep them fresh.
- Netlify deploys from the local folder, not from git — pushing to GitHub does **not**
  update the site. Run `netlify deploy --prod --dir=.` from this directory.
