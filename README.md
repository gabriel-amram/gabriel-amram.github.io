# amram.co

A lightweight, dependency-free personal site for Gabriel Amram.

## Routes

- `/` — Professional homepage
- `/cv/` — Concise human-readable CV
- `/cv/ai/` — Detailed AI-readable CV
- `/stories/` — Writing archive
- `/llms.txt` — Machine-readable navigation
- `/robots.txt`
- `/sitemap.xml`

## Local preview

From the repository directory:

```bash
python3 -m http.server 8000
```

Then open `http://localhost:8000`.

## Deploy to Cloudflare Pages

Use these settings:

- Framework preset: None
- Build command: leave empty
- Build output directory: `/`
- Root directory: `/`

Because this is a static site with no build step, Cloudflare Pages can publish the repository directly.

## Deploy to GitHub Pages

In repository settings, enable Pages and deploy from the root of the default branch. Add `amram.co` as the custom domain.

## Domain setup

GoDaddy may remain the registrar. Point DNS to whichever host is selected. For Cloudflare Pages, the simplest setup is to use Cloudflare nameservers and attach `amram.co` as a custom domain.

## Before publishing

1. Confirm role dates.
2. Replace placeholders on `/stories/` with the correct Medium URLs.
3. Consider adding quantified adoption and impact metrics when available.
4. Add a PDF at `/cv.pdf` once the human CV layout is finalized.
5. Review whether the phone number should remain public on the website.
