# NOCLIP

A first-person found-footage horror game in a Backrooms-style maze, built with Three.js.

You leaned on a wall and fell through it. Now it's damp carpet, yellow wallpaper and the hum of fluorescent lights, forever. The camcorder is still recording. Someone was here before you and left five notes on the walls. Find them, then find the exit. A six-foot thing with a permanent grin walks the halls.

## The monster

It uses `smily_horror_monster.glb`, scaled to stand 6 feet tall. Every movement is procedural: the game drives the model's bones with inverse kinematics instead of playing canned animations.

- **Walks wrong:** hunched over, one leg dragging, with stop-motion stutters and sudden head twitches.
- **Drags a hand along the wall** when it walks near one.
- **Peeks around corners:** it grips the wall edge with both hands and leans its sideways-tilted head out. If you watch it too long, it either snaps back or steps out, raises its arms, screams and charges.
- **Stands and stares** fully upright at the end of a hall. Look away and it's closer.
- **Crosses a hallway** in the distance, stops, and turns its head to look at you.
- **Chases on all fours**, with each hand and foot planting on the floor.
- **Grabs your face** if it catches you.

## How to survive

- It loses you when it can't see or hear you. Break line of sight at corners, then crouch.
- Running is loud. Walking near it is loud too.
- Some areas have dead lights. Your camera light (F) helps you see, but the lights flicker when it's close.
- Your map (M) shows where you've been, and the exit once all five notes are found.
- If it catches you, rewind the tape. You keep your notes.

## Controls

| Action | Keys |
| --- | --- |
| Move / run / crouch | W A S D / Shift / C |
| Look | Mouse (click to lock), drag on a touchscreen, or arrow keys |
| Read a note / open the door | E |
| Camera light | F |
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
