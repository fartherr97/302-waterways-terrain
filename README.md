# 302 Waterways terrain tiles

Depth and elevation tiles for the 302 Waterways 3D view, served by GitHub Pages
at `https://fartherr97.github.io/302-waterways-terrain/`.

- Source: NOAA NCEI Continuously Updated Digital Elevation Model (CUDEM),
  1/9 arc-second topobathy (public domain).
- Area: lng -76.65 … -73.95, lat 37.90 … 40.30 (Delaware, Ocean City MD,
  the Delaware River to Philadelphia, South Jersey, the upper Chesapeake).
- Tiles: XYZ (Web Mercator) at zoom 10, 12 and 14 (14 only where there is
  water); `index.json` lists them.
- Format: 257 × 257 int16 heights in decimetres (NAVD88), rows north → south,
  each row delta-coded (first value absolute), little-endian, gzip.

Built by `scripts/engine3d/bake_terrain.py` in the app repository.
