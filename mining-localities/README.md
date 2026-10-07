---
license: cc-by-4.0
pretty_name: Erebaur Gem Mining Localities
language:
- en
size_categories:
- n<1K
task_categories:
- other
tags:
- gemstones
- mining
- geography
- geospatial
- diamonds
configs:
- config_name: default
  data_files:
  - split: train
    path: mining-localities.csv
---

# Erebaur Gem Mining Localities

57 gem mining localities across 31 countries, from the mine map in Chapter 05 of the Erebaur encyclopedia: diamond, corundum (ruby and sapphire), emerald and other gem deposits, with coordinates, the stones produced, operating status as of September 2026 and a coordinate-quality grade.

**57 rows**, one CSV file: `mining-localities.csv` (UTF-8, comma-separated, header row).

## Attribution

Required wherever the data is reused:

> Data: [Erebaur](https://erebaur.com/atlas/) (https://erebaur.com), CC BY 4.0

The link goes to the matching page on the site, https://erebaur.com/atlas/. Keep it when you reproduce the line.

## Data dictionary

| Column | Type | Description |
|---|---|---|
| `name` | string | Locality name as used on the map. |
| `country` | country | Country, English short name. |
| `iso3` | string | ISO 3166-1 alpha-3 country code. |
| `lat` | latitude | Latitude in decimal degrees (WGS 84). A mine or nearest-town position; see coordinate_quality. |
| `lon` | longitude | Longitude in decimal degrees (WGS 84). |
| `group` | string | Map layer: diamond, corundum, emerald or other. |
| `stones` | string | Stones the locality produces or produced. |
| `status` | string | active, artisanal, closed or historic, as of September 2026. |
| `description` | string | One-line description written for the encyclopedia. |
| `coordinate_quality` | string | operator_stated: the operator’s own coordinate. published_coordinate: printed in a journal. approximate: a mine or town position, typically good to 0.1 to 0.3 degrees. weak: named in the editorial review as one of the least certain points. |
| `coordinate_precision_deg` | numeric | Estimated precision in degrees, where the editorial review states one. Empty otherwise. |
| `notes` | string | What Erebaur’s editorial review records about this locality’s coordinate, status or description. Empty when it records nothing. |
| `sources` | string | Sources in Chapter 05’s list that are about this locality, separated by " \| ". Otherwise the URL of the chapter’s full source list. |
| `erebaur_url` | url | The locality selected on the erebaur.com atlas map. |

## Sources and how they were checked

The chapter was re-sourced in September 2026 against journals, government and intergovernmental bodies and operators’ own disclosures. One source is trade press (MINING.COM, for Koidu), and its row says so.

Coordinates are mine or nearest-town positions. Most were first taken from public gazetteers and are approximations; the editorial review grades the weakest of them, and the `coordinate_quality` and `coordinate_precision_deg` columns carry that grading. Karowe uses the operator’s stated coordinate and Zabargad the one printed in *Gems & Gemology* (Spring 1981). Four points added in September 2026 were located with OpenStreetMap through Nominatim (© OpenStreetMap contributors) and checked against a published distance where one exists, and one (Kollur) is Mindat’s point.

Status is the editorial judgment as of September 2026, from operator disclosures where they exist. The `notes` column says where a status is judged rather than sourced.

The full source list for the chapter, as published on the site: <https://erebaur.com/chapters/mining/#sources>

- [Kimberley Process: Annual Global Summary 2025, production and exports](https://kimberleyprocessstatistics.org/static/pdfs/public_statistics/2025/2025GlobalSummary.pdf)
- [Kimberley Process: Annual Global Summary 2024, production and exports](https://kimberleyprocessstatistics.org/static/pdfs/public_statistics/2024/2024GlobalSummary.pdf)
- [USGS: Mineral Commodity Summaries 2026, Gemstones](https://pubs.usgs.gov/periodicals/mcs2026/mcs2026-gemstones.pdf)
- [European Commission: restrictions on diamonds under Council Regulation 833/2014](https://finance.ec.europa.eu/system/files/2023-12/faqs-sanctions-russia-diamonds_en.pdf)
- [IGF and IISD: Global Trends in Artisanal and Small-Scale Mining (2018)](https://www.iisd.org/system/files/publications/igf-asm-global-trends.pdf)
- [World Bank: working conditions of artisanal and small-scale miners (2021)](https://www.worldbank.org/en/news/press-release/2021/05/03/better-working-conditions-can-improve-safety-and-productivity-of-artisanal-and-small-scale-miners-around-the-world)
- [IMF: Botswana 2025 Article IV consultation staff report](https://www.imf.org/-/media/files/publications/cr/2025/english/1bwaea2025001-source-pdf.pdf)
- [World Bank: Macro Poverty Outlook, Botswana](https://thedocs.worldbank.org/en/doc/bae48ff2fefc5a869546775b3f010735-0500062021/related/mpo-bwa.pdf)
- [Debswana: Jwaneng mine](https://www.debswana.com/jwaneng/)
- [De Beers Group: Strengthening our partnership with Botswana (2025)](https://www.debeersgroup.com/about-us/case-studies/2025/strengthening-our-partnership-with-botswana)
- [De Beers Group: Beneficiation](https://www.debeersgroup.com/about-us/case-studies/2025/beneficiation)
- [SAIMM Journal: the CCUT block cave design for Cullinan Diamond Mine (2016)](https://scielo.org.za/scielo.php?script=sci_arttext&pid=S2225-62532016000800005)
- [SAIMM Journal: pioneering large diamond recovery at Karowe diamond mine (2016)](https://scielo.org.za/scielo.php?script=sci_arttext&pid=S2225-62532016000800004)
- [Lucara Diamond: recovery of a 1,111 carat diamond at Karowe (November 2015)](https://lucaradiamond.com/newsroom/news-releases/lucara-makes-diamond-history-recovers-1-111-carat-diamond-122558/)
- [Lucara Diamond: Annual Information Form 2025](https://lucaradiamond.com/site/assets/files/63154/lucara_annual_information_form_2025_year-end-vf.pdf)
- [Lucara Diamond: Q2 2026 results](https://lucaradiamond.com/newsroom/news-releases/lucara-announces-q2-2026-results-122939/)
- [Rio Tinto: Diavik diamond mine delivers its final production (March 2026)](https://www.riotinto.com/en/news/releases/2026/rio-tintos-diavik-diamond-mine-delivers-its-final-production)
- [PwC Canada: Arctic Canada Diamond Company receivership, Ekati mine (2026)](https://www.pwc.com/ca/en/services/insolvency-assignments/arctic-canada-diamond-company.html)
- [Petra Diamonds: Annual Report 2025, sale of Williamson](https://wp-petra-diamonds-2023.s3.eu-west-2.amazonaws.com/media/2025/10/25106-Petra_Diamonds-AR-2025-13.pdf)
- [Gemfields Group: Kagem emerald mine](https://www.gemfieldsgroup.com/assets/kagem-mining-limited-emerald-mines/)
- [Gemfields: Montepuez Ruby Mine](https://gemfields.com/about/our-mines-and-brands/montepuez-ruby-mine/)
- [Rostec: the Kaliningrad amber combine and the Primorskoye deposit (2025)](https://rostec.ru/en/media/news/the-amber-combine-resumed-mining-at-the-world-s-largest-amber-field/)
- [Maconachie, University of Bath: the Diamond Area Community Development Fund](https://www.environmentalpeacebuilding.org/assets/documents/5811bd4950fa.pdf)
- [MINING.COM: Sierra Leone's largest diamond miner shuts down (2025)](https://www.mining.com/web/sierra-leones-largest-diamond-miner-shuts-down-laying-off-more-than-1000-workers/)
- [GIA Gems and Gemology: Letseng's unique diamond proposition (Fall 2015)](https://www.gia.edu/gems-gemology/fall-2015-letseng-unique-diamond-proposition)
- [GIA Gems and Gemology: black diamonds from Marange, Zimbabwe (Summer 2018)](https://www.gia.edu/gems-gemology/summer-2018-black-diamonds-from-marange-zimbabwe-a-result-of-natural-irradiation-and-graphite-inclusions)
- [GIA Gems and Gemology: Kashmir sapphire, Atkinson and Kothavala (Summer 1983)](https://cms.gia.edu/dam/jcr:14ffa273-3244-4c28-a324-3f0ff388c57e/Kashmir-Sapphire.pdf)
- [GIA Gems and Gemology: rubies from Mong Hsu (Spring 1995)](https://www.gia.edu/doc/Rubies-from-Mong-Hsu.pdf)
- [GIA Gems and Gemology: gemstone mining in Vietnam, Luc Yen (Winter 2013)](https://www.gia.edu/gems-gemology/wn13-long-gemstone-mining-vietnam)
- [GIA Gems and Gemology: emeralds of the Panjshir Valley, Afghanistan (Spring 1991)](https://www.gia.edu/dam/jcr:86a21be8-7615-40d2-a4c1-b7c70c07d8a4/SP91A2.pdf)
- [GIA Gems and Gemology: emerald mining in Brazil, Belmont and Capoeirana (Spring 2012)](https://www.gia.edu/gems-gemology/spring-2012-brazil-emerald-lucas)
- [GIA Gems and Gemology: trace-element characteristics of emeralds, Swat (Fall 2020)](https://www.gia.edu/gems-gemology/fall-2020-trace-element-characteristics-emeralds)
- [GIA Gems and Gemology: a gemological expedition to Ethiopia (Spring 2019)](https://www.gia.edu/gems-gemology/spring-2019-land-of-origins-gemological-expedition-ethiopia)
- [GIA Gems and Gemology: play-of-color opal from Wegel Tena, Wollo (Summer 2010)](https://www.gia.edu/gems-gemology/summer-2010-opal-ethiopia-rondeau)
- [GIA Gems and Gemology: cuprian elbaite from Sao Jose da Batalha (Fall 1990)](https://www.gia.edu/gems-gemology/fall-1990-tourmaline-brazil-fritsch)
- [Journal of Gemmology: spinel from Mahenge and Matombo, Tanzania (2023)](https://gem-a.com/wp-content/uploads/2024/11/JoG2023_38_5_Krzemnicki-annotated-v.2.pdf)
- [GIA Gems and Gemology: Zabargad, the ancient peridot island in the Red Sea, Gubelin (Spring 1981)](https://www.gia.edu/gems-gemology/spring-1981-zabargad-peridot-gubelin)
- [GIA Gems and Gemology: diamond and colored stone localities active 2000 to 2010, data depository to Shigley et al. (Fall 2010)](https://www.gia.edu/doc/Fall-2010-Gems-Gemology-Diamond-Colored-Stone-Localities.pdf)
- [GIA: historical reading list, diamonds in ancient India](https://www.gia.edu/diamonds-ancient-india-reading-list)
- [GIA: historical reading list, Japanese cultured pearls](https://www.gia.edu/japanese-cultured-pearls-reading-list)

## Known limitations

- Typical coordinate error is 0.1 to 0.3 degrees, more for the points graded `weak`. Do not use the points for anything that needs mine-level precision.
- Status changes quickly: Ekati, Diavik, Finsch and Koidu all changed in 2025 or 2026. Treat `status` as a snapshot of September 2026.
- The map is a selection of significant localities, not a register of every working. It is capped at 60 points.
- Four coordinates come from OpenStreetMap (ODbL 1.0) and one from Mindat; where a value came from a third-party database, that database’s terms continue to apply to it.
- Kimberley Process 2025 figures for Lesotho and Tanzania appear to repeat their 2024 values; no production figures are carried here.

## License

[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). The license covers Erebaur’s compilation: the selection and arrangement of the rows, the column structure and the descriptive text Erebaur wrote. The underlying facts are not owned by anyone, and the publications listed above keep their own rights. See `../LICENSE`.

## Citation

Data: Erebaur (https://erebaur.com), CC BY 4.0. Erebaur Gem Mining Localities, compiled from the Erebaur encyclopedia, last reviewed 2026-09-19. https://erebaur.com/atlas/

A machine-readable citation is in `CITATION.cff`.

## Regenerating

These files are generated from the encyclopedia content. Do not edit them by hand: run `npm run datasets` in the site repository.
