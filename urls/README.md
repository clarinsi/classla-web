# URL Dumps

This directory contains lists of the URLs extracted from CLASSLA-web 1.0 and 2.0 corpora.

We publish:
- lists of full URLs: all URLs from each web corpus (e.g., CLASSLA-web.cnr.2.0.urls.json)
- lists of all unique domains from each web corpus (e.g., CLASSLA-web.cnr.2.0.domains.json)
- a blacklist: a list of domains from CLASSLA-web corpora that were manually identified as bad domains and removed from the curated corpora - `CLASSLA-web.blacklisted_domains.json`. The list contains 682 domains. More information on some of the domains (the source and reason for removal) is available in `CLASSLA-web-bad-domains-more-information.txt`
- information on manually-verified domains: a table with domains that have been manually verified to be okay (i.e., not automatically generated or machine translated) - `CLASSLA-web-manually-verified-domains-list.txt`

|corpus| # urls | # unique domains |
|:-----|--------|------------------|
| bg.1.0     | 7,456,186       |     86,099             |
| bg.2.0     | 14,667,915       |     63,828             |
| bs.1.0     | 1,993,891       |     8,453             |
| bs.2.0     | 2,537,973       |     7,172             |
| cnr.1.0     | 401,290       |     3,160             |
| cnr.2.0     | 786,012       |     2,801             |
|  hr.1.0    |  5,422,656      |     41,524             |
|  hr.2.0    |  5,918,208      |     30,789             |
|  mk.1.0    |  1,482,490      |     6,267             |
|  mk.2.0    |  2,111,190      |     5,207             |
|  sl.1.0    |  4,063,462      |     49,652             |
|  sl.2.0    |  4,786,328      |     33,778             |
|  sr.1.0    |  5,256,087      |     40,962             |
|  sr.2.0    |  7,232,860      |     36,171             |



## More information

Domains are created from the URLs following this code:

```python
import regex as re
import html

domain_re=re.compile(r'^https?://(?:www\.)?(.+?)[/$]')

domains = []

for curr_url in urls:
	curr_domain=html.escape(domain_re.search(curr_url).group(1))
	domains.append(curr_domain)

unique_domains = sorted(list(set(domains)))


```