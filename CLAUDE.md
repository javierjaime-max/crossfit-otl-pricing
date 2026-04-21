# CLAUDE.md — CrossFit OTL Pricing Tools

Static HTML tools for CrossFit OTL pricing consultations and member marketing.
Deployed on Vercel. No build step — raw HTML/CSS/JS files.

---

## What's Here

| File | What It Is | Status |
|------|-----------|--------|
| `pricing-consultation.html` | Interactive pricing tool for consultations with prospective members | Live |
| `crossfit-explainer.html` | What is CrossFit? explainer for walk-ins / cold prospects | Live |
| `leaderboard.html` | Member transformation leaderboard (fat loss / muscle gain) | Built Apr 2026 |
| `index.html` | Entry point / redirect | Minimal |

---

## CrossFit OTL Ecosystem (under Fit4)

CrossFit OTL has three layers — this repo lives in **Prospect Engagement**.

| Layer | What | Where |
|-------|------|-------|
| **External** | Public website, social media (future) | `crossfit-otl/` → crossfit-otl.com |
| **Prospect Engagement** | Pricing guide, explainer, leaderboard | `crossfit-otl-pricing/` ← YOU ARE HERE |
| **Internal / Coach Dev** | CCFT study app, CCFT-Brain (Obsidian) | `ccft-study-app/`, Obsidian vault |

Knowledge source: Javier's Obsidian brain → Atlas S3 vault when needed.

Social media (future): sourced from photo library + CCFT knowledge base.

---

## Context

CrossFit OTL charges **$180/4 weeks** flat rate. No tier confusion, no upsells.

The pricing consultation tool is used when Yvette (or any coach) sits down with a prospect.
It walks them through:
1. What they're getting (facility, programming, community, coaching)
2. Cost breakdown vs. alternatives (commercial gym, personal training)
3. The single price — $180/4 weeks — and how to join

The leaderboard is for social proof / member motivation. It shows real members' fat loss + muscle gain deltas from InBody scans.

---

## Data Sources (leaderboard)

- **InBody scans** — exported as `.xls` from InBody device, parsed for fat mass / lean mass deltas
- **PushPress** — member roster (`members.csv`) and attendance (`attendance.csv`) exported from admin panel
- Cross-referenced by name to build member highlight cards

Member approval required before any profile goes live. Obtained from Deanie / coaches.

---

## Deploy Pipeline

```bash
git add -p
git commit -m "feat: <what changed>"
git push origin main
# Vercel auto-deploys
```

No build step. Vercel serves static files directly.

---

## Assets

```
photos/          # Member photos (manually added, named by member)
assets/          # CSS, JS, icons
```

Photo naming convention: `firstname-lastname.jpg` (lowercase, hyphenated)

---

## Ownership

- Deanie runs day-to-day operations
- Coaches: Nicholas, Ava, Clay
- Javier owns pricing strategy and digital tools
- Atlas owns go-to-market analysis and content — proposes, Javier approves

---

## Active Projects (as of Apr 2026)

1. **Pricing consultation tool** — review and update content to reflect current offer
2. **Leaderboard** — add photo assets when available from coaches
3. **Digital pricing guide PDF** — not yet built; vault note exists with outline

---

## Session Protocol

```bash
cd ~/Library/CloudStorage/OneDrive-OnTheLineFitness/GitHub/crossfit-otl-pricing
git pull
# Open files directly — no build step needed
# Test locally by opening HTML files in browser or using a simple server:
python3 -m http.server 8080
git push origin main
```
