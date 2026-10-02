# Global Orchid Pollinators: maps

Interactive maps of the global distribution of orchid pollinators.

- Site: <https://raymondltremblay.github.io/Global_Orchid_Pollinator_Maps/>
- Interactive explorer: <https://raymondltremblay-global-orchid-pollinators.share.connect.posit.cloud/>

Authors: Raymond L. Tremblay, Natalia Palou, Caleb Pacheco and Naan Lamoso.
Georeferencing: Natalia Palou, Caleb Pacheco and Naan Lamoso.

## The positions are approximate by design

Orchids are collected, and a published coordinate is a direction to a
population. **No coordinate in this repository is a study site.** Before the
data were published, each site was moved once by a random distance between 10
and 25 km, in a random direction:

- the displacement of a site is fixed, so the published position never changes
  and cannot be averaged out over versions;
- orchids studied at the same site were moved together;
- the displaced point was kept on land and, where possible, in the same
  ecoregion as the true one;
- the biome, ecoregion and realm of each record are those of its TRUE position.

The column `coord_displaced` in the workbook marks the records that were moved.
A few records could not be moved because no land lies within 25 km of them;
they are coordinates at sea, or on small islands that the ecoregion map does
not draw.

The true coordinates are not public. Researchers who need them for a specific
purpose can write to raymond.tremblay@gmail.com.

## What is here

| File | What it is |
|---|---|
| `Pollination_List_pollinators_enriched.xlsx` | The data: one row per orchid record, with traits, pollinators parsed to order, family and genus, displaced coordinates, coordinate precision, biome, ecoregion and realm |
| `mapa_final_static.qmd` | The distribution maps, rendered to `docs/mapa_final_static.html` |
| `mapa_final.qmd` | The same maps with the interactive explorer (Quarto with Shiny) |
| `pollinator_map.qmd` | A search map by orchid and by pollinator (Quarto with Shiny) |
| `biomes_2017.geojson` | The 14 biomes, simplified, drawn as the optional overlay |
| `docs/` | The published site (GitHub Pages) |
| `manifest.json` | What Posit Connect Cloud needs to build the explorer |

The workbook is produced from the master database by a pipeline that is not
in this repository, because the master holds the true coordinates.

## Sources

The pollination records are those of the global orchid pollination database of
Ackerman et al. (2023), *Beyond the various contrivances by which orchids are
pollinated: global patterns in orchid pollination biology*, Botanical Journal
of the Linnean Society 202: 295-324, archived at
<https://doi.org/10.5281/zenodo.7263689> (CC BY 4.0). This project adds the
georeferencing.

Biomes and ecoregions: RESOLVE Ecoregions 2017, Dinerstein et al. (2017),
BioScience 67: 534-545 (CC BY 4.0).

## Running the documents

`mapa_final.qmd` and `pollinator_map.qmd` use `server: shiny`: in RStudio use
**Run Document**. `mapa_final_static.qmd` renders with **Render** to a single
self-contained HTML file.

Packages: `openxlsx`, `readxl`, `dplyr`, `tidyr`, `stringr`, `ggplot2`,
`leaflet`, `shiny`, `htmltools`, `jsonlite`, `DT`.
