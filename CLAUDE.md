# CLAUDE.md

Guidance for Claude when working in this project. THIS REPOSITORY IS PUBLIC.

## What this project is

The public half of the Global Orchid Pollinators project: the maps, the
landing page and the one workbook they read. The private half is the sibling
folder `../Global_Orchid_Pollinators`, which holds the master workbook with the
true coordinates and the pipeline that produces the workbook here. Read that
project's `CLAUDE.md` for how the data are made.

## The rule that matters most

Nothing that could locate a population may enter this folder:

- no true coordinate, in any file, comment, commit message or note;
- not the master workbook, not the private enriched workbook, not
  `private/coordinate_mask.csv`, not the students' tracker or changelogs;
- no place name more specific than what the Ackerman database gives in its
  `locality` column.

The coordinates in `Pollination_List_pollinators_enriched.xlsx` here are
displaced by 10 to 25 km (see README.md). The workbook is written by
`pollinators_wrangling.qmd` in the private project and must never be edited by
hand or replaced by the private copy, which has the same file name.

## How it is rebuilt

From the PRIVATE project, run `render_all.qmd`. It writes the workbook here,
renders `mapa_final_static.qmd` into `docs/`, rewrites `manifest.json` and
refreshes the figures in `docs/index.html`. Then commit and push both
projects.

## Conventions

- All code lives in `.qmd` documents.
- Documents are in English. The landing page translates itself in the browser
  (English, Spanish, Portuguese, French, Chinese); see the private project's
  notes before changing its English wording.
- Subfamilies in phylogenetic order: Apostasioideae, Cypripedioideae,
  Vanilloideae, Orchidoideae, Epidendroideae.
- Genus and species names in italics. No em-dashes.
- Raymond commits and pushes with GitHub Desktop. Never run git from the Mac
  shell Claude uses: it leaves a lock file it cannot delete.
