# ahmed.ee — Portfolio Site

Personal site for Arbab Ahmed (Electronics Engineer, EIT). Single static `index.html` on GitHub Pages, domain ahmed.ee. Supports an active job search for full-cycle PCB/hardware design roles.

## Architecture rules

- Single HTML file, no build step, no framework. Maintainability beats cleverness. Any change that makes the file harder to hand-edit needs justification.
- Dark PCB-inspired theme: copper (`--copper: #e8953a`), blue, dark blue-black. Evolve it, don't replace it.
- Restraint over flash: no heavy animation, no scroll-jacking, fast load. Desktop is the primary review context.

## Copy rules

- Arbab makes final edits himself. Deliver drafts and options; never silently overwrite his copy.
- No fabrication or inflation. Every claim must trace to verified facts. When in doubt, leave it out and flag it.
- Do NOT describe him as "sole PCB designer" at Open Ocean Robotics in new copy. Correct framing: owned layouts and hands-on schematic/PCB work. (Existing instances on the site are a known, deliberately deferred fix — see backlog.)
- Do not mention his current contract role (RST Instruments) without asking him first.
- Voice: short direct sentences, engineer-to-engineer, every claim carries a specific (voltage, layer count, protocol). Banned: em dashes in prose, "architected," "passionate," "leveraged," "spearheaded," and similar filler.
- No GitHub links anywhere — he doesn't do work in GitHub.
- The `ahmed-ee-handoff.md` doc (if provided in a conversation) is a jumping-off point, not the final word. Arbab's direct feedback overrides it.

## Brand assets

`Minimal_A.png` (repo root) is the source brand mark: flat copper "A" with PCB traces on black. `favicon.png` (64px), `apple-touch-icon.png` (180px), and `og-image.png` (1200x630) are all derived from it by cropping/downscaling. Regenerate from the source if it ever changes. `Stylized_A.png` is an alternate glossy version of the same mark, currently unused.

## Backlog

### Deferred: "sole PCB designer" rewording (discuss with Arbab before doing)
Appears in the featured project card and the Open Ocean Robotics experience bullet in `index.html`. Needs rewording. Arbab wants to handle this after the other fixes land — raise it, don't just do it.

### Resume download button (good task for a small/cheap model)
Add a resume-download CTA to the hero (e.g. a third button or replace "Get in Touch"). Steps:
1. Arbab provides `resume.pdf` (or similar) at the repo root.
2. Add `<a href="/Arbab-Ahmed-Resume.pdf" download class="btn-secondary">Resume ↓</a>` (or `btn-primary` — his call) to the `.hero-ctas` div.
3. Optionally repeat it in the contact section.
Filename should be human-friendly since it lands in a recruiter's Downloads folder.

### OG image v2 (waiting on Arbab's reworked artwork)
Meta-tag inspectors flag `og-image.png` as missing "conversion text." Fix when Arbab reworks the mark: recompose the 1200x630 card with his name and title (e.g. "ARBAB AHMED / PCB Design") next to the A. The compose step is a PowerShell System.Drawing crop/scale onto a 1200x630 black canvas.

### Future polish (P3 — not scheduled)
- Mobile nav: `.nav-links` is `display: none` under 800px with no replacement. Add a minimal collapsed nav.
- Respect `prefers-reduced-motion`: disable the fadeUp/fade-in animations for users who opt out.
- Semantics: project titles and card headings are `div`s; switch to `h3` for screen readers/SEO.
- Contrast check: `--muted: #5e7490` on `#07090d` is near the WCAG AA line for small text.
