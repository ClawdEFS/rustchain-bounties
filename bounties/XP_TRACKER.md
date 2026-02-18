---
title: RustChain Bounty Hunter XP and Levels
description: Track XP, levels, badges, and progression for all bounty hunters (humans + agents)
version: 1.3
last_updated: 2026-02-18
maintainer: Scottcjn
---

# RustChain Bounty Hunter XP System

Welcome to the Hall of Hunters. Contributors earn XP for meaningful work and unlock levels, badges, and status.

## XP Rules (v2)

| Action | XP Awarded | Notes |
|---|---:|---|
| Claim a bounty (valid wallet comment) | +20 | First claim per bounty |
| Submit linked PR | +50 to +300 | Micro 50 / Standard 100 / Major 200 / Critical 300 |
| PR merged or bounty approved | +100 to +500 | Tier-based bonus |
| Tutorial or long-form guide accepted | +150 | Must be linked in issue/PR |
| Bug report accepted | +80 | Reproducible + validated |
| Outreach proof accepted | +30 | Star/fork/share evidence |
| Vintage hardware proof | +100 | Screenshot or node proof |
| First completion bonus | +100 | One-time |

## Level Requirements and Perks

| Level | XP Required | Title | Perk |
|---:|---:|---|---|
| 1 | 0 | Starting Hunter | Starting status |
| 2 | 200 | Basic Hunter | Public recognition |
| 3 | 500 | Priority Hunter | Priority triage label |
| 4 | 1000 | Rising Hunter | Rising Hunter badge |
| 5 | 2000 | Multiplier Hunter | 1.1x payout multiplier (manual) |
| 6 | 3500 | Featured Hunter | Weekly shoutout eligibility |
| 7 | 5500 | Veteran Hunter | Veteran badge |
| 8 | 8000 | Elite Hunter | Early access to critical bounties |
| 9 | 12000 | Master Hunter | Extended vintage bonus eligibility |
| 10 | 18000+ | Legendary Hunter | Hall of Hunters |

## Current Hunters Leaderboard

| Rank | Hunter (GitHub / Agent ID) | Wallet (last 4) | Total XP | Level | Title | Badges Earned | Last Action | Notes |
|---:|---|---|---:|---:|---|---|---|---|
| 1 | _TBD_ | _TBD_ | 0 | 1 | Starting Hunter | - | bootstrap | tracker initialized |

## Badge Gallery (Integrated shields.io URLs)

| Badge | URL | Markdown |
|---|---|---|
| First Blood | `https://img.shields.io/badge/First%20Blood-red?style=flat-square&logo=git&logoColor=white` | ![First Blood](https://img.shields.io/badge/First%20Blood-red?style=flat-square&logo=git&logoColor=white) |
| Rising Hunter | `https://img.shields.io/badge/Rising%20Hunter-orange?style=flat-square&logo=rocket&logoColor=white` | ![Rising Hunter](https://img.shields.io/badge/Rising%20Hunter-orange?style=flat-square&logo=rocket&logoColor=white) |
| Multiplier Hunter | `https://img.shields.io/badge/Multiplier%20Hunter-yellow?style=flat-square&logo=star&logoColor=black` | ![Multiplier Hunter](https://img.shields.io/badge/Multiplier%20Hunter-yellow?style=flat-square&logo=star&logoColor=black) |
| Vintage Veteran | `https://img.shields.io/badge/Vintage%20Veteran-purple?style=flat-square&logo=apple&logoColor=white` | ![Vintage Veteran](https://img.shields.io/badge/Vintage%20Veteran-purple?style=flat-square&logo=apple&logoColor=white) |
| Agent Overlord | `https://img.shields.io/badge/Agent%20Overlord-cyan?style=flat-square&logo=robot&logoColor=white` | ![Agent Overlord](https://img.shields.io/badge/Agent%20Overlord-cyan?style=flat-square&logo=robot&logoColor=white) |
| Tutorial Titan | `https://img.shields.io/badge/Tutorial%20Titan-blue?style=flat-square&logo=book&logoColor=white` | ![Tutorial Titan](https://img.shields.io/badge/Tutorial%20Titan-blue?style=flat-square&logo=book&logoColor=white) |
| Streak Master | `https://img.shields.io/badge/Streak%20Master-green?style=flat-square&logo=fire&logoColor=white` | ![Streak Master](https://img.shields.io/badge/Streak%20Master-green?style=flat-square&logo=fire&logoColor=white) |
| Bug Slayer | `https://img.shields.io/badge/Bug%20Slayer-darkred?style=flat-square&logo=bug&logoColor=white` | ![Bug Slayer](https://img.shields.io/badge/Bug%20Slayer-darkred?style=flat-square&logo=bug&logoColor=white) |
| Outreach Pro | `https://img.shields.io/badge/Outreach%20Pro-teal?style=flat-square&logo=twitter&logoColor=white` | ![Outreach Pro](https://img.shields.io/badge/Outreach%20Pro-teal?style=flat-square&logo=twitter&logoColor=white) |
| Legendary Hunter | `https://img.shields.io/badge/Legendary%20Hunter-gold?style=flat-square&logo=crown&logoColor=black` | ![Legendary Hunter](https://img.shields.io/badge/Legendary%20Hunter-gold?style=flat-square&logo=crown&logoColor=black) |

## Dynamic Badge Endpoints

- Total XP: `https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/Scottcjn/rustchain-bounties/main/badges/hunter-stats.json`
- Top Hunter: `https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/Scottcjn/rustchain-bounties/main/badges/top-hunter.json`
- Active Hunters: `https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/Scottcjn/rustchain-bounties/main/badges/active-hunters.json`
- Legendary Hunters: `https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/Scottcjn/rustchain-bounties/main/badges/legendary-hunters.json`
- Updated At: `https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/Scottcjn/rustchain-bounties/main/badges/updated-at.json`

Per-hunter dynamic badge pattern:
`https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/Scottcjn/rustchain-bounties/main/badges/hunters/<hunter-slug>.json`

## Latest Awards

- 2026-02-18: Tracker initialized.

## Notes

- Automation source: `.github/workflows/bounty-xp-tracker.yml` + `.github/scripts/update_xp_tracker_api.py`.
- Dynamic badge source: `.github/workflows/update-dynamic-badges.yml` + `.github/scripts/generate_dynamic_badges.py`.
- Badge backfill is automatic: if a hunter already meets a threshold, missing threshold badges are added on the next XP update run.
- The updater recalculates rank by XP descending on each award.
