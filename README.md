# Reverse Invaders

A 90s-style 2D pixel space shooter with the roles **reversed**: *you* command the alien
horde, while a CPU-piloted defender ship dodges and fights back. Your goal is to destroy
the lone defender before your fleet is wiped out.

Built as a single self-contained HTML file — HTML5 canvas, no dependencies, no build step.

> 🤖 This project was **vibecoded** with almost a single prompt.

## Play

🎮 **Play it now in your browser:** [reverse-invaders.tiiny.site](https://reverse-invaders.tiiny.site)

Or open `index.html` in any modern browser:

```
# either open the file directly...
xdg-open index.html        # Linux
open index.html            # macOS

# ...or serve it locally
python3 -m http.server 8173
# then visit http://127.0.0.1:8173/index.html
```

Press **ENTER** on the title screen to begin.

## Controls

| Key            | Action                                            |
| -------------- | ------------------------------------------------- |
| **W A S D** / arrows | Steer the entire swarm as one block         |
| **SPACE**      | Fire a volley (every living alien shoots at once) |
| **P**          | Pause / resume                                    |
| **M**          | Mute / unmute sound                               |
| **ENTER**      | Start / restart                                   |

## How it works

- **You are the horde.** You steer the whole alien formation together and unleash volleys.
- **The defender is CPU-controlled.** It actively dodges incoming bolts, hunts your lowest
  aliens, and shoots back when aligned.
- **Win:** drain the defender's HP bar to zero.
- **Lose:** your entire fleet is destroyed with no reserves left to deploy.
- Aliens arrive in **waves** drawn from a shared fleet pool. The defender's HP **persists
  across waves**, so you chip it down over time.
- **Kamikaze tactic:** drive the swarm straight down into the ship — ramming deals heavy
  damage but costs you the ship.

The HUD shows defender HP, remaining fleet, current wave, and score.

## Look & feel

- Internal 320×240 resolution scaled up with nearest-neighbor for chunky pixels
- CRT scanline + vignette overlay, parallax starfield
- Hand-drawn pixel sprites (three alien types + the defender)
- Particle explosions, screen shake, hit flashes
- Tiny WebAudio square-wave blip synth for shots and explosions

## Tuning

Balance constants live near the top of the `<script>` block in `index.html`:
`HERO_MAX_HP`, `HERO_SPEED`, `HORDE_SPEED`, `VOLLEY_CD`, `ALIEN_BULLET_DMG`, `RAM_DMG`,
`FLEET_RESERVE_START`, and the formation size — tweak them to adjust difficulty.
