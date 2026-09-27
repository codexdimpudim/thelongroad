# The Long Road

A browser-based procedural road-driving prototype built with Three.js. The current build includes streamed terrain, seasonal biomes, a city biome, self-driving, a Ford Bronco player vehicle, and AI traffic.

## Run locally

Serve the folder over HTTP (do not open `index.html` as `file://`):

```bash
python3 -m http.server 8000
```

Then open `http://localhost:8000`.

## Required local assets

Place these files in `assets/`:

- `2021_ford_bronco_wildtrak.glb`
- `traffic_car_pack.glb`

The code intentionally keeps large binary GLBs separate from `index.html`, which makes source control and debugging much easier.

## Controls

- W / Up: accelerate
- S / Down: brake
- A / D: steer
- Space: handbrake
- T: toggle Self Drive
- B: next biome
- C: change camera
- R: reset

## Current vehicle fixes

- Bronco uses its native +Z forward orientation; the previous extra 180-degree rotation was removed.
- Traffic car #1 no longer captures the wheels from every vehicle in the pack.
- Each traffic model is normalized independently to a realistic vehicle length.
- Traffic positions use the same road tangent/normal math as the rendered road ribbon, keeping lane centers on asphalt through curves.
- Traffic pitch follows road elevation rather than adjacent terrain.

## Asset attribution

**2021 Ford Bronco Wildtrak** — David_Holiday / Sketchfab, CC BY 4.0.  
Source: https://sketchfab.com/3d-models/2021-ford-bronco-wildtrak-0876db48ce354f3a81f6cbd307b0324e

**Traffic Car Pack** — JUSTGAME / Sketchfab, CC BY 4.0.  
Source: https://sketchfab.com/3d-models/traffic-car-pack-916a8b149ae24d8b8c9cf12d4a1c64d4

## Project note

The terrain/road architecture was reconstructed as a clean implementation inspired by observed behavior from an old Slow Roads build; the project does not copy its minified implementation.
