# Lumencraft — native HTML site

![Lumencraft homepage — full-page scroll preview](docs/preview/homepage.gif)

<sub>Full-page scroll of `index.html` at 1440×900 · [hero screenshot](docs/preview/hero.png)</sub>

Static native HTML/CSS/JS site. No framework, server or build step is needed to view it: open `index.html` directly in a browser.

## Structure

```
index.html, about.html, services.html, flex.html, the-hub.html, work.html,
case-studies.html, industries.html, blog.html, contact.html, careers.html,
book-a-call.html, privacy.html, terms.html, cookie-policy.html, 404.html
services/<category>.html + services/<category>/<sub>.html   (4 categories + 24 sub-services)
work/<project>.html            (24 project detail pages)
case-studies/<slug>.html       (12)
industries/<slug>.html         (10)
blog/<slug>.html               (15 articles)
the-hub/app.html               (dashboard demo)
assets/css    base.css (chrome) · home.css · pages.css
assets/js     main.js (global) · home.js · pages.js
assets/img/u  Unsplash photos (local) · assets/img/favicon.svg
assets/video  reel.mp4 + reel-poster.jpg (Mixkit clips + Mixkit music)
assets/fonts  Plus Jakarta Sans + Victor Mono (Google Fonts, OFL)
docs/preview  homepage.gif + hero.png (README preview)
```

Total: 106 pages.

## Editing copy

Copy lives directly in the HTML files. Shared header, footer, chat widget and cookie banner markup is repeated in every page, so a change there has to be applied to all pages (a project-wide find-and-replace works well).

## States & interactions that were built

- Desktop preloader: particle canvas (cursor repels), logo draw → wordmark, "Click to enter", boom exit (auto-exits after ~4.4s).
- Hero: dot globe canvas with arcs + comets, orb mouse parallax, rotating ring of 30 work tiles (pauses on hover, swipeable on mobile).
- Statement & headline text lights up word by word as you scroll; footer statement lights up in sequence.
- Service rows: sticky media + entrance clip; growth panel with count-ups + donut; animated AI panel.
- Hub window tilts while scrolling; like buttons on work cards (saved in localStorage).
- **Sound:** only the "reel" video in the "Based in…" section (mute/unmute button).
- Chat widget (label changes with scroll position, typing indicator, simulated replies; no backend).
- Cookie banner + Consent Preferences modal, mobile drawer menu (focus trap, Esc), FAQ accordions.
- Contact form: progress %, validation, phone formatting, success state (no data is sent).
- Booking calendar (date/time picker → confirm modal → done), careers apply modal, team member modal.
- Blog: load more, reading progress bar, TOC with active state, share/copy link, interactive aiSEO tabs.
- Industries: hover list switches image; Flex: rotating phrase, draggable marquee, block picker; Hub App: feature tabs; 404: starfield + astronaut.

## Placeholders to replace

Brand "Lumencraft", logo, address, phone (954) 555-0148, email hello@lumencraft.studio, team names,
client/project names, case study numbers, testimonials, and the legal text (privacy/terms/cookie are demo text).
All photos are from Unsplash; the video uses Mixkit clips + Mixkit music.

## Regenerating the preview

The GIF was recorded with headless Playwright (Chromium, 1440×900 video): wait ~5s for the preloader and hero intro,
dismiss the cookie banner via stored consent, then scroll with mouse-wheel steps of 110px every 55ms until the
scroll position stops changing, and hold 1.5s on the footer. It was converted with ffmpeg at 640px wide, 8fps,
a 96-color palette and infinite loop (~5.6 MB).
