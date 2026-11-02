# NOCLIP

A first-person found-footage horror game in a Backrooms-style maze, built with Three.js.

You leaned on a wall and fell through it. Now it's damp carpet, yellow wallpaper and dead lights. It's pitch black, and your flashlight is the only light. The camcorder is still recording. Someone was here before you and left five notes on the walls. Find them, then find the exit. A six-foot thing with a permanent grin walks the halls.

The exit doesn't go out. It goes down, to level 2, where something blind hunts you by sound. Below that is level 3, a hotel built round a courtyard of windows, and the first one is out in that courtyard, taller than the building, looking in.

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

A new 32×32 maze every tape: yellow wallpaper with uneven wear, doorways cut into the walls, pillar halls, long corridors, missing and fallen ceiling tiles, outlets, vents and damp stains.

**Rooms cut from the Backrooms VR scan.** Most of each new tape's map, about 70%, is rooms cut out of `backrooms_vr.glb`. That's 35–40 rooms per tape, each turned and mirrored at random, sitting wall to wall and joined by doorways. Short stretches of maze fill the gaps between them. Arch rooms come up the most. One big room is always within a few cells of where you start. The rooms keep the scan's layout, carpet, ceiling tiles, lamps, vents, smoke detectors (with their red lights) and furniture. The lamp glow baked into the scan is taken out, so the rooms are as dark as everywhere else.

**One look everywhere.** The maze's own walls, carpet, ceiling tiles and cream skirting use the colours of the scan, and each section of the scan is evened out to the same shade. A corridor and a cut-out room look like the same place.

| Room | What's in it |
| --- | --- |
| Arch hall | A row of arched pillars and a pile of armchairs and side tables |
| Arch wing | The arched pillars along one side of a long room |
| Arch lounge | The armchair pile next to the arches |
| Short arches | A short run of arches |
| Colonnade | A narrow hall along the arches |
| Offices | An L-shaped wall block, an alcove and half-height counters |
| Counter room | The counters and the L-shaped block |
| Partition hall | A long wall with a side corridor and thin partitions |
| Side corridor | A corridor behind a long wall with doorways |
| Lounge | The armchair pile on its own (rare) |
| Alcove | A small side room |
| Partitions | A corner of short dividing walls |

The cut-out walls block you, the monster and its line of sight; the counters and the furniture block movement but not sight. They also show up in pencil on your map.

**Furniture.** Ladder-back chairs, 70s desk chairs, dressers, sofas, armchairs and low tables are scattered around. Some stand against the walls and some lie knocked over on their sides or backs. A few corners are set up like an abandoned waiting room: a sofa against the wall, a low table and two armchairs. You and the monster both collide with all of it.

## Stage select and cutscenes (start menu)

- **STAGE SELECT** jumps straight into level 0, level 2 or level 3 with fresh tapes.
- **CUTSCENES** replays any scene on its own: the basement intro, the stairwell, the freight lift, the north stair door, and the ending film. Each one goes back to the title when it ends (E or tap skips).

## Settings (start menu)

Both are off by default, and the game remembers your choice in this browser.

- **Kill cam:** when it catches you, you watch the last ~15 seconds again from above: you (blue ring and arrow, with your flashlight beam), and the monster moving exactly as it did. Press E or click to skip.
- **Pina mode:** the monster gets Mr. Pina's face (from `pina_face.jpg`), his skin tone, a black DOOM tee and dark jeans. The face is built onto a new head that follows the monster's head bone; the original head is hidden.

## How it looks

- **Surfaces:** walls, carpet and ceiling tiles get fine 3D surface detail applied in world space, so it lines up on the maze and on the scanned rooms alike. The wallpaper has paper grain and bubbles, the carpet has tufts with a soft fabric sheen at low angles, and the ceiling tiles are pitted and cracked. Recesses read darker and rougher.
- **Flashlight:** the beam has a real reflector pattern (hot centre, softer ring, faint lens smudges) and sharper shadows. A warm fill light bounces off whatever the beam hits, so the room around the spot isn't pitch black, and dust drifts through the beam.
- **Corners and contact shadows:** ambient occlusion darkens corners, skirting and the floor under furniture. A soft bloom picks out the brightest highlights.
- **The monster:** waxy, slightly wet skin with a sheen, and it shadows itself.
- **Damp patches:** soft, ragged-edged stains on the carpet.
- **Slower computers:** if the first seconds of play run slow, the game turns off the occlusion, then the bloom, and lowers the shadow detail by itself.

## Harder

- **Battery:** your flashlight drains its battery, and it flickers more and dims when low. Seven spare camcorder batteries are hidden around the level (look for a tiny green LED).
- **Three tapes:** each death costs one. Lose all three and the tape is erased, and you start over in a new maze.
- **Tuning:** the monster is faster, backs off less often, and gets more aggressive with every note, every death and every minute.

## The rule

It cannot move while your flashlight is on it. It freezes mid-step, mid-pose. But your flashlight flickers when it's close or when you stare too long, and in every dark flicker it moves.

## How it thinks

It's always somewhere in the maze. Nothing teleports. It builds a belief about where you are.

It also takes breathers: after every 30 to 50 seconds of hunting you, it pulls back somewhere out of sight for 16 to 26 seconds (10 to 15 once the exit is open) before it starts again.

What it uses to work out where you are:

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

- **Camcorder:** a real camcorder model (`camcorder.glb`) cradled in your right hand: palm under it, fingers curling up its right side through the hand strap. Its flip-out screen shows a live mini feed of what the camera sees, with a REC dot, timecode and battery level. If you walk up against a wall it pulls back toward you instead of poking through.
- **Bob:** your hands and your view bob and sway as you walk, harder when you sprint, and lag a little behind when you turn.
- **Left hand:** hangs low while walking, pumps as a fist when you sprint, and pulls in when you crouch.
- **Pickups:** you step in and reach for notes (you hold each one up to read it) and kneel for batteries, which you snap into the camcorder.
- **Panic:** when the light flickers with the monster nearby, it sometimes smacks the camcorder.
- **The map (M):** you hold the paper up in your left hand. It's a real object in front of you, lit by your light, and the game keeps running.
- **The kill:** both hands come up to shield your face, get shoved aside, and the camcorder falls.
- **Intro and ending:** you carry the box down the stairs, reach for the wall that isn't there, flail as you fall, and push the exit door open at the end.

## Level 2: the service tunnels

The exit door from level 0 opens onto a staircase going down. Level 2 is a new maze of concrete maintenance tunnels: pipes along the walls, puddles, floor grates, a green-and-yellow painted band, and red emergency lamps (most of them dead). The tunnels are longer and narrower than level 0, with fewer loops.

The thing down here is The Smile: a tall, stooped figure with long arms and a mouth that never closes. Its body is wet, near-black skin with a crawling grain, so in the beam you mostly see the pale ridges of its ribs and shoulders and its white skull face. When it rushes or investigates it moves in jerky stop-motion. It is blind. It hunts by sound:

- Running can be heard about 20 m away (less through walls). It shrieks and rushes the spot.
- Walking can be heard a few metres away. It comes to investigate.
- Crouching is almost silent. Standing still is silent, but it can still walk into you.
- It clicks its tongue to find its way, so you can hear where it is. The clicking speeds up when it stops to listen.

Your objective is three breakers on the walls. You can hear them buzz, and all three are marked on the map (M) from the start. Throwing one is a loud CLUNK that it hears from anywhere nearby, and it comes running. After the third breaker, the freight lift opens somewhere far away. The tapes are fresh when you start level 2, a death costs a tape and you keep your breakers, and if all three tapes run out the tunnels change and you start level 2 again.

When it catches you, it folds down over you face-first, both hands on your head.

It has its own rig: two-bone IK for its legs and long arms, a stepping gait, a torso that stoops more the faster it goes, and a head that twitches and tilts while it listens.

## Level 3: The Windows (Level 188)

The freight lift drops for a long time and opens into the lift lobby of an old hotel, then goes dead behind you. The hotel is one long ring of building around a courtyard as big as a city block. On the ground floor a single corridor runs all the way round, with windows on the courtyard side and hotel rooms on the other. Across the yard, four more floors of windows look back at you. This is the Backrooms' Level 188.

The smiling monster from level 0 followed you down. Here it is nine times its size, taller than the building, and it crouches in the middle of the courtyard. **Its eyes glow, and they throw a white beam.** It drags that beam along the windows of one wing at a time, back and forth, stopping now and then to lean in and peer through a window. The beam casts real shadows through the window frames, so you can watch the light crawl down the corridor toward you.

- **Stay out of the beam.** If it sits on you for about a second, the giant roars and comes for you. Crouching and switching your flashlight off buy you a little more time.
- **Run.** Sprinting past the light is usually the way through, but it can hear you run, and it may swing the beam toward the sound.
- **Duck into the rooms.** Every room has an open door off the corridor, and the beam can't reach far past the doorway.
- **Close the curtains (E).** A closed curtain blocks the beam completely, so drawing the curtains ahead of the light makes a safe stretch of corridor.
- **When it hunts you,** the beam stays on you through every window you pass. It rears up, then lunges at the building and punches both hands through the window nearest to where you're going. Glass sprays down the corridor and that window's curtains are gone for good. If you're right there, it has you.
- **The way out:** find the **four fuses**, one in a room in each wing (they glint in the dark). Bring them to the fuse box in the lift lobby. That powers the lock on the **north stair door**, on the far side of the ring. It also turns every light in the building on, and the giant sees it: it gets faster, sweeps harder and listens harder. Run for the stairs.
- People stand in some of the upper windows across the courtyard, but only at the edge of your vision (Level 188's "Peripherals"). Look straight at them and they're gone.
- Dying here costs no tape. You wake up in the lift lobby, you keep your fuses, and its beam starts on some other wing.

## Between the levels

Each level hands over to the next with a short in-game scene (E or click to skip):

- **Level 0 → level 2:** you step through the exit door onto a concrete stairwell. The door slams behind you and takes the yellow light with it. You go down two flights past a red lamp and someone's warning painted on the wall (DON'T RUN, it hears), then through a steel door into the dark.
- **Level 2 → level 3:** the freight lift grinds down a long shaft with floor lights strobing past the gate, then thuds to a stop and dings. The gate and doors open onto the lift lobby, and the lift dies behind you. You walk out into the corridor and up to a window. The giant is out in the courtyard, sweeping its beam along the windows. It turns its glowing eyes, and its light, onto you.
- **Level 3 → the ending:** you pull the north stair door open and step through. Behind you, the window across the corridor bursts and a giant hand reaches down the corridor after you. The door slams on its fingers, and the ending film plays.

## The map

Press M to hold up Wanderer 7's pencil map. The game keeps running while you read it. It shows the walls you've seen, your trail, every spot where you saw the monster (with how long ago), and a circle where the next note probably is.

## When it catches you

Your view whips around to face it. It rises, tilts its head and closes its hands around your face. It snaps forward, you drop to your knees, then hit the floor with it hanging over you, and the light dies.

## The ending

Get through the north stair door in level 3 and a short film plays. You stumble out into a rainy parking lot under one orange street lamp as the door swings shut behind you. Then it's three weeks later: the tape rewinds and plays back the last seconds, filmed from the camcorder hanging at your side. A long pale hand slides out and stops the door from closing. Pause. One frame forward. It's in the doorway, smiling at the camera. Press E or tap to skip.

## Controls

| Action | Keys |
| --- | --- |
| Move / sprint / crouch | W A S D / Shift / C |
| Look | Mouse (click to lock), drag on a touchscreen, or arrow keys |
| Read a note / open the door / throw a breaker / close curtains / take a fuse | E |
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
- `monster_lite.glb`, `arms_lite.glb`, `camcorder_lite.glb`: what the game loads for the monster, your arms and the camcorder. They're lighter copies of `smily_horror_monster.glb`, `fps_arms.glb` and `camcorder.glb` (the originals), with textures as JPEG, the camcorder mesh simplified from 200k to 24k triangles, and two textures that were cut off at the end of the original files removed.
- `smile.glb`: level 2's hunter, a simplified copy (1.5 MB) of `the_smile__rigged 2.glb`
- `world.glb`: what the game actually loads for the rooms and furniture (3.8 MB). It's built from the five models below: textures shrunk, unused parts of the room scan removed, and the desk chair simplified.
- `backrooms_vr.glb`, `70s_desk_chair.glb`, `backrooms_movie_ladderback_restaurant_chair.glb`, `sofa_-_classic_furniture_set..glb`, `trim_sheet__example_dresser.glb`: the original models

## Credits

- Monster: "Smily horror monster" (CC BY 4.0), from Sketchfab.
- Level 2 hunter: "The smile ( Rigged)" by Vertex Mercher (CC BY 4.0), from Sketchfab. `smile.glb` is a simplified copy.
- Arms: "fps arms" (CC BY 4.0), from Sketchfab.
- Camcorder: "Camcorder" by omegadarling (CC BY 4.0), from Sketchfab.
- Rooms: "Backrooms VR" by carlcapu9 (CC BY 4.0), from Sketchfab.
- "70's desk chair" by iank2z (CC BY 4.0), from Sketchfab.
- "Backrooms Movie Ladderback Restaurant Chair" by varrocharlie (CC BY 4.0), from Sketchfab.
- "Sofa - Classic furniture set." by chris_models (CC BY 4.0), from Sketchfab.
- "Trim Sheet Example Dresser" by Chris Sweetwood (CC BY-SA 4.0), from Sketchfab. The reduced copy of the dresser inside `world.glb` is shared under the same CC BY-SA 4.0 licence.
