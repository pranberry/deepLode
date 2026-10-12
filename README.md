# Deep Lode

A Motherload-style mining game in a single HTML file. Dig into a planet, haul ore to the surface, sell it, upgrade your pod, fill contracts, recover buried relics, defeat the Molten Heart at the bottom of the mine, and launch to harder planets.

## Build

There is no build step. The whole game (HTML, CSS, and JavaScript) lives in `index.html`, with no dependencies to install.

The only external resource is two Google Fonts. Offline, the game still runs and falls back to system fonts.

## Run

### Option 1: open the file

Double-click `index.html`, or drag it into any modern browser (Chrome, Firefox, Safari, Edge).

On macOS you can also run:

```bash
open index.html
```

### Option 2: serve it locally

Use this if your browser restricts `localStorage` or file downloads for pages opened from disk.

With Python:

```bash
python3 -m http.server 8000
```

With Node:

```bash
npx serve .
```

Then visit http://localhost:8000 (or the URL `serve` prints).

## Controls

| Key | Action |
| --- | --- |
| `←` `→` / `A` `D` | Drive; push into a wall to dig sideways |
| `↓` / `S` | Dig down |
| `↑` / `W` / `Space` | Thrust upward |
| `1` | Repair kit |
| `2` | Reserve fuel |
| `3` | Dynamite |
| `4` | Teleport to surface |
| `Esc` | Open the pause menu (save/load, sound, new game); close any open menu or shop |
| `Space` / `Enter` | Select in menus |
| Arrow keys | Move between menu buttons |

Every menu also has a **×** button in its top-right corner, and clicking outside a menu closes it too. Closing the title screen drops you straight into the game, continuing your save if you have one. Closing the "Pod lost" screen rebuilds the pod.

On touch screens, on-screen buttons appear automatically.

## Saving

- **Autosave:** progress saves to the browser's `localStorage` every few seconds and whenever you leave a shop. It belongs to that browser and that address, so a save made from `file://` is separate from one made on `localhost`.
- **Save files:** open the menu (`Esc`) and choose **Save to file**. You get a JSON file such as `deep-lode_p1_2026-10-12_1430_850ft.json`. To restore it, choose **Load from file** in the menu, or **Load save file** on the title screen. Save files work across browsers and machines.

## Gameplay overview

- **Surface buildings:** Fuel Depot, Mineral Processor (sell ore and see contracts), Upgrade Bay (pod upgrades and supplies, in quantities of 1, 10, or 100), and Repair Shop. Drive onto a building's pad to enter it.
- **Hazards:**
  - Boulders can't be drilled; clear them with dynamite. They fall when you dig out from under them.
  - Gas pockets look like dirt and explode when dug.
  - Lava does heavy damage.
  - Long falls hurt the hull.
  - Fuel burns faster in the hot depths.
- **Rock crawlers:** they appear below about 560 ft and tunnel toward you. Drill or blast them for a bounty.
- **Contracts:** three jobs are always open: deliver ore, reach a depth, or destroy crawlers.
- **Relics:** 12 buried chests between about 375 ft and 6,000 ft. The last one is the Core Key.
- **The vault:** a sealed chamber at about 6,300 ft. The Core Key opens it, and the Molten Heart waits inside; dynamite is the main way to damage it.
- **Planets:** after beating the Heart you can launch to the next planet. You keep your upgrades and cash. Ore is worth more, hazards hit harder, and each of the first two launches opens a new upgrade tier.

## Project layout

```
index.html   the entire game
README.md    this file
```
