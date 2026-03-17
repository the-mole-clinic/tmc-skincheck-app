# TMC Skin Check App

Free skin health check tool for [The Mole Clinic](https://themoleclinic.co.uk) — a private UK dermatology clinic chain. The app guides users through a personalised skin cancer risk assessment, captures photos, and recommends the appropriate clinic service and nearest location.

This is a patient acquisition and lead generation tool. It is **not a diagnostic tool** — it profiles risk and drives professional bookings.

**Live:** https://the-mole-clinic.github.io/tmc-skincheck-app/
**Trello:** https://trello.com/c/iWUhQpVC

---

## App Flow

1. Welcome — social proof, urgency
2. Email / name / postcode capture
3. GDPR consent
4. Skin tone picker (Monk Skin Tone Scale, 10 tones)
5. Risk profile questionnaire (11 weighted questions)
6. Photo capture — guided full-body flow (6 steps) or specific areas via interactive body map
7. ABCDE self-check education
8. Loading / processing
9. Results — animated risk gauge, risk factors, service recommendation, nearest clinics, sticky booking CTA

---

## Running Locally

No build step required. Just open `index.html` in a browser:

```bash
git clone https://github.com/the-mole-clinic/tmc-skincheck-app.git
cd tmc-skincheck-app
open index.html        # macOS
start index.html       # Windows
```

Or drag `index.html` into any browser window.

---

## Tech Stack

| | |
|---|---|
| Structure | Single `index.html` — inline CSS and JS |
| Frameworks | None |
| Fonts | DM Sans + Fraunces (Google Fonts CDN) |
| Photos | Stored client-side as base64 (no backend) |
| Hosting | GitHub Pages — auto-deploys from `main` |
| PWA | `manifest.json` in root |

Supports iOS Safari, Android Chrome, and desktop browsers. Mobile-first, max-width 480px.

---

## Deployment

Push to `main` — GitHub Pages deploys automatically within ~2 minutes.

```bash
git add .
git commit -m "[feat] Description"
git push
```
