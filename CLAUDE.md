# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This project is a **single-page landing page** for an AI course by **AI BBC**:

- **Course name:** AI轉型不能等，3小時帶你無痛上手 (AI Transformation Can't Wait — 3 Hours to Get You Started)
- **Registration URL:** https://www.surveycake.com/s/l78MP (target=`_blank`)
- **Organizer:** AI BBC
- **Full spec doc:** `LandingPage_完整開發說明書.docx`

## Building the Page

The spec recommends **HTML + CSS** (Claude Code can generate directly, deploy via GitHub Pages). Alternatives: Notion, Canva, Framer.

There is no build system — the output is a static `index.html` file.

## Architecture: 8 Page Sections

Sections flow in this psychological order (引發恐懼 → 點燃希望 → 建立信任 → 推動行動):

| ID | HTML id | Purpose |
|----|---------|---------|
| 01 | `section-hero` | Main visual — tagline, title, CTA button, date/price summary |
| 02 | `section-urgency` | Pain points — creates urgency |
| 03 | `section-benefits` | 6 benefit cards (2×3 grid → 1×6 on mobile) |
| 04 | `section-outline` | 6 course units, accordion on desktop / all expanded on mobile |
| 05 | `section-info` | Course info: date, location, price, payment instructions |
| 06 | `section-who` | Two-column "Is this for you?" checklist |
| 07 | `section-guarantee` | Three learning guarantees |
| 08 | `section-cta` | Final CTA: QR code + button + 3-step signup instructions |

## Design System

### Colors
| Purpose | Hex |
|---------|-----|
| Primary deep blue (Hero bg, headings) | `#1A3C5E` |
| Mid blue (hover, links) | `#2E75B6` |
| Orange (CTA buttons, key numbers, tagline) | `#E8722A` |
| Red (urgency, sold-out warnings) | `#C0392B` |
| Green (benefits, guarantees, left-column) | `#27AE60` |
| Light blue bg | `#D5E8F0` |
| Light yellow bg | `#FFFDE7` |
| Light orange bg | `#FFF3E0` |
| Body text | `#1A1A1A` |

### Typography (中高齡 optimized — minimum 18px body)
| Level | Mobile | Desktop |
|-------|--------|---------|
| Page title / Hero tagline | 36–40px | 48–56px |
| Section headings | 28–32px | 36–40px |
| Card titles | 20–22px | 22–24px |
| Body text | 18–20px | 20–22px |
| Fine print | 16px | 16–18px |

Line height: 1.8–2.0. Paragraphs ≤ 3 lines, ≤ 50 characters.

### Breakpoints
`576px` / `768px` / `1200px` — Mobile-First.

## Key UX Rules for Older Users (中高齡 UX)

- **Sticky bottom bar (mobile):** Orange "▶ 立即報名" button always visible
- **CTA button:** height ≥ 56px (finger-friendly), width 100% on mobile
- **No accordion on mobile** — expand all course units by default
- **No light-grey text** — all text contrast ≥ 4.5:1 against background
- **Phone numbers:** use `tel:` links for auto-dial
- **LINE links:** use `line.me/ti/p/` format to open LINE App directly
- **QR Code on mobile:** replace with a direct-link button (older users may not know how to scan)
- **QR Code on desktop:** ≥ 200×200px, labeled "掃描報名"
- Never use color alone to convey meaning — always pair emoji/icon with text

## Technical Requirements

- **LCP ≤ 2.5s** (older users will close slow pages)
- **Target browsers:** Chrome latest, LINE in-app browser (iOS & Android), Safari iOS
- **SEO meta:**
  - `<title>`: AI轉型不能等，3小時帶你無痛上手 | 草屯 AI 課程
  - `og:description`: 不用懂電腦，帶手機就能學。5/23、5/30 開課，名額有限
  - `og:image`: Hero screenshot at 1200×630px (critical for LINE share preview)

## Content That Still Needs to Be Filled In

The spec marks these as `（待填入）` — do not fabricate values, leave as placeholders:

- Bank transfer account (玉山銀行 808, account number, account name)
- LINE Pay / 街口支付 QR code image
- Contact LINE account ID
- Contact phone number
- Hero image (real photo of older woman using phone — **not AI-generated**)
- QR code PNG file (links to registration URL)
- AI BBC logo/wordmark file
- Registration deadline (or use "額滿為止")
- Google Analytics ID (optional)
- Facebook Pixel / LINE Tag (optional)

## Copy Style Rules

- Use plain Chinese — no English tech jargon (Prompt, API, Cloud, UX, etc.)
- Address reader as「你」, never「學員」or「使用者」
- Every feature → state the **result for the user**, not the feature name
- Headlines ≤ 15 characters; card copy ≤ 60 characters
- Urgency phrases: 「名額快滿了」「現在不學，就是讓機會跑掉」
