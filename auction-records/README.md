---
license: cc-by-4.0
pretty_name: Erebaur Gem Auction Records
language:
- en
size_categories:
- n<1K
task_categories:
- tabular-regression
tags:
- gemstones
- diamonds
- auctions
- prices
- finance
configs:
- config_name: default
  data_files:
  - split: train
    path: auction-records.csv
---

# Erebaur Gem Auction Records

19 record auction sales of diamonds, rubies and a natural pearl, 2010 to 2023, from the records table in Chapter 14 of the Erebaur encyclopedia: price as announced and in US dollars, carat weight, computed price per carat, house, city and date. Prices include the buyer’s premium.

**19 rows**, one CSV file: `auction-records.csv` (UTF-8, comma-separated, header row).

## Attribution

Required wherever the data is reused:

> Data: [Erebaur](https://erebaur.com/records/) (https://erebaur.com), CC BY 4.0

The link goes to the matching page on the site, https://erebaur.com/records/. Keep it when you reproduce the line.

## Data dictionary

| Column | Type | Description |
|---|---|---|
| `name` | string | Name of the stone or jewel, as sold or as later known. |
| `stone` | string | Description: color grade, cut, clarity, origin or setting, as catalogued. |
| `category` | string | pink-diamond, blue-diamond, colorless-diamond, ruby, pearl or other, read from the description. The same categories as the erebaur.com records page. |
| `carats` | numeric | Weight in carats at the time of sale. |
| `price_usd_millions` | numeric | Price in millions of US dollars as the chapter’s table gives it, including the buyer’s premium. |
| `price_usd` | integer | Best available US$ total: the house’s exact US$ figure where it published one, otherwise price_usd_millions × 1,000,000. |
| `price_usd_basis` | string | exact_usd_total when price_usd is an exact figure published in US dollars; usd_millions_rounded when it comes from the rounded table figure. |
| `local_price` | string | Price as the house announced it, in the currency of the sale. |
| `local_currency` | string | ISO 4217 code of local_price: USD, CHF or HKD. |
| `local_amount` | integer | local_price as a number. Rounded when the announced figure is (for example "CHF 45.44 million"). |
| `house` | string | Auction house. |
| `city` | string | City of the sale. |
| `sale_date` | string | Year and month of the sale, YYYY-MM. |
| `usd_per_carat` | integer | price_usd divided by carats, rounded to the dollar. Computed by Erebaur; can differ from a per-carat figure a house or GIA publishes. |
| `stated_record` | string | The record Chapter 14 says this sale holds, in its own words. Empty for every other row: a row is not called a record for ranking first in this table. |
| `notes` | string | What Erebaur’s editorial review records about this row. Empty when it records nothing. |
| `sources` | string | Sources in Chapter 14’s list that name this sale: lot records, press releases and GIA reports, separated by " \| ". |
| `erebaur_url` | url | The sale’s row on the erebaur.com records page, which lays the records out by category. |

## Sources and how they were checked

The table was rebuilt in September 2026 from auction house primary records: Christie’s lot pages and sale results, Sotheby’s press releases and catalogues, and GIA *Gems & Gemology* auction reports. Every price is the figure the selling house published, which includes the buyer’s premium. No row rests on Wikipedia.

`usd_per_carat` is Erebaur’s arithmetic: `price_usd` divided by `carats`. Where the house published an exact US$ total, that total is used. Otherwise the table’s US$ figure is used, which is rounded to US$0.1 million, and `price_usd_basis` says which of the two applies.

The full source list for the chapter, as published on the site: <https://erebaur.com/chapters/auctions/#sources>

- [Sotheby's: our history (founded 1744 by Samuel Baker; taken private by Patrick Drahi in 2019)](https://www.sothebys.com/en/about/our-history)
- [Sotheby's: 2025 financial results (PDF; consolidated sales of US$7.1 billion)](https://www.sothebys.com/en/docs/pdf/sothebys-reports-2025-financial-results.pdf)
- [Groupe Artémis: Christie's (founded by James Christie in 1766; joined the group in 1998)](https://www.groupeartemis.com/en/our-investments/christies)
- [Christie's: about Christie's](https://www.christies.com/en/about/overview)
- [Christie's: financial information for buyers, buyer's premium rates effective 1 September 2026](https://www.christies.com/en/help/buying-guide-important-information/financial-information)
- [Phillips: about the company (founded 1796 by Harry Phillips; LVMH 1999; de Pury 2002)](https://www.phillips.com/about)
- [Phillips: Jewels department and auction calendar](https://www.phillips.com/departments/jewels)
- [Christie's lot 242: The Oppenheimer Blue, CHF 56,837,000](https://www.christies.com/en/lot/lot-5990891)
- [Christie's: Magnificent Jewels, Geneva, 13 November 2018, lot list with prices realised](https://www.christies.com/auction/auction-16112-gnv/browse-lots)
- [Christie's lot 311: The Pink Legacy, CHF 50,375,000](https://www.christies.com/en/lot/lot-6164899)
- [Christie's: Magnificent Jewels including The Bleu Royal, Geneva, 7 November 2023](https://www.christies.com/auction/auction-21991-gnv/browse-lots)
- [Christie's lot 87: Bleu Royal, CHF 39,505,000](https://www.christies.com/en/lot/lot-6451329)
- [Christie's: New York Magnificent Jewels and The Princie Diamond, 16 April 2013](https://www.christies.com/auction/auction-2694-nyr/browse-lots)
- [Christie's lot 295: The Princie Diamond, US$39,323,750, with its Hyderabad provenance](https://www.christies.com/en/lot/lot-5672735)
- [Christie's: The Collection of Elizabeth Taylor, The Legendary Jewels, 13 December 2011](https://www.christies.com/auction/auction-2623-nyr/browse-lots)
- [Christie's lot 80: The Elizabeth Taylor Diamond, US$8,818,500](https://www.christies.com/en/lot/lot-5507955)
- [Christie's lot 12: La Peregrina, US$11,842,500, with the 1969 Parke-Bernet purchase](https://www.christies.com/en/lot/lot-5507887)
- [Christie's: Magnificent Jewels, Geneva, 11 May 2022, lot list with prices realised](https://www.christies.com/auction/auction-20937-gnv/browse-lots)
- [Christie's lot 26: The Rock, CHF 21,681,000](https://www.christies.com/en/lot/lot-6367687)
- [Christie's lot 61: The Red Cross Diamond, CHF 14,181,250](https://www.christies.com/en/lot/lot-6367722)
- [Christie's: Magnificent Jewels and the Jubilee Ruby, New York, 20 April 2016](https://www.christies.com/auction/auction-12180-nyr/browse-lots)
- [Christie's lot 255: the Jubilee Ruby, US$14,165,000](https://www.christies.com/en/lot/lot-5988023)
- [Sotheby's press release: the Williamson Pink Star, HK$453,223,000 / US$57,736,078](https://www.sothebys.com/en/articles/bidding-frenzy-for-the-williamson-pink-star-one-of-the-purest-pinkest-diamonds-ever-to-appear-at-auction-drives-final-price-to-record-hk-453-2-million-us-57-7-million)
- [Sotheby's: the five most expensive pink diamonds (CTF Pink Star, Graff Pink)](https://www.sothebys.com/en/articles/the-five-most-expensive-pink-diamonds)
- [Sotheby's: highlights from Geneva auctions (Sunrise Ruby, Blue Moon of Josephine)](https://www.sothebys.com/en/slideshows/impressive-highlights-from-geneva-auctions)
- [Sotheby's: The De Beers Blue digital catalogue (15.10 ct, Hong Kong, 27 April 2022)](https://www.sothebys.com/en/digital-catalogues/the-de-beers-blue)
- [Sotheby's press release: Hong Kong 2022 spring sales, De Beers Blue at HK$451m / US$57.5m](https://www.sothebys.com/en/press/strong-hong-kong-sales-results-reaffirm-sothebys-market-leadership-in-asia-hong-kong-2022-spring-sales-achieve-hk-3-852-billion-us-496-million-the-second-highest-total-in-company-history)
- [Sotheby's: royal jewels from the Bourbon-Parma family, CHF 53.5 million total](https://www.sothebys.com/en/articles/royal-jewels-from-the-bourbon-parma-family-achieve-record-sale)
- [GIA Gems & Gemology: Fall 2023 auction highlights (Bleu Royal, Infinite Blue)](https://www.gia.edu/gems-gemology/winter-2023-gemnews-fall-auction-highlights)
- [GIA Gems & Gemology: Spring 2023 auction highlights (Estrela de Fura, Eternal Pink, Horten)](https://www.gia.edu/gems-gemology/summer-2023-gemnews-spring-auction-highlights)
- [GIA Gems & Gemology: Spring 2022 auction highlights (The Rock, Red Cross, De Beers Blue)](https://www.gia.edu/gems-gemology/summer-2022-gemnews-auction-highlights)
- [GIA: the spring 2016 auction season (Oppenheimer Blue, Jubilee Ruby)](https://www.gia.edu/gia-news-research/vivid-spring-2016-auction-season-sales-totals-near-800-million)
- [GIA: top gems continue to set records at 2015 auctions (Sunrise Ruby, Blue Moon, Bonhams)](https://www.gia.edu/gia-news-research/top-gems-continue-set-records-2015-auctions)
- [GIA Gems & Gemology: a history of European royal jewel sales (Windsor 1987, Bourbon-Parma)](https://www.gia.edu/gems-gemology/fall-2020-european-royal-jewel-sales)
- [Gemfields Group: cumulative auction revenue and 2024 production](https://www.gemfieldsgroup.com/)
- [Gemfields Group: Kagem Mining Limited (75% Gemfields, 25% the Zambian state)](https://www.gemfieldsgroup.com/assets/kagem-mining-limited-emerald-mines/)
- [Gemfields Group: Montepuez Ruby Mining Limitada (75% Gemfields, 25% Mwiriti)](https://www.gemfieldsgroup.com/assets/montepuez-ruby-mining-limitada/)
- [Gemfields: commercial-quality emerald auction results, September 2026](https://www.gemfieldsgroup.com/auction-results-commercial-quality-emeralds-11-9-26/)
- [Gemfields: Trade Select ruby auction results and MRM update, June 2026](https://www.gemfieldsgroup.com/auction-results-trade-select-ruby-auction-and-mrm-update/)
- [Christie's: sale results, including The Blue (lot 260, Geneva, 14 May 2014), lot 409 (Geneva, 10 November 2015) and the 2023 Horten sales](https://www.christies.com/en/results)

## Known limitations

- A selection of notable record sales, not every sale above a threshold. Spirit of the Rose is left out because no lot record could be retrieved, and the Marie Antoinette pearl pendant, the natural pearl record, because no carat weight could be.
- Auction results only. Most gems change hands in confidential dealer transactions, so a stone sold privately for more does not appear.
- Prices include the buyer’s premium; pre-sale estimates do not, so a price and an estimate are not on the same basis.
- US$ figures for sales announced in Swiss francs or Hong Kong dollars come from the house or from GIA at the exchange rate on the day of sale, so US$ prices from different years are not directly comparable.
- Ranking first in a category here is not a record claim. `stated_record` carries the claims Chapter 14 makes; The Rock, for example, tops the colorless rows but the chapter makes no record claim for it.
- Chapters 13 and 15 mention further prices in their text, but neither holds a structured auction price table, so nothing from them is included.

## License

[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). The license covers Erebaur’s compilation: the selection and arrangement of the rows, the column structure and the descriptive text Erebaur wrote. The underlying facts are not owned by anyone, and the publications listed above keep their own rights. See `../LICENSE`.

## Citation

Data: Erebaur (https://erebaur.com), CC BY 4.0. Erebaur Gem Auction Records, compiled from the Erebaur encyclopedia, last reviewed 2026-09-19. https://erebaur.com/records/

A machine-readable citation is in `CITATION.cff`.

## Regenerating

These files are generated from the encyclopedia content. Do not edit them by hand: run `npm run datasets` in the site repository.
