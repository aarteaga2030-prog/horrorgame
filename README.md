# Little Grin

A first-person Three.js horror game. Marrow Street Children's Home closed in 1998 after children went missing. A polaroid arrived in your mail showing you as a child, with something small and grey smiling behind you. You go back at night to find the rest of the photographs.

## How it plays

- The house is pitch black. Your hand-crank flashlight is the only light, apart from lightning through the windows.
- **It only moves when your light isn't on it.** In the beam it freezes mid-pose. Look away and it skitters closer.
- Your light drains. Hold **R** to crank it, but the light is off while you crank.
- The flashlight flickers when it's near. If it stays lost in the dark, it gets behind you.
- Find 6 photographs (random spots, one per room). Each one makes it faster.
- After all six, take the last photo by the front door and run. It doesn't stop for the light anymore.

## Play

Open `index.html` through a web server (GitHub Pages works). Opening the file straight from disk blocks the monster model, and a stand-in creature is used instead.

```
python3 -m http.server
```

Then open http://localhost:8000.

## Controls

| Action | Keys |
| --- | --- |
| Move / run | W A S D / Shift |
| Look | Mouse (click to lock), drag on a touchscreen, or arrow keys |
| Pick up a photo / open the door | E |
| Crank the flashlight | Hold R |
| Flashlight on/off | F |
| Photos | P |

## Files

- `index.html`: the whole game (Three.js r160 from a CDN, no build step)
- `smily_horror_monster.glb`: the monster's model and animation, scaled down to child size in game
