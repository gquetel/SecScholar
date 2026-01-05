# sec-papers-search

This project aims at making the search of good quality papers easier. Directly querying Google Scholar can lead to an enormous amount of retrieved paper. Manually filtering good quality paper is time-consuming, however, it can be simplified using filters, notably the `source` keyword which allows to specify the venues in which the papers should be published. 

This simple repository generates a webpage where we can select cybersecurity venues or groups of cybersecurity venues and generate the according Google Scholar filter. The project can easily be forked and adapted to other domains by simply modifying the [data/conferences.yml](data/conferences.yml) file. 


## Adapting this repository to another domain

### Finding the list of conferences to include

### Finding the correct source strings
So far, finding the correct source has been a bit of a trial and error. Typically, for a conference I would:  
1. Search for the last conference occurrence's proceedings.
2. Cut the name to not include dates, and search on scholar using the source keyword for all results.
3. Filter using the date (since XXXX) to only show the papers of the last conference occurrence.
4. If the order of magnitude seems ok, the source is used.

Else, try with substrings of the proceedings full name. For instance: `source:"ACM SIGSAC Conference on Computer and Communications Security"` does not work, while `source:"ACM SIGSAC"` does.

