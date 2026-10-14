# Oder Front

A real-time strategy game in the browser, in the spirit of *War of the Dots*, played on real maps.
Pick any place on Earth (or upload a map image, such as a Google Maps screenshot), draw the opening front, deploy your divisions and fight a computer opponent.

## Play
Open `index.html` through a web server (it loads `world.json` and `terrain.png` from the same folder):

```sh
python3 -m http.server
# then open http://localhost:8000/
```

With GitHub Pages turned on for this repository, it is playable at `https://comeonfloyd.github.io/wargame/`.

## Features
- World map picker with city search and presets (Leszno–Wrocław sketch, Ardennes, Normandy, Kursk, Korea, Virginia), or upload any map image (blue = water, darker green = forest, beige/grey = city).
- Draw the opening front freehand; swap sides.
- Infantry and armor divisions take ground around them; front lines redraw live. Encircled troops lose strength; empty pockets collapse.
- Easy / Normal / Hard opponent.
- Dig in (D): draw a defence line and the selected units spread along it and dig it (or press twice to dig in where they stand). Trenches cut the damage defenders take and slow attackers; fighting and bombing wreck them.
- Terrain: open, forest, hills, mountains, dry ground, marsh, cities, rivers and roads, each changing speed and combat. Roads give a fast road march.
- Orders route around water, rough ground and enemy troops; drag in a curve to give a hand-drawn route.
- Air wings: bombing strikes and fighter cover. Fighting and bombing scar the ground.
- Save / continue in the browser.

## Data
- Natural Earth 1:10m (land, lakes, rivers, roads, borders, urban areas, wetlands): public domain.
- Towns: GeoNames (CC BY 4.0), via the `all-the-cities` npm package.
- `terrain.png`: derived from the three.js Earth textures (NASA Blue Marble colour and bump map). About 10 km per pixel, so forests are approximate.
- `tools/world.py` and `tools/terrain.py` rebuild `world.json` and `terrain.png`.

`legacy/v1-leszno-wroclaw.html` is the first single-map version.
