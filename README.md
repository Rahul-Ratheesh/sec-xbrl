sec-xbrl
========

Copyright 2014 Altova GmbH

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

  http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

-------------------------------------------------------------------------

<h2>How to download and process SEC XBRL Data Directly from EDGAR</h2>

Idea of this fork is to remove the dependency on RaptorXML server but instead use Arelle's open source platform for processing XBRL files.

In addition to the standard Python libraries, you also need to install 
+ Python feedparser module/library available here: https://pypi.python.org/pypi/feedparser
+ BeautifulSoup module/library available here: https://pypi.org/project/beautifulsoup4/

For more information on Arelle, please see here: http://arelle.org/arelle/

-------------------------------------------------------------------------

<h3>Usage Information</h3>

<h4>loadSECfilings</h4>

    loadSECfilings.py -y <year> -m <month> | -f <from_year> -t <to_year> 

These creates a subdirectory sec/ and then subsequent year-based directories and months
underneath and downloads all SEC XBRL filings from the EDGAR system to your local hard
disk for further processing. Please use only during off-peak hours in order to not
overload the SEC servers. This downloads the ZIPped XBRL filings, so you'll have one
ZIP file per filing submitted to the SEC on your drive. If you call this script
again for the current or any previous month at a later day, it will only download
any files that are new and have not yet been downloaded before.

    loadSECfilings.py -s <symbol> -d <doc_type>

This creates a subdirectory sec/symbol/doc_type and then downloads all SEC XBRL filings from the EDGAR system for the given trading symbol and the given type (10-Q, 10-K etc)

<h5>Examples</h5>

    python3 loadSECfilings.py -y 2014 -m 9

This will load all SEC filing for September 2014.

    python3 loadSECfilings.py -f 2005 -t 2014

This will load all SEC filing for the start of the XBRL pilot program in 2005 until 2014.
WARNING: If you download all years available (2005-2014) this will be about 127,000 files
and take about 18GB of data on your hard disk, so please use with caution, especially 
when you are on a slow Internet connection.

    python3 loadSECfilings.py -s AMZN -d 10-K
  

This will download all 10-K SEC filings of Amazon.


<h4>valSECfilings</h4>

Work in progress

<h5>Examples</h5>

Work in progress


-------------------------------------------------------------------------

