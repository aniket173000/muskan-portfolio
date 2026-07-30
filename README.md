# Muskan Gupta — Product Portfolio

A single-file, recruiter-ready portfolio website. No build step, no dependencies.
The four interactive prototypes are surfaced everywhere — a "try it" strip in the hero
and a live phone demo inside every case study.

## Files
- `index.html` — the whole site (HTML + CSS + JS inline)
- `Muskan_Gupta_Resume.pdf` — linked from the "Download résumé" buttons
- `assets/` — prototype preview screenshots (phonepe, cred, splitwise, zomato)

## Live prototypes (already wired in)
- PhonePe UPI Recall — https://muskangupta2328-bot.github.io/phonepe-payment-recall-/
- CRED Social Sync — https://muskangupta2328-bot.github.io/CRED-Auto-Split-Engine-/
- Splitwise Smart-Sync — https://muskangupta2328-bot.github.io/Splitwise-Smart-Sync-Settlement-/
- Zomato Mood-Pulse (Figma) — https://www.figma.com/make/beCQhD7rH56MnWNqXy4J2u/Mood-Pulse-Widget-Placement

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
