# OBSIDIAN — *Bend sound around a point of no return*

A single-file, **dependency-free** landing page whose hero is a real-time **gravitational black hole**, rendered entirely in one WebGL2 fragment shader.

### ▶ [Live demo](https://daydreamer13.github.io/obsidian-blackhole/)

![WebGL2](https://img.shields.io/badge/WebGL2-raw%20shader-FF8A3C) ![deps](https://img.shields.io/badge/dependencies-0-05060A) ![size](https://img.shields.io/badge/files-1-FFD089)

## What it does

A full-screen fragment shader renders a Schwarzschild-style black hole with:

- **Gravitational lensing** — the starfield *and the headline itself* bend around the event horizon into an Einstein ring.
- **Doppler-beamed accretion disk** — relativistic beaming blazes the approaching side white-hot and dims the receding side to ember red (~5× brightness asymmetry), with domain-warped turbulent filaments.
- **Lensed halo** — the far side of the disk wraps up and over the shadow (the *Interstellar* arc).
- **Razor-thin photon ring** + soft bloom glow.

### Interaction
- **Move the cursor** → steer the singularity; the hole tracks your pointer and idles above the wordmark.
- **Press & hold** → raise the Schwarzschild radius; the hole *inhales* the layout, spiralling text and stars inward, then springs back.
- **Scroll** → lensing relaxes and the wordmark resolves into flat, legible type.

It degrades gracefully: a CSS-only void fallback when WebGL2 is unavailable, a static poster under `prefers-reduced-motion`, and a mobile/touch path (drag to steer, touch-and-hold to collapse).

## Tech

Raw **WebGL2**, one full-screen triangle, one fragment shader — no Three.js, no libraries, no build step. Everything (lensing, disk, beaming, fbm turbulence, the wordmark texture) lives in a single `index.html`. A quality governor auto-scales resolution/octaves to hold 60fps on weaker GPUs.

## Run

```bash
# any static server, e.g.
python -m http.server 4180
# then open http://localhost:4180
```
…or just open `index.html` in a modern browser.

---

*A fictional sound-design instrument brand, built as a creative demo with [Claude Code](https://claude.com/claude-code).*
