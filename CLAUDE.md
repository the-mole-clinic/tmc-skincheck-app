# TMC Skin Check App — Project Instructions for Claude Code

## Project Overview
Free skin health check PWA for The Mole Clinic (TMC), a private UK dermatology clinic chain. This app is a patient acquisition and lead generation tool — it captures emails, builds risk profiles, and drives clinic bookings. It is NOT a diagnostic tool.

- **Repo:** https://github.com/the-mole-clinic/tmc-skincheck-app
- **Live URL:** https://the-mole-clinic.github.io/tmc-skincheck-app/
- **Trello Card:** https://trello.com/c/iWUhQpVC
- **Hosting:** GitHub Pages (static, auto-deploys from main branch)

## Technical Architecture (current — POC phase)
- Single `index.html` file with inline CSS and JS
- No frameworks, no build tools, no external JS libraries
- Google Fonts CDN: DM Sans (body) + Fraunces (display)
- Photos stored client-side as base64 (no backend)
- PWA manifest.json in root directory
- Must work on iOS Safari, Android Chrome, and desktop browsers
- Mobile-first design, max-width 480px centred layout

## Brand & Design
- **Colours:** navy #1a2332, teal #2ec4b6, coral #e07a5f, gold #f2cc8f, cream #faf8f5
- **Fonts:** DM Sans (body), Fraunces (display headings)
- **Tone:** Professional, warm, reassuring, never alarming. British English spelling throughout.
- **Feel:** Premium private healthcare, not tech startup

## Clinic Locations (for postcode matching)
| Clinic | Postcodes |
|--------|-----------|
| London Marylebone | W1, NW, WC (and default fallback) |
| London City | EC, E1, E2 |
| London Chelsea | SW, KT, TW |
| London Canary Wharf | E (other East London) |
| Manchester | M, WA, SK, OL, BL, WN |
| Leeds | LS, BD, HG, WF, HX, HD |
| Bristol | BS, BA, GL, SN |
| Birmingham | B (not BS/BD/BL/BN), WS, DY, WV, CV |

## Service Tiers
| Risk Level | Service | Price |
|-----------|---------|-------|
| HIGH / changing moles (multiple) | Full Body Mole Check | from £250 |
| MODERATE / changing moles (one) | Targeted Mole Check | from £150 |
| LOW | Skin Health Screen | from £100 |

## Critical Rules
1. **NEVER use diagnostic language** — no "you may have cancer", "this looks suspicious", "malignant", "benign". This app profiles risk and recommends professional assessment. Diagnosis is for clinicians only.
2. **NEVER add AI image analysis** — no mole scanning, no photo-based diagnosis, no skin condition detection.
3. **Conversion is the priority** — every screen should move the user toward either giving us their email or booking an appointment.
4. **GDPR compliance** — data processing consent is mandatory before any data collection. Marketing consent is optional.
5. **Accessibility** — touch targets minimum 44x44px, all images need alt text, sufficient colour contrast.

## Git Workflow
- Work on `main` branch (POC phase — we'll add branching for MVP)
- Write clear, descriptive commit messages
- Always push after committing so GitHub Pages auto-deploys
- After pushing, verify the live site updated

## Commit Message Format
```
[type] Short description

Longer description if needed.

Trello: https://trello.com/c/iWUhQpVC
```

Types: `[feat]` new feature, `[fix]` bug fix, `[style]` visual/CSS changes, `[refactor]` code restructure, `[docs]` documentation

Example:
```
[feat] Add SVG body map with tappable regions

Replaced grid buttons with front/back body silhouette SVG.
Regions highlight on tap and link to photo upload flow.

Trello: https://trello.com/c/iWUhQpVC
```

## App Flow (current)
1. Welcome/landing (social proof, urgency stats)
2. Email + name + postcode capture
3. GDPR consent (data required, marketing optional)
4. Fitzpatrick skin type picker (6 types)
5. Risk profile questionnaire (11 questions, weighted scoring)
6. Photo capture (full body guided flow OR specific areas via body map)
7. ABCDE self-check education
8. Loading/processing animation
9. Mole Clinic Profile results (risk gauge, risk factors, service recommendation, nearest clinics, booking CTA, share/refer)

## Key Conversion Elements
- Email captured at step 2 (before any value delivered — this is the minimum viable lead)
- Risk nudges during questionnaire prime users to take results seriously
- Results screen has sticky booking CTA bar — always visible
- "Didn't book today?" section captures intent for email follow-up
- Re-check reminders keep users in the funnel
- Referral sharing generates new leads

## Future Phases (do NOT implement unless specifically asked)
- Backend API (Azure Functions)
- Database (Azure SQL / Cosmos)
- Photo storage (Azure Blob Storage)
- CRM integration (Microsoft Dynamics 365)
- Push notifications
- AI chat (Claude API)
- React Native / Expo migration for app stores
- Booking system integration (IntakeQ)
