# Stanley Research Group — Project Brief

## What This Is

This is a standalone professional landing page for Jason Stanley's OSINT research services. It is **completely separate** from the main journalism site (`kcgovcorruption-site`). Do not mix these codebases.

The site is a single-page marketing/contact site targeting plaintiff attorneys who need investigative research support — primarily § 1983 civil rights cases, wrongful death, jail conditions, and First Amendment litigation.

## Why It Was Built

Jason runs Kootenai County Corruption (kootenaicountycorruption.org), an investigative journalism operation covering government misconduct in northern Idaho. Over the course of that work he has built a deep capability in:

- OSINT research on public officials (career history, lawsuits, financials, contractor connections)
- Idaho Public Records Act filings — drafted, tracked, and followed up
- Court docket research (PACER, CourtListener, iCourt, Justia)
- Document analysis — budgets, inspection reports, contracts, grievance logs

The journalism site is free and always will be (Jason made a public commitment to his audience). This service site is the monetization layer — he can sell the same research skills to attorneys without touching the journalism site's brand.

The primary value proposition: attorneys fighting local governments often lack someone who knows how to navigate Idaho public records law, find civil litigation history on sheriffs, and pull institutional-failure patterns from budget data. Jason has done all of this already on Kootenai County. He can do it for attorneys anywhere in Idaho and the Pacific Northwest.

## Target Audience

Plaintiff attorneys, specifically:
- § 1983 civil rights counsel
- Wrongful death counsel (in-custody deaths especially)
- First Amendment lawyers (press retaliation, public meeting removal)
- Jail conditions litigation (ADA, medical neglect, overcrowding)

The tone is **professional and credibility-forward**, not salesy. The page reads like a quiet specialist making themselves known, not a pitch deck. Attorneys are skeptical people — the page earns trust through specificity and real proof-of-work, not claims.

## Owner / Contact Info

- **Owner:** Jason Stanley
- **Contact email on site:** jasonstanl3y@gmail.com
- **Journalism site:** kootenaicountycorruption.org
- **U.S. Press Association credential:** ID #802085569

## Design System

The aesthetic is "classified dossier" — dark background, amber/gold accent, IBM Plex Mono for labels and code-style UI elements, IBM Plex Serif for body text, Bebas Neue for display headings. The look signals precision and documentation, not flashy marketing.

Colors (dark mode default):
- `--bg: #0b0c0e` (near black)
- `--surface: #13151a`
- `--accent: #c8a84b` (amber gold — primary brand color)
- `--accent2: #4b7fc8` (steel blue — secondary)
- `--red: #c84b4b` (used sparingly for alert-level stamps)

Light mode uses a warm off-white (`#f0ede6`) that preserves the document aesthetic.

## File Structure

```
stanley-research/
  index.html     — the entire site (single page, self-contained)
  server.js      — minimal Express static server for Railway
  package.json   — dependencies (just express)
  CLAUDE.md      — this file
```

## Hosting

Hosted on Railway (same account as the main journalism site). This is a separate Railway service — it gets its own domain/URL. Deploy steps:

1. `cd C:\Users\jason\Documents\Projects\stanley-research`
2. `git init && git add . && git commit -m "Initial deploy"`
3. Link to a new Railway service (not the existing kcgovcorruption service)
4. Railway auto-detects Node.js and runs `npm start`

**Do not deploy to the same Railway service as the journalism site.**

## What to Update Over Time

1. **Email address** — currently `jasonstanl3y@gmail.com`; two instances in `index.html` if it ever changes
2. **Case study stats** — the "200+ Documents Archived", "10 Civil Cases Catalogued" etc. are current as of Oct 2026; update them as the investigation grows
3. **Service area** — currently says "Idaho · Pacific Northwest"; expand if Jason starts taking cases from other states
4. **New case studies** — if a major case gets resolved and Jason can name it, add a second case study card below the Kootenai County one
5. **Pricing** — right now contact-first ("we discuss scope and rate"). If Jason ever wants to add a rates table, add a section above the contact box

## What NOT to Do

- Do not connect this to the journalism site's Supabase instance
- Do not add a CMS or admin panel — Jason edits the HTML directly
- Do not add Google Analytics or any tracking without Jason's explicit ask
- Do not publish case details from the private Norris dossier on this page — the dossier is for internal research use only; the page only references the public journalism site as proof-of-work
- Do not name confidential sources, tipsters, or anyone under a family privacy hold (see the main site's memory files for those rules)
- Do not add a contact form that submits to a server — Jason's current email is shown as text + copy button; a real form would need backend handling we don't have

## Relationship to Main Site

These are **completely separate projects**. The only connection is:
- Same owner (Jason Stanley)
- The landing page links to `kootenaicountycorruption.org` as proof-of-work
- Same Railway account for hosting

Do not import code, routes, or dependencies from one into the other.
