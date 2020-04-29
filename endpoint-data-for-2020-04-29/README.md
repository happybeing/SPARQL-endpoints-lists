# SPARQL Endpoints Analysis 29-April-2020
This directory contains all the files used as sources for testing of 773 unique SPARQL endpoint URLs which were collected within a couple of days of the date above.

It also contains various files which were created manually in order to feed the URLs into a SPARQL interrogation app part of [Visualisation Lab](https://github.com/theWebalyst/visualisation-lab) (VisLab).

VisLab includes a SPARQL endpoint interrogator into which you can paste a set of endpoint URLs. After it has updated the table of results they can be copied to the clipboard in CSV format for import into a spreadsheet. 

These results have been provided for every endpoint tested as a set of spreadsheet files, and a set of text files for easier access to the endpoint URLs. Note that VisLab can also be used to copy the URLs from its table to the clipboard in JavaScript format (after updating the table).

## Spreadsheet Results
The spreadsheet (ODS) files contain two tables, one for http URLs and one for https URLs showing the results of the tests for each URL, and including a 'Summary' column which classifies the URLs as working or non-working SPARQL endpoints (or 'Invalid' for reporting the response type incorrectly).

## Text files of URLs
The spreadsheet results were then used to create a final set of text files containing the SPARQL endpoint URLS, one per line, which can be copied and pasted into the SPARQL interrogator within VisLab in order to repeat the tests or to obtain them in JavaScript format (via the clipboard). 

The 'final' set of text files are separated into good/bad and http/https endpoints.

## Source Files
The `./inputs` subdirectory contains source files obtained from various places on the internet summarised here:

- **Wikidata:**		   98 SPARQL endpoints (28/04/20) ([SPARQL Endpoints list](https://www.wikidata.org/wiki/Wikidata:Lists/SPARQL_endpoints))
- **sparqls:**		446 SPARQL Endpoint 29/04/20 ([github json](https://github.com/pyvandenbussche/sparqles/blob/master/endpoints.json))
- **LodCloud OL:**	394 SPARQL endpoints 28/04/20 (URI burner [query as Json](https://linkeddata.uriburner.com/sparql?default-graph-uri=&query=select+distinct+%0D%0A%23%3Fs2+as+%3Fstatus%0D%0A%3Fs3+as+%3Fendpoint%0D%0A%23+from+%3Chttps%3A%2F%2Fgithub.com%2FSmartDataAnalytics%2Flodservatory%2Fraw%2Fmaster%2Flatest-status.ttl%3E++%0D%0Awhere%0D%0A{+%0D%0A++optional+{++%3Fs1+%3Chttp%3A%2F%2Fwww.w3.org%2F2007%2F05%2Fpowder-s%23describedby%3E+%3Fs6}+.%0D%0A++filter+(%3Fs6+%3D+%3Chttps%3A%2F%2Flinkeddata.uriburner.com%2Fabout%2Fid%2Fentity%2Fhttps%2Fgithub.com%2FSmartDataAnalytics%2Flodservatory%2Fraw%2Fmaster%2Flatest-status.ttl%3E)+%0D%0A++%23+optional+{%3Fs1+a+%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Fsparql-service-description%23Service%3E+}+.%0D%0A++optional+{%3Fs1+%3Chttps%3A%2F%2Fschema.org%2FserverStatus%3E+%3Fs2}+.%0D%0A++optional+{%3Fs1+%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Fsparql-service-description%23endpoint%3E+%3Fs3}+.%0D%0A++optional+{%3Fs1+%3Chttp%3A%2F%2Fschema.org%2Fpublisher%3E+%3Fs4}+.%0D%0A++optional+{%3Fs1+%3Chttp%3A%2F%2Fschema.org%2Fname%3E+%3Fs5+}.%0D%0A}%0D%0Aorder+by+desc+(%3Fs2)%0D%0A&should-sponge=&format=text%2Fhtml&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=30000000&format=json))
- **LOD Cloud net:**	567 SPARQL Endpoints 28/04/20 plus many RDF URIs from lod-cloud.net with updates to 2019 (28/04/20) ([Json file](https://lod-cloud.net/lod-data.json))
- **DataHub:** 		719 SPARQL Endpoints (28/04/20) from DataHub with updates to 2019 ([SPARQL endpoints query](https://old.datahub.io/api/2/search/resource?format=api/sparql&all_fields=1&limit=10000))
- **2013 Paper:** 	427 SPARQL Endpoints (28/04/20) from 2013 paper: *SPARQL Web-Querying Infrastructure: Ready for Action?* ([download PDF](http://aidanhogan.com/docs/epmonitorISWC.pdf))

## Processing Files

The `./processing` subdirectory contains files produced merging, sorting and evaluating the enpoints extracted from the above source files. These include:

```
all-endpoints-20-04-29-https.txt	Total inc duplicates:    118
all-endpoints-20-04-29-http.txt	Total inc duplicates: 2,210
all-endpoints-20-04-29.txt		Total inc duplicates: 2,328
-> reduce to:
all-endppoints-89-unique-HTTPS-URIs-20-04-29.txt 	Total unique:    89 https
all-endppoints-684-unique-HTTP-URIs-20-04-29.txt	Total unique: 684 http
all-endppoints-773-unique-URIs-20-04-29.txt 		Total unique: 773
-> raw CSV:
all-endppoints-89-unique-HTTPS-URIs-20-04-29.csv 	Total unique:    89 https
all-endppoints-684-unique-HTTP-URIs-20-04-29.csv	Total unique: 684 http
-> Spreadsheeds (http & https):
all-endpoints-773-unique-URLs-200429.ods 			Total unique: 773
all-endpoints-773-unique-URLs-200429-sorted-by-summary.ods
```

## Results

### Spreadsheets
The results are provided in several kinds of file:
- raw VisLab output in two CSV files (one for http and one for https endpoints)
- a spreadsheed containing a table for http and a table for https Endpoints (sorted by endpoint domain)
- the same spreadsheet, but sorted by endpoint result 'Summary'

### Final URL lists
Finally, the URLs have been copied from the spreadsheets into files which just contain the endpoint URLs in different categories, which can easily be copied and pasted back into VisLab for further testing.

```
final-good-http-endpoints-222-unique.txt
(includes 4 'Invalid' due to reporting response type incorrectly)

final-good-https-endpoints-54-unique.txt
final-bad-http-endpoints-462-unique.txt
final-bad-https-endpoints-35-unique.txt
```