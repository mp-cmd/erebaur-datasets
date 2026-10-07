# Erebaur open datasets

Three tables from the [Erebaur encyclopedia of precious stones](https://erebaur.com/chapters/), published as open data under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).

| Dataset | Rows | From | Erebaur page | Hugging Face |
|---|---|---|---|---|
| [`gem-properties`](gem-properties/) | 60 | Chapter 02, property table | <https://erebaur.com/stones/> | [mp-cmd/erebaur-gem-properties](https://huggingface.co/datasets/mp-cmd/erebaur-gem-properties) |
| [`mining-localities`](mining-localities/) | 57 | Chapter 05, mine map | <https://erebaur.com/atlas/> | [mp-cmd/erebaur-mining-localities](https://huggingface.co/datasets/mp-cmd/erebaur-mining-localities) |
| [`auction-records`](auction-records/) | 19 | Chapter 14, records table | <https://erebaur.com/records/> | [mp-cmd/erebaur-auction-records](https://huggingface.co/datasets/mp-cmd/erebaur-auction-records) |

Each folder holds the CSV, a dataset card (`README.md`) with the data dictionary, the sources and how they were checked and the known limitations, a `CITATION.cff`, and the metadata Kaggle reads (`dataset-metadata.json`).

## Attribution

Required wherever the data is reused:

> Data: Erebaur (https://erebaur.com), CC BY 4.0

To cite the collection, use `CITATION.cff` at the root of this repository (GitHub’s “Cite this repository”). Each folder has its own for a single table.

## How these files are made

They are generated from the encyclopedia content, last reviewed 2026-09-19, and are not edited by hand. The generator reads the chapter tables, asks the site’s own code which stones have a page and how records are categorized, and restates the editorial review items for each row. When a review item it relies on has changed, it stops and names the row, so a stale note cannot be published.

## Corrections

If a value is wrong, open an issue here or write to info@erebaur.com, with a source. Corrections are made in the encyclopedia first and the tables are regenerated from it.

## License

See [LICENSE](LICENSE). The license covers Erebaur’s compilation, not the underlying facts or the sources it cites.
