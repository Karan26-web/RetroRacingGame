# Flat Track GP

*A flat picture, tilted into a road.*

A retro racer drawn the way 16-bit consoles faked 3D: the whole circuit is one flat 1024 × 1024 picture, and every line of the screen shows it at a different scale. Big at the bottom, tiny at the horizon, and it reads as a road.

Three laps against five rivals on a lake circuit at sunset.

## Play

Open `index.html` in a browser. That is the whole game: one file, no assets, no dependencies, no build.

| | Keyboard | Touch |
|---|---|---|
| Steer | ← → or A D | ◀ ▶ |
| Gas | ↑ or W | GAS |
| Brake / reverse | ↓, S or Space | BRAKE |
| Pause | P or Esc | |
| Restart | R | |
| Sound | M | |

On the title screen, ← → picks a kart and Enter starts. Hit the gas as the third light comes on for a rocket start.

## What is in it

- **The road:** per-scanline scaling of a track picture that is itself painted in code at load (asphalt, kerbs, start grid, lake, sand, bushes, boost pads), with mip levels so the distance does not shimmer.
- **Karts:** a small 3D model rasterised with a z-buffer into pixel-art sprite sheets at 48 angles, six liveries, so karts turn properly through corners. Brake lights when they brake.
- **Upright scenery:** pine trees, bumpers, a chequered start gantry and a tiled grandstand, depth-sorted with the karts.
- **Racing:** grass, sand and water slow you; bumpers and trees are solid; karts collide; two boost pads; rivals that brake for corners and move over to pass; wandering too far puts you back on the track.
- **Sky:** a sunset panorama that scrolls with your heading.
- **Sound:** a synthesised engine, effects and a chiptune loop.
- Position, lap, time, speed and a live minimap; your lap record is kept in the browser.

It fills the window in landscape and keeps the tall phone layout in portrait.

## Notes for development

`index.html#sim=20` starts a race with the autopilot at the wheel, steps the simulation 20 seconds and draws one frame (add `,title` to do the same on the title screen). After a simulated race the page title carries each kart's lap count and best lap. This is how the game was checked in headless Chrome.

The look was matched to a reference video, which is kept out of the repository (it is 237 MB).
