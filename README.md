# sec-papers-search

This project aims at making the search of good quality papers easier. Directly querying Google Scholar can lead to an enormous amount of retrieved papers. Manually filtering good quality papers is time-consuming, however, it can be simplified using filters, notably the `source` keyword which allows to specify the venues in which the papers should be published.

This repository provides a static webpage where users can select cybersecurity venues and generate the corresponding Google Scholar `source:` filter string ready to copy-paste into a search query.

## Features

### Search by conference
Each conference is listed with a checkbox. Checking a conference adds its `source:"..."` clauses to a text box that can be copied directly into Google Scholar.

### Search by tags
Tags allow including or excluding entire groups of conferences at once. The tag taxonomy (SEC, PRIV, CRYPTO, TOP4, CONF, SHOP) follows the convention established by [sec-deadlines](https://github.com/sec-deadlines/sec-deadlines.github.io/blob/master/_data/types.yml).

## Data

- [`data/conferences.yml`](data/conferences.yml) — Conference entries with `name`, `description`, `sources` (Scholar source strings), and `tags`.
- [`data/types.yml`](data/types.yml) — Tag definitions used to group conferences.

## Adapting this repository to another domain

The project can easily be forked and adapted to other domains by modifying the data files.

### Finding the list of conferences to include

### Finding the correct source strings
So far, finding the correct source has been a bit of a trial and error. Typically, for a conference I would:
1. Search for the last conference occurrence's proceedings.
2. Cut the name to not include dates, and search on scholar using the source keyword for all results.
3. Filter using the date (since XXXX) to only show the papers of the last conference occurrence.
4. If the order of magnitude seems ok, the source is used.

Else, try with substrings of the proceedings full name. For instance: `source:"ACM SIGSAC Conference on Computer and Communications Security"` does not work, while `source:"ACM SIGSAC"` does.
