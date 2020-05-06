# SPARQL Endpoints Lists and Analysis

This repository provides lists of SPARQL endpoints which have been tested using a SPARQL endpoint interrogator (part of [Visualisation Lab](https://github.com/theWebalyst/visualisation-lab)).

Following an initial analysis in April 2020, further updates may be made from time to time as new endpoints are added to the master list. Each update is summarised below with the full data available as follows:

- [endpoint-data-latest](https://github.com/theWebalyst/SPARQL-endpoints-lists/tree/master/endpoint-data-latest): contains the most recent list of endpoints and the results of the most recent tests (summarised below).

- [endpoint-data-for-2020-04-29](https://github.com/theWebalyst/SPARQL-endpoints-lists/tree/master/endpoint-data-for-2020-04-29): contains the results of the first interrogation tests along with the sources used to generate the first list of endpoints tested.

# Analyses Log
Below is a short summary of each SPARQL endoint interrogation, beginning with the most recent.

## Analysis 6-May-2020
Added some new URIs and new interrogatory queries, fixed some issues in the VisLab interrogator and corrected URLs which depended on having a trailing
slash.

As a result the numbers of active endpionts in both http and https datasets have increased.

### Results
<table>
<tr><td></td><td>http</td><td>https</td><td>Total</td></tr>
<tr><td>Tested:</td><td>726</td><td>104</td><td>830</td></tr>
<tr><td>Working:</td><td>264</td><td>72</td><td>336</td></tr>
<tr><td>Not working:</td><td>462</td><td>32</td><td>494</td></tr>
</table>

Note: a few URLs appear in both http and https lists, so the Total figure may be larger than the actual number of unique endpoints.

## Analysis 30-April-2020

An analysis including 782 URLs (an extra 11 discovered through web searches). 255 appear to be functioning SPARQL endpoints or the 782 tested.

**Details:** [SPARQL Endpoints Analysis 30-April-2020](https://github.com/theWebalyst/SPARQL-endpoints-lists/tree/master/endpoint-data-for-2020-04-30)

## Analysis 29-April-2020

An analysis of the inputs collected on or shortly before 29-April-2020 identified 773 unique SPARQL endpoint URLs from an initial set of over 2,200.

These results have been provided for every endpoint tested as a set of spreadsheet files, and as set of text files for easier access to the endpoint URLs. Note that VisLab can also be used to copy the URLs from its table to the clipboard in JavaScript format (after updating the table).

**Details:** [SPARQL Endpoints Analysis 29-April-2020](https://github.com/theWebalyst/SPARQL-endpoints-lists/tree/master/endpoint-data-for-2020-04-29)

## Notes

1. Separate tests are carried out for http and https URLs from http and https hosted versions of VisLab.
2. Tests are carried out using a browser plugin to disable CORS pre-flight checks in the browser. This avoids some issues with active endpoints, but cannot prevent errors where the server is configured to disallow CORS, or where a redirect occurs.  This is one of the drawbacks of testing from a web app in a browser rather than a desktop application, although with the prevalence of browser based applications for Linked Data, the results are useful in that they will tend to show failures for endpoints that are not accessible from the browser even when a CORS plugin is being used to disable pre-flight checks. The issue with redirects is because as of May 2020, modern browsers do not yet allow CORS for redirects (a late addition to the CORS specification).

