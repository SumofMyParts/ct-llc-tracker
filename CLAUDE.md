# Alchemy Dynamics LLC — CT Compliance & Startup Tracker

## Project Overview
Single-file HTML5 web application for tracking and managing Alchemy Dynamics LLC's Connecticut administrative compliance obligations AND the full startup build-out checklist. Covers annual reports, tax filings, registered agent requirements, USPTO trademark tracking, IP protection, and a comprehensive 40+ item startup checklist. Data stored in browser localStorage — no server, no dependencies, no build step.

## Company
- **Entity:** Alchemy Dynamics LLC
- **State:** Connecticut
- **Domains:** alchemydynamics.com, alchemydynamics.ai
- **Social:** X, YouTube, Facebook, GitHub, LinkedIn — all @AlchemyDynamics

## Tech Stack
- Single `index.html` — all HTML, CSS, and JavaScript embedded
- Zero dependencies — runs directly in any modern browser
- `localStorage` for all data persistence
- No npm, no build tools, no backend

## Project Structure
```
ct-llc-tracker/
├── index.html    ← entire application
└── CLAUDE.md     ← this file
```

## Opening the App
Open `index.html` directly in a browser:
- Windows: double-click `index.html`, or drag into browser
- WSL path: `/mnt/c/Users/Marco/develop/ct-llc-tracker/index.html`
- Windows path: `C:\Users\Marco\develop\ct-llc-tracker\index.html`

## Features
- **Dashboard** — compliance status, countdown timers, alerts for overdue/due-soon items
- **Profile** — LLC name, formation date, EIN, NAICS, tax classification, registered agent, members
- **Obligations** — all recurring state/tax/federal/local obligations; mark as filed, add custom items
- **Annual Report** — pre-filing checklist, deadline countdown, direct link to CT.gov filing portal
- **Tax Calendar** — year-selectable timeline of CT tax deadlines; CT-PET election tracker; extension tracking
- **Startup Checklist** — 40+ item master checklist across Legal, IP, Digital Presence, Financial, and Operations
- **Filing History** — chronological log of all recorded filings; CSV export

## Connecticut LLC Compliance Reference
| Obligation | Due Date | Fee | Portal |
|---|---|---|---|
| Annual Report (SoS) | March 31 (window: Jan 1–Mar 31) | $80 | business.ct.gov |
| CT-1065/CT-1120SI (DRS) | March 15 (payment); Sep 15 (extended filing) | varies | portal.ct.gov/drs |
| CT-PET (optional election) | March 15 (payment) | varies | portal.ct.gov/drs |
| Registered Agent | Continuous | — | business.ct.gov |
| DRS Registration | One-time | $100 | portal.ct.gov/drs |

## Data Storage
All data lives in `localStorage` under the key `ct_llc_tracker_v1`. To reset: open DevTools → Application → Local Storage → delete the key.

## Conventions
- All state lives in the `data` object; always call `saveData()` after mutations
- Views are rendered on demand by `renderView(name)` — no reactive framework
- Built-in obligations have `isBuiltIn: true` (cannot be deleted via UI)
- Annual due dates are computed dynamically via `nextAnnualDate()` — always shows the next upcoming occurrence
- `computeStatus(ob)` is the single source of truth for obligation status badges and alerts

## Git Workflow
- Always commit and push after every meaningful change.
- One feature, fix, or concern per commit — no bundling unrelated changes.
- Imperative mood commit messages (e.g., "Add CT-PET payment tracking to tax calendar").
- After every commit, run `git push origin main`.
- Never leave uncommitted changes at the end of a session.
