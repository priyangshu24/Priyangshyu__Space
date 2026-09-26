# Priyangshu Dey · portfolio

A single-page portfolio: glass UI, GSAP animation, a Three.js globe-to-city walk, an ASCII terminal intro, Dev Arcade and an AI twin.

## Run it

The dotted cities read pixels from the images in `cities/`, and browsers only allow that over http, not when you double-click the file.

- **VS Code:** install the **Live Server** extension, then right-click `index.html` → *Open with Live Server*.
- **Or from a terminal in this folder:** `python -m http.server 8000`, then open http://localhost:8000

## Files

- `index.html`: the whole site (HTML, CSS and JS in one file).
- `cities/c1.jpg` to `c10.jpg`: greyscale city photos used for the dotted backgrounds.

## Notes

- **AI twin:** outside Claude, it uses the pre-written answers. Live Claude answers only work when the page is opened as a Claude artifact.
- **Credits:** the photos come from Wikimedia Commons under CC licenses, and the credits are in the page footer. Keep them if you deploy the site.
- **Libraries:** GSAP 3.12.5 and three.js r128 load from cdnjs.
