# CLAUDE.md

This file gives Claude Code (and anyone else using AI tools on this repo) the context it needs to work on this project well.

## What this project is

This is Devansh Singla's personal portfolio website. He is a Chartered Accountant, and this site is aimed at recruiters and hiring managers for **finance analyst** and **management consulting** roles. It is effectively a public resume/landing page, so first impressions matter a lot here.

## Top priorities (in order)

1. **Professional look** — the site represents a finance/consulting candidate. Keep the tone, layout, and visuals polished, clean, and business-appropriate. Avoid anything that looks like a "hobby project" (flashy animations, casual language, cluttered layouts).
2. **Fast loading** — recruiters will not wait around. Keep the page lightweight: avoid adding large libraries, frameworks, or heavy images/fonts unless there's a clear need. Prefer plain HTML/CSS/JS over adding a build system.

## Hard rule: never change the overall design without asking first

Do not change the site's layout, color scheme, fonts, or visual structure on your own initiative — even if it seems like an improvement. This includes things like:
- Changing the color palette, fonts, or spacing system defined in the `:root` CSS variables in `index.html`.
- Restructuring sections, the navigation bar, or the hero layout.
- Swapping the overall visual style (e.g. card styles, accordion behavior for the Experience section).

Small, clearly-scoped fixes (typos, broken links, updating text content, fixing a bug) are fine to do directly. Anything that changes how the site *looks or is organized* should be proposed first, with a short explanation of what would change and why, before making the change.

## Explain changes using both technical terms and plain language

Devansh is not a developer, but he wants to learn the real technical terms too — not just simplified summaries. When describing what was changed (in commit messages, PR descriptions, or comments), state the technical term or jargon first, then immediately explain what it means in plain, non-technical language. For example:
- "Refactored the RSS-to-JSON fetch logic (i.e., fixed how the blog posts load on the page so they show up more reliably)."
- "Added a media query breakpoint (i.e., made the page look better on phones and tablets)."

Don't drop the jargon and don't drop the plain-language explanation — include both, every time.

## Project structure

This is a static site with no build process:
- `index.html` — the entire site: HTML structure, all CSS (in a `<style>` block), and all JavaScript (in a `<script>` block) live in this one file.
- `profile.jpg` — profile photo used in the hero section.

There is no `package.json`, no framework, and no build/bundling step. Changes are made directly to `index.html` and take effect immediately when the file is opened or deployed.

Notable behavior to be aware of:
- The "Equity Research Reports" and "Latest Blogs" sections are populated at page-load time via JavaScript, by fetching Devansh's Blogspot RSS feed through the `rss2json.com` public API. If that feed or API is unavailable, those sections show a fallback message.

## How to check your work

Since there's no build step, the way to verify a change is to open `index.html` directly in a browser (or serve the folder with any static file server) and visually check the page, including on a narrow/mobile-width window, since the layout has mobile-specific styles.
