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

## More sets

The rest of the Atlantic coast is in other repositories, listed in `sets.json`
(`{ sets: [{ name, url, core: [w, s, e, n] }] }`): the app fetches a tile from the set
whose `core` holds the middle of its zoom-10 tile (falling back to this one), and merges
their `index.json`s with this one's.

- `302-waterways-terrain-north`: north of 39.1°N (northern New Jersey to Maine)
- `302-waterways-terrain-south`: south of 39.1°N (Virginia to Florida's Atlantic side and the Keys)


## The sets (November 2026)

`sets.json` splits the rest of the coast at 33.1°N: north of it (Maine to the Carolinas) is
`302-waterways-terrain-north`, south of it (the lower Carolinas, Georgia and all of Florida,
Atlantic and Gulf) is `302-waterways-terrain-south`. Florida's tiles are NOAA NCEI CUDEM 1/9"
where it reaches, over NOAA Office of Coast Survey BlueTopo (the water) and USGS 3DEP 1/3"
(the land): data derived from NOAA Office of Coast Survey BlueTopo, all public domain.
