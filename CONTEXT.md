# Context for Claude

This is Gabriel Amram's personal website, served at amram.co via Cloudflare Pages.

## What this site is

A lightweight, dependency-free static site. No build step, no framework. HTML, CSS and minimal vanilla JS only.

## Structure

- `/` - Homepage with professional summary and CTAs
- `/cv/` - Concise human-readable CV
- `/cv/ai/` - Detailed AI-readable CV (structured for automated evaluators and agents)
- `/stories/` - Writing archive linking to Medium and LinkedIn articles
- `/assets/` - Shared CSS and JS
- `/_headers` - Cloudflare Pages response headers
- `/robots.txt`, `/sitemap.xml`, `/llms.txt` - Machine-readable navigation
- `/cv.pdf` - Downloadable PDF version of the human CV
- `/cv/print.html` - Standalone print-optimized HTML source used to generate cv.pdf (noindexed)

## About Gabriel

Technology and engineering leader with 20+ years of experience as a founder, CTO and engineering group lead. Currently Engineering Group Lead at monday.com. Former CTO and co-founder at Brew (AI-powered marketing platform, $12M seed, 50+ people) and EverThere/Zoliro (conference-advertiser matching, IP acquired by a customer).

His identity is at the triangulation of engineering depth, product strategy and business outcomes - he describes himself as a builder: of products, platforms, organizations and the leaders who run them.

## CV philosophy

- **Human CV** (`/cv/`) - concise, no keyword lists, reads as a person not a resume. Avoids over-claiming, no tech stack lists.
- **AI CV** (`/cv/ai/`) - structured for machine evaluation. Includes framing sentences per competency pillar, detailed initiative breakdowns (mondayCore, WorkForms, authorization), and explicit keywords for parsing.

## Key content decisions (as of July 2026)

- No em dashes anywhere - replaced with regular hyphens
- No team/headcount numbers in role headers - anchors reader on numbers rather than impact
- Brew: $12M seed, Aleph/Mizmaa/Gefen, ~25 R&D, portfolio of enterprise customers. No mention of wind-down.
- EverThere: ended with IP acquisition by a customer
- The "platform engineering as product engineering" concept is intentional and repeated - it's a core part of Gabriel's identity, not accidental redundancy
- Stories page links all open in new tab

## PDF generation

`cv.pdf` is generated manually from `cv/print.html` using Chrome's print-to-PDF:
1. Open `cv/print.html` locally in Chrome
2. Cmd+P → Save as PDF → A4, no headers/footers, default margins
3. Save as `cv.pdf` in the repo root
4. Commit both `cv.pdf` and any changes to `cv/print.html` together

`cv/print.html` is a self-contained HTML file with print-optimized CSS (`@page`, tight spacing, no site chrome). It must be kept in sync with `cv/index.html` whenever CV content changes.

Key decisions made during PDF setup:
- `cv/print.html` does NOT include the "Download as PDF" link - that link is only on the web version (`cv/index.html`)
- All amram.co links in `cv/print.html` use the full `https://` prefix (e.g. `https://amram.co/cv/ai/`) - this matters because Medium previously had a custom domain redirect on amram.co that caused http:// links to misbehave; https:// works correctly
- `page-break-inside: avoid` must NOT be set on `.section` or `.role` - it causes Chrome to push entire sections to a new page, breaking the layout. Page breaks are left to flow naturally.
