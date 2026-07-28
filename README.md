# SMU SurfaceWare Kiosk — static site

Refactored against the SurfaceWare Spatial Layout Schema. All interactive
targets sit inside the centred primary interaction zone (1280 × 440 design px,
40 px padding, ≥80 px targets, -50 px parallax offset); headers, hero copy,
readers, countdown, ticker and floor anchors are display-only.

## Run

Serve this folder over HTTP (any static host or local server):

    python3 -m http.server 8000

Then open http://localhost:8000/ — index.html forwards to the Welcome screen.

Opening `index.html` straight off the filesystem also works in most browsers,
but a server is recommended so the local assets resolve consistently.

## Screens

| File | Purpose |
| --- | --- |
| `index.html` | Entry point, forwards to Welcome |
| `SMU Welcome (SurfaceWare).dc.html` | Root menu — two dwell-to-enter cards |
| `SMU Lyle Kiosk (SurfaceWare).dc.html` | News · Events · Leadership · Research |
| `SMU Athletics (SurfaceWare).dc.html` | Schedule · Team · Gameday · 2025 · Tickets |

## Interaction

- **Dwell 350 ms** on any card commits the selection; a green progress bar
  shows the countdown so a passing hand never triggers navigation.
- **Back · Menu · Fwd** cluster (88 px circular targets) walks a 24-step
  history of section and item selections; Menu returns to the Welcome screen.
- Zone guides (dashed green overlays) are toggleable per screen and are
  intended for calibration, not production display.

## Files

- `support.js` — component runtime, required by all three screens
- `assets/` — player, leadership and QR imagery extracted from the source app

Fonts load from Google Fonts, so the kiosk needs network access on first paint;
cache them locally if the installation runs offline.
