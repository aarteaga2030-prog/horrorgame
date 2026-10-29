# NOCLIP

A first-person found-footage horror game in a Backrooms-style maze, built with Three.js.

You leaned on a wall and fell through it. Now it's damp carpet, yellow wallpaper and dead lights. It's pitch black, and your flashlight is the only light. The camcorder is still recording. Someone was here before you and left five notes on the walls. Find them, then find the exit. A six-foot thing with a permanent grin walks the halls.

## The monster

It uses `smily_horror_monster.glb`, scaled to stand 6 feet tall. Every movement is procedural: the game drives the model's bones with inverse kinematics instead of playing canned animations.

- **Walks wrong:** hunched over, one leg dragging, with stop-motion stutters and sudden head twitches.
- **Drags a hand along the wall** when it walks near one.
- **Peeks around corners:** it grips the wall edge with both hands and leans its sideways-tilted head out. If you watch it too long, it either snaps back or steps out, raises its arms, screams and charges.
- **Stands and stares** fully upright at the end of a hall. Look away and it's closer.
- **Crosses a hallway** in the distance, stops, and turns its head to look at you.
- **Chases on all fours**, with each hand and foot planting on the floor.
- **Grabs your face** if it catches you.

## The rule

It cannot move while your flashlight is on it. It freezes mid-step, mid-pose. But your flashlight flickers when it's close, and in every dark flicker it lurches toward you. The closer it gets, the more the light flickers.

## How to survive

- Keep the beam on it and back away.
- It's smart. It uses the flickers to dart behind walls, then circles around to come at you from the side or behind. Listen for it.
- It switches between walking upright and crawling every few seconds, even while frozen, so each flicker can show it in a new pose.
- Don't stare too long. Hold the beam on it and the light starts flickering harder. Then it bolts for the nearest cover and comes around another way.
- It learns your habits: which way you usually turn, whether you check behind you, and how long you stare. Then it comes from your blind side. It remembers you between games (saved in your browser), and the death screen tells you what it has learned.
- Look away and it comes fast. If it's been out of sight too long, it gets behind you.
- Turning the light off (F) lets it move freely.
- Your map (M) shows where you've been, and the exit once all five notes are found.
- If it catches you, rewind the tape. You keep your notes.

## Controls

| Action | Keys |
| --- | --- |
| Move / run / crouch | W A S D / Shift / C |
| Look | Mouse (click to lock), drag on a touchscreen, or arrow keys |
| Read a note / open the door | E |
| Flashlight on/off | F |
| Map | M |

## Play

Open `index.html` through a web server. GitHub Pages works (Settings → Pages → deploy from `main`). Opening the file directly from disk blocks the model from loading.

```
python3 -m http.server
```

Then open http://localhost:8000.

## Files

- `index.html`: the whole game (Three.js r160 from a CDN, no build step)
- `smily_horror_monster.glb`: the monster's model and skeleton
