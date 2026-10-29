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

It cannot move while your flashlight is on it. It freezes mid-step, mid-pose. But your flashlight flickers when it's close or when you stare too long, and in every dark flicker it moves.

## How it thinks

It's always somewhere in the maze. Nothing teleports. It builds a belief about where you are:

- **Sight:** your flashlight gives you away to anything with line of sight. In the dark it only sees you up close.
- **Sound:** running is loud, walking is quieter, crouching is nearly silent.
- **Memory:** it learns your habits (turn direction, whether you check behind you, how long you stare, whether you hide in the dark) and saves them in your browser.

Several times a second it scores its options and commits to the best one:

- **Search:** walks upright, head sweeping, checking the places you spend the most time.
- **Hunt:** heads for where you're going, not just where you are, and creeps slowly for the last few meters.
- **Flank:** slips behind walls and circles to your blind side.
- **Ambush:** reads which way you're walking, waits at a corner ahead of you, and peeks out.
- **Lurk:** stands perfectly still in the dark at the edge of your view for you to find.
- **Back off:** if it has been on top of you too long, it retreats for a while, then comes back.

Stare at it too long and it forces a burst of flickers and bolts for the nearest cover.

## The map

Press M for Wanderer 7's pencil map. The game keeps running while you read it. It shows the walls you've seen, your trail, every spot where you saw the monster (with how long ago), and a circle where the next note probably is.

## When it catches you

Your view whips around to face it. It rises, tilts its head and closes its hands around your face. It snaps forward, you drop to your knees, then hit the floor with it hanging over you, and the light dies.

## The ending

Open the EXIT door and a short film plays. You stumble out into a rainy parking lot under one orange street lamp as the door swings shut behind you. Then it's three weeks later: the tape rewinds and plays back the last seconds, filmed from the camcorder hanging at your side. A long pale hand slides out and stops the door from closing. Pause. One frame forward. It's in the doorway, smiling at the camera. Press E or tap to skip.

## Controls

| Action | Keys |
| --- | --- |
| Move / run / crouch | W A S D / Shift / C |
| Look | Mouse (click to lock), drag on a touchscreen, or arrow keys |
| Read a note / open the door | E |
| Flashlight on/off | F |
| Map (game keeps running) | M |

## Play

Open `index.html` through a web server. GitHub Pages works (Settings → Pages → deploy from `main`). Opening the file directly from disk blocks the model from loading.

```
python3 -m http.server
```

Then open http://localhost:8000.

## Files

- `index.html`: the whole game (Three.js r160 from a CDN, no build step)
- `smily_horror_monster.glb`: the monster's model and skeleton
