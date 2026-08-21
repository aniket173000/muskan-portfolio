# Muskan Gupta — Product Portfolio

A single-file, recruiter-ready portfolio website. No build step, no dependencies.
The four interactive prototypes are surfaced everywhere — a "try it" strip in the hero
and a live phone demo inside every case study.

## Files
- `index.html` — the whole site (HTML + CSS + JS inline)
- `Muskan_Gupta_Resume.pdf` — linked from the "Download résumé" buttons
- `assets/` — prototype preview screenshots, `favicon.svg`, `og-cover.png` (link previews)
- `prototypes/` — the interactive prototypes, self-hosted (one folder each)

## Prototypes
Self-hosted in this repo so they ship with the site in a single deploy:
- `prototypes/upi-recall/` — recover a misdirected UPI payment without sharing a phone number
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

### The UPI recall prototype
GitHub disabled `muskangupta2328-bot/phonepe-payment-recall-` on 2026-08-06 under its
Trademark Policy, which killed that Pages site and left Case 01 as a written case study
with no demo.

Muskan rebuilt it at `muskangupta2328-bot/UPI-payment-recall-`. That copy still carried
the old brand name in its title and body copy, so it was exposed to the same takedown.
It now lives here as `prototypes/upi-recall/`, de-branded per above, and Case 01 links
to the local copy — not to GitHub Pages. Don't point Case 01 back at an external host.

The prototype scales itself to fit any viewport (`fitStage()` in its inline script), so
the whole phone is visible on a laptop and on a phone without scrolling. It also accepts
`?screen=<name>` to deep-link a single frame, e.g. `prototypes/upi-recall/?screen=detail` —
that's how `assets/upi-recall.png` was captured.

### Regenerating the preview images
Preview shots are 860×1720 (1:2, matching the `.device` mock) captured at 2× DPR:

```
"/Applications/Google Chrome.app/Contents/MacOS/Google Chrome" \
  --headless=new --disable-gpu --hide-scrollbars \
  --window-size=430,860 --force-device-scale-factor=2 \
  --user-data-dir=/tmp/cap --virtual-time-budget=7000 \
  --screenshot=assets/upi-recall.png \
  "file://$PWD/prototypes/upi-recall/index.html?screen=detail"
```

`assets/og-cover.png` (1200×630, the LinkedIn/WhatsApp link preview) is built the same
way from a throwaway layout file — regenerate it if the prototype shots change.

## Preview locally
Double-click `index.html`, or run a local server:
```
cd muskan-portfolio && python3 -m http.server 8080
# open http://localhost:8080
```

## Publish
The live site is https://muskangupta-pm.netlify.app/ — that URL is printed on the résumé,
so it is the one that has to stay current.

Netlify deploys from the local folder, not from git, so pushing to GitHub does **not**
update the site. From this directory:

```
npx netlify-cli deploy --prod --dir=.
```

Worth doing once: in the Netlify dashboard, link this site to the GitHub repo
(Site configuration → Build & deploy → Link repository). After that a `git push`
publishes on its own and the two can't drift apart.

## Notes
- LinkedIn is wired to the real profile (muskan-gupta-9b29991bb).
- Each of the first three case studies links out to its full Notion write-up. Those pages
  are published to the web (`versed-hedgehog-ded.notion.site/...`). If a write-up is ever
  unpublished the link dies silently — check them when the résumé changes.
- Prototype preview images are static screenshots; the buttons open the *live* demos.
  If you redesign a prototype, re-capture its screenshot (command above).
- `og:image` and `canonical` are absolute URLs pointing at muskangupta-pm.netlify.app.
  If the site moves to a custom domain, update them in the `<head>`.
