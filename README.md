# Fireflies

An interactive web project that uses real-time face and hand tracking to drive
generative visuals in the browser. Built as part of coursework at Bezalel
Academy of Arts and Design.

## Live site

https://omri-bergman.github.io/Fireflies/

## How it works

The page accesses the user's webcam and runs Google's MediaPipe models in the
browser to detect faces and hands. The detected landmarks feed a canvas /
Three.js scene that renders different visual modes, including a typographic
"headline" mode that draws large characters over the live video.

## Tech

- HTML / CSS / vanilla JavaScript
- [MediaPipe](https://developers.google.com/mediapipe) — face detection & hand tracking
- [Three.js](https://threejs.org/) — 3D rendering
- Hosted on GitHub Pages

## Running locally

This is a static site — no build step. The MediaPipe scripts are loaded from a
CDN and the browser needs camera permission, so it must be served over HTTP(S)
(not opened as a `file://` URL).

From the project root:

```bash
python3 -m http.server 8000
```

Then open http://localhost:8000 and click **Start Camera**.

## Project structure

```
├── index.html          # Entry point
├── articles/           # Article pages (influences, editors, remake, …)
├── css/                # Stylesheets
├── images/             # Image assets
└── js/
    ├── navbar.js
    └── homePageScript.js   # Main interaction / rendering logic
```

## Controls

- **Start / Stop Camera** — toggles the webcam feed
- **Next Mode** — cycles through visual modes
- **Randomize Order** — toggles sequential vs randomized character order
