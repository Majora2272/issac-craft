[README.md](https://github.com/user-attachments/files/33043842/README.md)
# IsaacCraft — Basement I

A Minecraft Java 1.21.4 prototype inspired by The Binding of Isaac. You descend through room-based floors while keeping Minecraft's mining, crafting, building and destruction.

## What players get

- One procedurally assembled floor per run: entrance, three combat rooms, treasure room, bomb-secret room and a Monstro boss room. The connected room tree changes on every restart, while room shapes remain authored Minecraft spaces.
- First-person tears, bombs and nine individual collectibles: Blood Clot, Sad Onion, Breakfast, Halo, Wooden Spoon, Boom!, 20/20, Cupid's Arrow and Common Cold. Their Minecraft effects are adapted: damage, fire rate, health, armour, speed, bombs, double shot, piercing and poison. Effects last the run; inventory icons are keepsakes, not equipment requirements.
- Up to four players by design, on the same home network. Every participating player receives an individual random room-clear reward. Extra players are spectators.
- Minecraft mining, block placement, crafting and explosions. The outer boundaries preserve room progression; a bomb at the marked cracked wall opens the hidden passage.
- Fallen players spectate until the current room clears. A team wipe starts a fresh run.
- Gapers chase, spiders pursue and climb, Clotties fire four-way volleys, and Monstro has a telegraphed stomp plus eight-way volleys. These are Minecraft adaptations, not exact Isaac AI.
- Run restart: `/trigger ic.restart`.

## Controls

WASD and mouse as in Minecraft. Slot 1: tears, hold right click. Slot 2: bomb, right click and move away. Slot 3: pickaxe. Slot 4: sword. Mining, placing blocks and crafting use Minecraft's normal controls. Bomb charges and upgrade stats appear above the hotbar.

## Requirements

Requires an owned copy of **Minecraft: Java Edition 1.21.4** and Java 21. The installed local test instance is **IsaacCraft - Basement Lab (1.21.4)** in Prism. No mod loader is used. The distributable fallback build does not require or launch Isaac and includes no Isaac assets or game binaries. The installed private art pack additionally requires the owner's Isaac files; it supplies collectible art and static camera-facing enemy sprites over Minecraft hitboxes.

The distributable prototype requires an owned copy of Minecraft: Java Edition 1.21.4 or newer in the supported range. The regular package uses Minecraft-compatible placeholder textures. The Isaac-art prototype archive includes converted Isaac sprites for testing.

The Isaac-art archive is a fan prototype. It contains converted sprites supplied for this project and does not include the Isaac game executable or raw game installation files.

## Melty installation

Upload the repository contents to GitHub, then point Melty at the repository. Melty uses `melty.json` to install the world into the Minecraft instance saves folder. Choose Minecraft Java Edition 1.21.4 or newer when prompted, then press Play and open the `IsaacCraft | Basement I` world.

The recipe has been checked by Melty as one-click installable. Melty Test still needs to be run on the listing before calling the release fully verified.

LAN hosting/joining has not been validated with two player copies. Do not assume internet co-op, Melty join links, automatic LAN hosting or one-click installation work. The user currently has no second testing computer available.

## Testing status

The official 1.21.4 server parsed the generated pack. Live single-player checks verified open corridors, breakable interiors, boundary protection, base and upgraded tear damage, right-click firing, room clear, player reward, bomb charge consumption, secret passage opening, boss health and floor-completion state. See `gameplay-test-log.txt`. Some tests used frozen enemies and temporary player protection: these verify behavior, not difficulty or balance. Test helpers are not included in the release packs.

The procedural expansion also passed generated-room/edge counts over eight resets, moving secret-door opening, attached boss sprite and Clotty volley checks in the official server. Live client checks confirmed piercing, poison application/ticks and double shots. See `expansion-test-results.json` and `expansion-gameplay-test-log.txt` for final results.

The official Minecraft 1.21.4 server and the real Prism client passed the procedural dungeon, secret-room, collectible, enemy, combat, reward and boss checks. Eight generated layouts were checked, and the real client displayed Gapers, spiders, Clotties and Monstro. See `expansion-gameplay-test-log.txt` and `expansion-test-results.json`.

The following remain prototype limitations: uninterrupted balance testing, revival with multiple players, and a two-player LAN join test. Do not assume internet multiplayer. Melty Test is still required before publication.

## Source

JSON tables in `sheets/` are the design inputs. `python build.py --preflight` checks filled/typed cells and cross-table references. `python build.py` repeats preflight, generates runtime records/functions and packages the datapack and resource pack. `preflight.json` records design/schema checks; it explicitly does not certify gameplay verification.

## Credits and permissions

Design direction: the creator in this chat. Implementation assisted by Codex. Minecraft is by Mojang/Microsoft; The Binding of Isaac is by its respective creators. This is an unofficial fan project. Confirm the project's code license and remix permission on the Melty listing before publishing.

Development tools: universal-modder (MIT), Prism Launcher (GPL-3.0), Eclipse Temurin/OpenJDK (GPL-2.0 with Classpath Exception), Python and its development libraries. These tools are local development dependencies and are not bundled in the world archive.

### Optional local Isaac art
A private art experiment now uses sprites and backdrop samples from the owner's Isaac installation. `local-art.json` defines conversions and `make_local_art.py` builds the local pack from already extracted resources. The extracted images and resulting pack are not included in these project/release files. The public development world still uses Minecraft textures. Melty installation support for generating owner-supplied Isaac art is not yet verified. Do not redistribute the private pack.
