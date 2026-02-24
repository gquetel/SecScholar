# ScholarSec

Searching for academic papers on Google Scholar can return an overwhelming number of results. **ScholarSec** is a simple web tool that lets you build targeted Google Scholar queries filtered by your targetted cybersecurity conferences. Select the venues you care about, type your keywords, and search for papers in those specific venues.

**Try it:** [scholarsec.gquetel.fr](https://scholarsec.gquetel.fr)

See the full list of venues in [`data/conferences.yml`](data/conferences.yml).

**Note:** Source strings are heuristics. While some precisely capture all papers from a conference, others may return incomplete results.  Google Scholar's `source:` field has a maximum length, which sometimes forces the use of shorter, incomplete substrings. For instance: `source:"International Conference on Trust, Security and Privacy in Computing and Communications"` does not return anything, while `source:"International Conference on Trust"` works. 

Missing a conference? PRs are welcome to add new entries.

## Forking

If you fork this project, remove the Plausible Analytics script tag in `index.html` (line starting with `<script defer data-domain=...`). It points to a self-hosted [Plausible](https://plausible.io/) instance used to collect privacy-friendly, cookie-free usage analytics for the original site. Leaving it in would send traffic data from your fork to my instance...

### Finding the correct source strings

Finding the right Scholar `source:` string is a bit of trial and error. For a given conference:

1. Search for the latest proceedings on Google Scholar.
2. Try the full proceedings name as a `source:"..."` filter.
3. Filter by date to isolate a single proceeding and sanity-check the result count to verify that the string covers all papers in that proceeding.
4. If results look off, try shorter substrings — e.g. `source:"ACM SIGSAC"` works while the full conference name does not.

## Credits

Conference data follows conventions from [sec-deadlines](https://github.com/sec-deadlines/sec-deadlines.github.io). Rankings are based on the [CORE 2026 conference portal](https://portal.core.edu.au/conf-ranks/?search=security&by=all&source=ICORE2026&sort=arank&page=1).
