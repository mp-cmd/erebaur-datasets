---
license: cc-by-4.0
pretty_name: Erebaur Gem Properties
language:
- en
size_categories:
- n<1K
task_categories:
- tabular-classification
tags:
- gemstones
- gemology
- mineralogy
- minerals
- crystallography
configs:
- config_name: default
  data_files:
  - split: train
    path: gem-properties.csv
---

# Erebaur Gem Properties

Physical and optical properties of 60 gem materials: species, chemical formula, crystal system, Mohs hardness, refractive index, specific gravity and colors, with a verification status for every row. From the property table in Chapter 02 of the Erebaur encyclopedia.

**60 rows**, one CSV file: `gem-properties.csv` (UTF-8, comma-separated, header row).

## Attribution

Required wherever the data is reused:

> Data: [Erebaur](https://erebaur.com/stones/) (https://erebaur.com), CC BY 4.0

The link goes to the matching page on the site, https://erebaur.com/stones/. Keep it when you reproduce the line.

## Data dictionary

| Column | Type | Description |
|---|---|---|
| `name` | string | Stone or variety name as used in the encyclopedia. |
| `species` | string | Mineral species, or the material for rocks and organics. |
| `family` | string | Grouping used by the site’s filters: diamond, corundum, beryl, chrysoberyl, garnet, tourmaline, spinel, quartz, opal, jade, other, rare or organic. |
| `formula` | string | Chemical formula, with Unicode subscripts. |
| `crystal_system` | string | Crystal system, following the MSA Handbook of Mineralogy. Qualifiers in brackets mark aggregates and microcrystalline material. |
| `mohs_min` | numeric | Mohs hardness, low end of the range. |
| `mohs_max` | numeric | Mohs hardness, high end of the range. Equal to mohs_min when a single value is given. |
| `ri_min` | numeric | Refractive index, low end. Empty when the material cannot be read on a refractometer. |
| `ri_max` | numeric | Refractive index, high end. |
| `sg_min` | numeric | Specific gravity, low end. |
| `sg_max` | numeric | Specific gravity, high end. |
| `colors` | string | Colors the stone occurs in, as described in the encyclopedia. |
| `verification` | string | grade_a_sourced: values from GIA, Gems & Gemology, the MSA Handbook of Mineralogy or CIBJO. grade_a_with_exceptions: grade-A values except for the field named in notes. group_range: Mohs is the range for the whole garnet group rather than the species. unverified_secondary_source: no grade-A source found; values from secondary compilations. |
| `notes` | string | What Erebaur’s editorial review records about this row specifically. Empty when it records nothing. |
| `sources` | string | Sources in Chapter 02’s list that are about this stone or that the editorial review ties to this row, separated by " \| ". Not a field-by-field citation. Otherwise the URL of the chapter’s full source list. |
| `erebaur_url` | url | The stone’s own page on erebaur.com, or its row in the chapter’s property table when it has none. |

## Sources and how they were checked

Every row was checked in September 2026 against institutional sources only: the GIA Gem Encyclopedia and *Gems & Gemology* for each stone they cover, the Mineralogical Society of America’s *Handbook of Mineralogy* for minerals GIA does not profile, and CIBJO’s Coral Book for precious coral. No row is taken from Wikipedia except the three marked `unverified_secondary_source`, which still carry values from secondary compilations because no grade-A figure could be found.

Crystal systems follow the MSA *Handbook of Mineralogy*: GIA’s property boxes do not state them and the IMA-CNMNC list does not publish them. Where a property is given as a single value, `*_min` and `*_max` are equal.

The `verification` and `notes` columns restate Erebaur’s editorial review items for Chapter 02 and Chapter 03 (the chapter’s `flags`, listed in the site’s REVIEW.md). The generator checks each note against the review item it restates and refuses to run when one has changed.

The full source list for the chapter, as published on the site: <https://erebaur.com/chapters/stones/#sources>

- [GIA Gem Encyclopedia: gem pages carrying species, Mohs hardness, refractive index, specific gravity and color](https://www.gia.edu/gem-encyclopedia)
- [GIA Gem Encyclopedia: Jade (jadeite, nephrite and green omphacite)](https://www.gia.edu/jade)
- [GIA Gems & Gemology, Spring 2000: Burmese Jade, The Inscrutable Gem (Hughes); Chromium-Bearing Taaffeites (Schmetzer)](https://www.gia.edu/dam/jcr:4b5d009c-53ed-464a-a8cd-4d5ab23f56c6/SP00.pdf)
- [GIA Gems & Gemology, Summer 1996: Russian Demantoid (Phillips and Talantsev), with calcium garnet property table](https://www.gia.edu/dam/migrated-assets/docs/doc1/Russian-Demantoid-Czar-of-the-Garnet-Family.pdf)
- [GIA Gems & Gemology, Winter 2003: Red Beryl from Utah, A Review and Update (Shigley and others)](https://cms.gia.edu/dam/jcr:e7867d10-09cc-4122-839b-2bf053ea11f6/Winter-2003-Gems-Gemology-Red-Beryl-Utah-Review-Update.pdf)
- [GIA Gems & Gemology, Spring 2003: Poudretteite from the Mogok Valley; The First Transparent Faceted Grandidierite](https://www.gia.edu/dam/migrated-assets/gems-and-gemology/pdf/SP03.pdf)
- [GIA Gems & Gemology, Fall 1997: Benitoite from the New Idria District, San Benito County, California (Laurs and others)](https://www.gia.edu/dam/migrated-assets/gems-and-gemology/pdf/FA97.pdf)
- [GIA Gems & Gemology, Winter 2005, Gem News International: New discoveries of painite in Myanmar (Rossman)](https://www.gia.edu/dam/migrated-assets/gems-and-gemology/pdf/WN05.pdf)
- [GIA Gems & Gemology, Summer 2009: The “Type” Classification System of Diamonds and Its Importance in Gemology (Breeding and Shigley)](https://www.gia.edu/dam/migrated-assets/docs/doc1/type-classification-system-of-diamonds-SU09.pdf)
- [GIA Gems & Gemology, Summer 2017: Carbonado Diamond, A Review of Properties and Origin](https://www.gia.edu/gems-gemology/summer-2017-carbonado-diamond)
- [CIBJO Blue Book: The Gemstone Book, Coloured Stone Commission (2022), commercial names and treatment disclosure](https://cibjo.org/wp-content/uploads/2023/01/22-12-22-Official-Gemstone-Book.pdf)
- [CITES species listing: Loxodonta africana (African elephant), Appendix I from 18 January 1990](https://cites.org/eng/gallery/species/mammal/african_elephant.html)
- [CITES AC31 Doc. 23: listing status and management of precious corals (Coralliidae and Antipatharia)](https://cites.org/sites/default/files/eng/com/ac/31/Docs/E-AC31-23.pdf)
- [US eCFR, 50 CFR 17.40(e): African elephant rule, prohibitions and de minimis and antique exceptions](https://www.ecfr.gov/current/title-50/chapter-I/subchapter-B/part-17/subpart-D/section-17.40)
- [Mineralogical Society of America, Handbook of Mineralogy: PDF search index for the per-mineral data sheets (system, hardness, RI, density)](https://handbookofmineralogy.org/pdf-search/)
- [GIA Gems & Gemology, Winter 1985: Stockton and Manson, A Proposed New Classification for Gem-Quality Garnets (Table 1)](https://www.gia.edu/gems-gemology/winter-1985-garnet-classification-stockton)
- [CIBJO Blue Book: The Coral Book, Coral Commission (November 2024), coral hardness, density and nomenclature](https://cibjo.org/wp-content/uploads/2024/11/November-2024-Coral-Blue-Book.pdf)
- [GIA Gems & Gemology, Winter 1987: Fritsch and Misiorowski, The history and gemology of queen conch pearls](https://www.gia.edu/gems-gemology/winter-1987-queen-conch-pearls-fritsch)
- [GIA Gems & Gemology, Summer 2015, Gem News International: non-bead cultured pearls from Strombus gigas (queen conch)](https://www.gia.edu/gems-gemology/summer-2015-gemnews-nonbead-cultured-pearls-strombus-gigas)
- [Sanders, Colour of precious opal, Nature 204 (1964) 1151–1153 (diffraction by ordered silica spheres)](https://www.nature.com/articles/2041151a0)
- [MSA Handbook of Mineralogy: Kyanite data sheet (hardness 5.5 parallel [001], 7 parallel [100])](https://handbookofmineralogy.org/pdfs/kyanite.pdf)
- [MSA Handbook of Mineralogy: Labradorite data sheet (hardness 6 to 6.5, density 2.68 to 2.72)](https://handbookofmineralogy.org/pdfs/labradorite.pdf)

## Known limitations

- Counts by verification status: grade_a_sourced 50, grade_a_with_exceptions 4, group_range 3, unverified_secondary_source 3.
- Ranges are gemmological ranges for the material as it is traded, not absolute limits for the mineral species.
- Some varieties carry their species’ ranges unchanged, so these columns cannot tell them apart: Ruby, Blue sapphire, Padparadscha sapphire, Fancy sapphire; Emerald, Aquamarine; Rubellite, Indicolite, Paraíba tourmaline; Red spinel, Cobalt blue spinel; Amethyst, Citrine, Rose quartz, Smoky quartz; Agate, Chrysoprase.
- Two published RI maxima are open bounds ("below 1.742" for pyrope, "below 1.810" for spessartine) stored as plain values.
- Taaffeite’s RI and SG come from a ten-stone study and may be narrower than the species; musgravite is absent because published RI and SG disagree.
- The table does not distinguish rhombohedral (a lattice system) from trigonal (a crystal system); see Chapter 03’s review items.
- Sphene’s dispersion of 0.051 and most dispersion values in Chapter 03 have no grade-A source. Dispersion is not a column here.

## License

[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). The license covers Erebaur’s compilation: the selection and arrangement of the rows, the column structure and the descriptive text Erebaur wrote. The underlying facts are not owned by anyone, and the publications listed above keep their own rights. See `../LICENSE`.

## Citation

Data: Erebaur (https://erebaur.com), CC BY 4.0. Erebaur Gem Properties, compiled from the Erebaur encyclopedia, last reviewed 2026-09-19. https://erebaur.com/stones/

A machine-readable citation is in `CITATION.cff`.

## Regenerating

These files are generated from the encyclopedia content. Do not edit them by hand: run `npm run datasets` in the site repository.
