This directory provides information on the texts that were identified to be near-duplicates in the versions 1.0 and 2.0 of the same national CLASSLA-web corpora (e.g., CLASSLA-web.hr 1.0 and CLASSLA-web.hr 2.0).

The near-duplicated texts were identified using MinHash over word 4-grams, with a similarity threshold set to 0.7.

For each national web, one file is provided (e.g., `CLASSLA-web.bs.2.0.duplicates_with_CLASSLA-web.bs.1.0.json`), with text ids from the [CLASSLA-web 2.0 version](http://hdl.handle.net/11356/2079) as keys and lists of the ids of identified near-duplicates from CLASSLA-web 1.0 (available in JSON formats inside the [MaCoCu-genre corpus collection](http://hdl.handle.net/11356/1969)) as values.

Example:
```python
  # CLASSLA-web 2.0 text id
  "CLASSLA-web.2.0.bs.2": [
    # CLASSLA-web 1.0 text id
    "CLASSLA-web.bs.1024224"
  ],
```
