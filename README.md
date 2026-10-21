# Skiltkart Bergen – byggesett

Publisert som artifact: https://claude.ai/artifact/CnwVitoCcUaprRMsUVfjaM

- `site/` er det som er publisert (index.html + base64-kodede PMTiles og glyph-filer, bydeler.json, steder.json).
- `template.html` er kilden til index.html (MapLibre-CSS settes inn der det står `/*MAPLIBRE_CSS*/`, fra `maplibre-gl.css`).
- `scripts/ov.py`, `convert.py`, `mz.py`, `index.py`, `glyphs.py`: henter Overture Maps (release 2026-09-23.1) og bygger fliser med tippecanoe.

## Legge inn skiltene
1. Miljøet må ha nettverkstilgang til `nvdbapiles.atlas.vegvesen.no`.
2. `python3 scripts/nvdb_skilt.py site/skilt.json`
3. Publiser artifacten på nytt med `skilt.json` lagt til i filene. Siden leser den automatisk (kategori fra første siffer i skiltnummeret, bydel beregnes i nettleseren).

## Status
- 21.10.2026: skilt.json hentet fra NVDB (42 402 skiltplater med posisjon av 42 821) og publisert som versjon 2. Kjør steg 2–3 på nytt for å oppdatere (tar ca. 5 min).
