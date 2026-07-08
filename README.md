# Whiteout Protocol ⚪

A top-down extraction shooter in a single HTML file. The machines took the
valley — drop in as a blank white silhouette, scavenge salvage, and get out.

All art is original and drawn in code (canvas shapes only): a minimalist white
figure on a flat sunlit meadow, hunted by geometric machines. Inspired by the
*mood* of extraction shooters, with zero borrowed assets.

## How to play

Open `index.html` in a browser (or serve the folder with
`python3 -m http.server`).

- **Goal:** collect **5 salvage crates**, then stand on the **extraction pad**
  for 4 seconds. The pad lands somewhere new every run — follow the minimap.
  Reaching it triggers one last swarm — survive it.
- **Loot the structures:** several **decayed houses** (rotting wooden homes and
  burned-out brick cottages) and **abandoned vehicles** (rusted sedans and
  pickup trucks) spawn at random spots across the valley each run. The crates
  inside hold **scrap, gears and cloth**, tallied in your HUD and on the end
  screen.
- **Gun up:** you land with a pistol. Sealed **weapon crates** (blue dots on
  the minimap) each hold a random gun — SMG, shotgun, rifle, or the
  one-shot-one-kill sniper. They're only found at structures: one inside every
  house, plus a couple stashed beside cars. Walk over one to equip it.
- **Craft your edge:** press **TAB** to open your gear menu — a materials tab
  with counters for everything you've scavenged, and a crafting tab. The world
  freezes while you tinker.

  | Recipe | Cost | Effect |
  |--------|------|--------|
  | Medkit | 3 cloth | +50 HP |
  | Shield plate | 4 scrap | +50 shield (soaks damage before HP) |
  | Gun tune-up | 3 gears + 2 scrap | +20% weapon damage, stacks to +100% |
  | Field cleats | 2 cloth + 2 gears | +10% move speed, stacks to +30% |

- **WASD / arrows** — move
- **Mouse** — aim, **click / hold** — shoot
- **R** — reload · **Shift** — sprint (stamina bar)
- **TAB** — gear & crafting · **P** — pause · **M** — mute

**On iPad / iPhone / any touch screen:** left thumbstick moves (push it all the
way to sprint), right thumbstick aims and fires. GEAR and PAUSE buttons sit in
the top-right corner. Reloads are automatic.

### Arsenal

| Weapon | Damage | Mag | Notes |
|--------|--------|-----|-------|
| Pistol | 12 | 12 | What you land with |
| SMG | 8 | 28 | Fast, sprays |
| Shotgun | 7×6 | 6 | Six pellets, brutal up close |
| Rifle | 16 | 20 | Accurate all-rounder |
| Sniper | 50 | 5 | Deletes a ticker per shot |

## The lobby (meta-progression)

Extract successfully and you land in the **Extraction Lobby**: your silhouette
(in its current skin) on display, your banked haul, and four tabs. Progress
saves automatically between sessions.

- **CRAFT** — spend banked materials on next-run gear: field medkits
  (auto-heal when low), a shield plate, gun tune-ups, field cleats. The
  loadout is consumed when you deploy.
- **SELL** — turn materials into money (scrap $2 · gears $5 · cloth $3).
  Extracting also pays a per-map reward. Die in the field and your carried
  materials are lost.
- **SKINS** — 6 skins for your silhouette: Whiteout (free), Crimson $50,
  Toxin $100, Azure $150, Golden $200, Void $300.
- **MAPS** — unlock harder drops, in order:

  | Map | Price | Machines | Salvage needed | Reward |
  |-----|-------|----------|----------------|--------|
  | The Valley | free | 17 | 5 | $40 |
  | Rust Flats | $120 | 27 | 6 | $90 |
  | Ashfall | $300 | 38 | 7 | $170 |
  | Blackout Zone | $650 | 52 | 8 | $300 |

  Harder maps have faster, harder-hitting machines and different terrain.

The big **▶ PLAY** button in the corner opens map choice — pick your drop and
you're in.

## The machines

| Machine | Behavior |
|---------|----------|
| **Ticker** | Small six-legged crawler. Swarms and bites at close range. |
| **Wasp** | Flying drone. Keeps its distance and fires 3-round bursts. Ignores walls. |
| **Strider** | Heavy tripod guarding the extraction pad. Slow, tanky, hits hard. |

Machines wander until they spot you (or hear gunfire nearby). Destroyed
crawlers and striders sometimes drop a **medkit** (+25 HP). Health slowly
regenerates if you avoid damage for a few seconds.

## Tech

- Single-file HTML5 canvas game, no dependencies, no external assets
- Procedurally generated map each run (rocks, ruined walls, tree groves you
  can walk under, dirt road, crates)
- WebAudio synthesized sound effects
- Best extraction time saved locally (safe when localStorage is blocked)
