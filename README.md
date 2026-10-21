# ECLIPSE: Cursed Land

A 2.5D dark fantasy action game in a single self-contained `index.html`
(Canvas 2D, no dependencies, no build step, no network calls).
Cross the Hollow March, hunt the lost, and face the Hollow Warden.

## Play

Open `index.html` in any modern browser, or serve the folder statically
(e.g. GitHub Pages). Landscape orientation recommended on mobile.

## Heroes

| Hero | HP | DMG | Style | Skill |
| --- | --- | --- | --- | --- |
| The Wanderer | 100 | 24 | Agile melee, curved saber | MOONCUT — frontal shock slash |
| Ashen Witch | 82 | 17 | Ranged spell orbs with trails | SOULFLARE — wide area burst |
| Dread Knight | 135 | 34 | Heavy greatsword + shield | GRAVEWAVE — heavy frontal wave |

## Enemies & boss

- **Husk** — shambling melee; telegraphs its strike before dealing damage.
- **Wraith** — floating caster; keeps its distance and fires soul orbs.
- **Brute** — armored heavy; slow overhead slam with a ground telegraph ring.
- **The Hollow Warden** (boss, after 6 kills) — telegraphed sword slam,
  soul-orb volley, and an enraged phase 2 below 50% HP.

## Controls

**Keyboard**

- Move: `A` / `D` or `←` / `→`
- Jump: `W`, `↑` or `Space`
- Attack: `J`
- Skill: `K`
- Potion: `L` (3 potions, +38 HP)
- Pause: `Esc` or `P`

**Touch**

- Left virtual joystick to move.
- Right button cluster: ATTACK (large), SKILL, JUMP, POTION.
- Buttons show live cooldown numbers; the skill button glows when ready.

## Technical notes

- Single file, procedural Canvas 2D art (parallax ruin/forest scenery,
  pre-rendered scenery tiles, fog sprites, pooled particles) — no external assets.
- Delta-time update loop with hit-stop and slow-motion on kills/deaths,
  DPR capped at 1.6 for mobile performance, auto-pause when the tab hides,
  `prefers-reduced-motion` disables screen shake.
- Enemy AI uses explicit state machines (chase → windup → strike → recover,
  casters use cast/recover) so every damaging attack is telegraphed and fair.

## Branches

- `main` — stable version.
- `backup/legacy-2026-10-21` — untouched snapshot of the original release.
- `feature/2.5d-visual-gameplay-upgrade` — the 2.5D visual/gameplay upgrade
  (review via pull request before merging).
