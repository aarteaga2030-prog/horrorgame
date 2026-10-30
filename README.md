# NOCLIP

A first-person found-footage horror game in a Backrooms-style maze, built with Three.js.

You leaned on a wall and fell through it. Now it's damp carpet, yellow wallpaper and dead lights. It's pitch black, and your flashlight is the only light. The camcorder is still recording. Someone was here before you and left five notes on the walls. Find them, then find the exit. A six-foot thing with a permanent grin walks the halls.

## The monster

It uses `smily_horror_monster.glb`, scaled to stand 2.35 m (about 7'8") tall. It hunches to squeeze through doorways. Every movement is procedural: the game drives the model's bones with inverse kinematics instead of playing canned animations.

- **Walks wrong:** hunched over, one leg dragging, with stop-motion stutters and sudden head twitches.
- **Drags a hand along the wall** when it walks near one.
- **Peeks around corners:** it grips the wall edge with both hands and leans its sideways-tilted head out. If you watch it too long, it either snaps back or steps out, raises its arms, screams and charges.
- **Stands and stares** fully upright at the end of a hall. Look away and it's closer.
- **Crosses a hallway** in the distance, stops, and turns its head to look at you.
- **Chases on all fours**, with each hand and foot planting on the floor.
- **Grabs your face** if it catches you.

## The intro

You carry the last box down the basement stairs, lean on the wall, and fall through it. You drop through the ceiling of somewhere else and land on damp carpet under humming lights. Then the lights die one by one, far to near. The box you were carrying lands next to you, torn open, with your camcorder inside. You kneel, reach in with both hands and pick it up, and its little screen flickers on. In the last of the light, something is standing at the end of the hall. Your camera light clicks on and the hall is empty. Press E or tap to skip.

## The level

A new 32×32 maze every tape: yellow wallpaper with uneven wear, doorways cut into the walls, pillar halls, long corridors, missing and fallen ceiling tiles, outlets, vents, damp stains and abandoned office chairs.

## Harder

- **Battery:** your flashlight drains its battery, and it flickers more and dims when low. Seven spare camcorder batteries are hidden around the level (look for a tiny green LED).
- **Three tapes:** each death costs one. Lose all three and the tape is erased, and you start over in a new maze.
- **Tuning:** the monster is faster, backs off less often, and gets more aggressive with every note, every death and every minute.

## The rule

It cannot move while your flashlight is on it. It freezes mid-step, mid-pose. But your flashlight flickers when it's close or when you stare too long, and in every dark flicker it moves.

## How it thinks

It's always somewhere in the maze. Nothing teleports. It builds a belief about where you are:

- **Sight:** your flashlight gives you away to anything with line of sight. In the dark it only sees you up close.
- **Sound:** running is loud, walking is quieter, crouching is nearly silent.
- **Memory:** it learns your habits (turn direction, whether you check behind you, how long you stare, whether you hide in the dark) and saves them in your browser.

Several times a second it scores its options and commits to the best one. Its paths avoid your flashlight beam and line of sight, so it moves through the dark:

- **Search:** walks upright, head sweeping, checking the places you spend the most time.
- **Hunt:** heads for where you're going, not just where you are, and creeps slowly for the last few meters.
- **Flank:** slips behind walls and circles to your blind side.
- **Ambush:** reads which way you're walking, waits at a corner ahead of you, and peeks out.
- **Lurk:** stands perfectly still in the dark at the edge of your view for you to find.
- **Guard:** it knows what you're looking for. It works out your route to the next note or the exit, then waits at a doorway or narrow corridor along the way.
- **Decoy:** it copies your own footsteps on the far side of you, then comes in silently from the other side.
- **Intercept:** when you sprint, it predicts your route through the maze and heads for a point ahead of you.
- **Wait:** if you hide (standing still, crouched or in the dark), it creeps close, goes completely silent, and waits for you to move.
- **Herd:** it finds dead ends near you and comes at you from the other side, so you run into them.
- **Back off:** if it has been on top of you too long, it retreats for a while, then comes back.

Stare at it too long and it forces a burst of flickers and bolts for the nearest cover.

## How it learns

**It learns which tactics work on you.** Every catch, near miss and escape is credited to the tactic it was using. It also checks whether you turned toward its decoy footsteps. It picks tactics that have worked on you more often, and drops the ones you beat. This is saved in your browser and shown on the death screen. It also remembers where you hid this run, and checks those spots first.

**It was trained by self-play.** Bot players (one careful, one that sprints everywhere, one that wanders) played thousands of matches against it. A search process tuned its numbers (how it weighs each tactic, how fast it moves, how often your light flickers, how soon it bolts when stared at) to catch players as effectively as possible while a careful player still survives about a third of the time. To run the harness yourself, open `index.html#debug` and call `__runSim({}, 'careful', 120)` from the console.

## Your arms

You see your own gloved arms (`fps_arms.glb`), posed live every frame with the same IK system as the monster:

- **Camcorder:** a real camcorder model (`camcorder.glb`) held in your right hand, fingers wrapped around its side. Its flip-out screen shows a live mini feed of what the camera sees, with a REC dot, timecode and battery level. If you walk up against a wall it pulls back toward you instead of poking through.
- **Bob:** your hands and your view bob and sway as you walk, harder when you sprint, and lag a little behind when you turn.
- **Left hand:** hangs low while walking, pumps as a fist when you sprint, and pulls in when you crouch.
- **Pickups:** you step in and reach for notes (you hold each one up to read it) and kneel for batteries, which you snap into the camcorder.
- **Panic:** when the light flickers with the monster nearby, it sometimes smacks the camcorder.
- **The map (M):** you hold the paper up in your left hand. It's a real object in front of you, lit by your light, and the game keeps running.
- **The kill:** both hands come up to shield your face, get shoved aside, and the camcorder falls.
- **Intro and ending:** you carry the box down the stairs, reach for the wall that isn't there, flail as you fall, and push the exit door open at the end.

## The map

Press M to hold up Wanderer 7's pencil map. The game keeps running while you read it. It shows the walls you've seen, your trail, every spot where you saw the monster (with how long ago), and a circle where the next note probably is.

## When it catches you

Your view whips around to face it. It rises, tilts its head and closes its hands around your face. It snaps forward, you drop to your knees, then hit the floor with it hanging over you, and the light dies.

## The ending

Open the EXIT door and a short film plays. You stumble out into a rainy parking lot under one orange street lamp as the door swings shut behind you. Then it's three weeks later: the tape rewinds and plays back the last seconds, filmed from the camcorder hanging at your side. A long pale hand slides out and stops the door from closing. Pause. One frame forward. It's in the doorway, smiling at the camera. Press E or tap to skip.

## Controls

| Action | Keys |
| --- | --- |
| Move / sprint / crouch | W A S D / Shift / C |
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
- `fps_arms.glb`: your arms
- `camcorder.glb`: the camcorder

## Credits

- Monster: "Smily horror monster" (CC BY 4.0), from Sketchfab.
- Arms: "fps arms" (CC BY 4.0), from Sketchfab.
- Camcorder: "Camcorder" by omegadarling (CC BY 4.0), from Sketchfab.
