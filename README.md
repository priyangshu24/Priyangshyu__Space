# Priyangshu Dey · Portfolio

A single-page, single-file portfolio site — no build step, no framework. Glassmorphism UI, GSAP-driven motion, a Three.js globe-to-city walk, an ASCII terminal intro, a "Dev Arcade," a Google Calendar booking flow, and a Claude-powered AI twin.

**Live:** open `index.html` through a local server (see below) — this is a static site with no deployed URL configured yet.

## Features

- **Hero terminal intro** — animated ASCII/typing sequence introducing the site.
- **Interactive globe** — Three.js scene that transitions from a rotating globe into dotted city photos (`cities/c1.jpg`–`c10.jpg`), rendered as point clouds sampled from pixel data.
- **Selected work** — case-study style project cards for *Sentinel* (LLMOps eval platform), *Orion* (AI-native CI/CD), and *COCO* (local-first AI desktop operator), each with a small live illustration (pipeline animation, voice waveform, etc.).
- **AI twin** — a chat panel that answers questions in Priyangshu's voice. Falls back to pre-written answers by default; live answers are available when the page is opened as a Claude artifact and the visitor grants Claude access.
- **Experience timeline** — animated scroll-linked timeline of roles at AI Data Craft Tech / Adhyaapak.
- **Stack panels** — categorized chips for languages, AI/ML, frontend, backend, cloud & data, and mobile.
- **Book a call** — a real booking calendar (5 slots/weekday, IST-based, configurable duration) that deep-links into Google Calendar with the event pre-filled.
- **Dev Arcade** — a small collection of interactive dev-themed mini experiences (see `index.html` for details).

## Getting started

The dotted city visuals read raw pixel data from the images in `cities/`, and browsers block that (CORS/canvas tainting) when the file is opened directly (`file://`). Serve it over HTTP instead:

```bash
# from this folder
python -m http.server 5500
# then open http://localhost:5500
```

Or in VS Code: install the **Live Server** extension, then right-click `index.html` → **Open with Live Server**.

No dependencies to install and no build step — everything ships in one HTML file.

## Project structure

```
.
├── index.html      # entire site: markup, styles, and JS in one file
├── cities/         # c1.jpg … c10.jpg — greyscale city photos for the dotted-globe backgrounds
└── README.md
```

## Tech

- Vanilla HTML/CSS/JS — no bundler, no framework.
- [GSAP 3.12.5](https://gsap.com/) for scroll reveals, transitions, and micro-interactions.
- [three.js r128](https://threejs.org/) for the WebGL globe and city-walk scene.
- Loaded via CDN (cdnjs) — see the `<script>` tags at the top of `index.html`.

## Notes

- **AI twin:** outside of Claude, it only uses pre-written answers. Live Claude-generated answers work only when the page is opened as a Claude artifact.
- **Photo credits:** city photos are sourced from Wikimedia Commons under CC licenses; credits are listed in the page footer. Keep them if you fork or deploy this site.
- **Booking flow:** slot state is kept in `localStorage` on the visitor's own browser (`pd-bookings`) purely to avoid double-booking the same slot in one session — there's no backend.

## License

Content and code are personal portfolio material. Photo credits are as noted in the footer; please retain them if you reuse this project.
