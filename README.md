# The Long Road

A browser-based procedural road-driving prototype built with Three.js.

## Current milestone: driving foundation

The active local build now focuses on driving before city/airport expansion:

- Ford Bronco stock vehicle at realistic overall scale and native forward orientation.
- Signed-speed arcade-realistic driving model with forward, braking, reverse, drag, handbrake, speed-sensitive steering, and a bicycle-style yaw model.
- Body pitch/roll response and smoother chase/interior cameras.
- Self Drive follows the right-hand lane and automatically reduces speed for bends.
- Traffic now uses the selected free low-poly car pack rather than the previous traffic pack.
- 12 traffic models are normalized independently to believable lengths, placed from the road tangent/normal, and spawned in both directions.
- Basic traffic spacing logic slows cars behind other vehicles.
- Visible asset loading status replaces silent model failures.

The next step is testing/tuning this milestone on the target machine before adding more scenery systems.

## Run locally

Serve the folder over HTTP:

```bash
python3 -m http.server 8000
```

Then open `http://localhost:8000`.

The packaged Mac build also includes `START.command` to start a local server and open the game.

## Vehicle asset layout

```text
assets/
  2021_ford_bronco_wildtrak.glb
  traffic/
    armor.glb
    coupe.glb
    fenyr.glb
    ghini.glb
    italia.glb
    jeep.glb
    kamaro.glb
    lamb.glb
    mobil.glb
    police.glb
    rally.glb
    van.glb
```

## Controls

- W / Up: accelerate
- S / Down: brake / reverse
- A / D: steer
- Space: handbrake
- T: toggle Self Drive
- B: next biome
- C: change camera
- R: reset to road

## Selected asset stack

For upcoming work we have selected:

- Downtown City MegaKit — city/building pieces
- Kenney City Kit: Roads — intersections and street infrastructure
- Free low-poly car pack — traffic
- Kenney Input Prompts — HUD/control prompts

Only the traffic pack is being integrated during the driving milestone.

## Project note

The terrain/road architecture is a clean implementation inspired by observed behavior from an old Slow Roads build; the project does not copy its minified implementation.
