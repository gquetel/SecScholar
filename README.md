# SecScholar

Searching for academic papers on Google Scholar can return an overwhelming number of results. **SecScholar** is a simple web tool that lets you build targeted Google Scholar queries filtered by your targetted cybersecurity conferences.

Select the venues you care about, type your keywords, and search for your no more manually assembling `source:"..."` filters.

**Try it:** [secscholar.gquetel.fr](https://secscholar.gquetel.fr)

See the full list of venues in [`data/conferences.yml`](data/conferences.yml).

**Note:** Source strings are heuristics. While some precisely capture all papers from a conference, others may return incomplete results.  Google Scholar's `source:` field has a maximum length, which sometimes forces the use of shorter, incomplete substrings. For instance: 
`source:"International Conference on Trust, Security and Privacy in Computing and Communications"` does not return anything, while `source:"International Conference on Trust"` works. 


## How it works

1. **Pick a tier** — A\*+, A+, B+, or C+ buttons select all conferences at or above a [CORE ranking](https://www.core.edu.au/conference-portal), or check individual conferences manually.
2. **Enter keywords** — e.g. *Intrusion Detection System*.
3. **Copy or search** — copy the generated query to your clipboard or open it directly on Google Scholar.

## Contributing

Missing a conference? PRs are welcome to add new entries.

### Finding the correct source strings

Finding the right Scholar `source:` string is a bit of trial and error. For a given conference:

1. Search for the latest proceedings on Google Scholar.
2. Try the full proceedings name as a `source:"..."` filter.
3. Filter by date to isolate a single edition and sanity-check the result count.
4. If results look off, try shorter substrings — e.g. `source:"ACM SIGSAC"` works while the full conference name does not.

## Credits

Conference data follows conventions from [sec-deadlines](https://github.com/sec-deadlines/sec-deadlines.github.io). Rankings are based on the [CORE 2023 conference portal](https://portal.core.edu.au/conf-ranks/?search=security&by=all&source=CORE2023&sort=arank&page=1).
