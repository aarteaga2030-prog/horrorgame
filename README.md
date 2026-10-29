# Don't Fix It

A first-person Three.js horror game built on the saying *"if it ain't broke, don't fix it."*

Uncle Wendell broke five things in his house on purpose. Each one holds back the Tinkerer, a thing under the floor that loves to help. It fixes what should stay broken and breaks what should keep working. Survive three nights until 6:00 AM.

## Play

Open `index.html` through a web server (GitHub Pages works). Opening the file directly from disk blocks the monster model from loading, and the game falls back to a placeholder creature.

To run it locally:

```
python3 -m http.server
```

Then open http://localhost:8000.

## Controls

| Action | Keys |
| --- | --- |
| Move | W A S D (Shift to hurry) |
| Look | Mouse (click to lock), drag on a touchscreen, or arrow keys |
| Fix | Hold E |
| Break | Hold Q |
| Read a note | E |
| Notebook | N |

## Files

- `index.html`: the whole game (Three.js r160 from a CDN, no build step)
- `smily_horror_monster.glb`: the Tinkerer's model and animation
