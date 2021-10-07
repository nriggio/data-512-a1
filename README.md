# Monthly Traffic on English Wikipedia 
Data 512: A1 - Data Curation

<!-- ABOUT THE PROJECT -->
## About the Project:
The goal of this project is to construct, analyze, & publish a dataset of monthly traffic on English Wikipedia from January 1, 2008 - September 30, 2021. This culminates in a timeseries visualization showing data across two relevant APIs (Legacy Pagecount & Pageview) and is broken down by traffic type (desktop, mobile, all).

This project is meant to be fully reproducible by others, this includes all steps from acquiring the data to producing the png of the final timeseries.

<!-- PREREQUISITES -->
## Prerequisites:

* pandas
* numpy
* matplotlib.pyplot
* matplotlib.dates
* json
* requests

<!-- PROJECT STRUCTURE -->
## Project Structure:

The raw & processed data is stored in the `data` directory (see Data header below for description), any processing or analysis is done in a jupyter notebook (`hcds-a1-data-curation.ipynb`), and the final timeseries plot is stored in `wiki_timeseries.png`.

```
.
├── LICENSE
├── README.md
├── data
│   ├── pagecounts_desktop-site_200712-202109.json
│   ├── pagecounts_mobile-site_200712-202109.json
│   ├── pageviews_desktop_200712-202109.json
│   ├── pageviews_mobile-web_200712-202109.json
│   ├── pageviews_mobile-app_200712-202109.json
│   ├── en-wikipedia_traffic_200712-202109.csv
├── hcds-a1-data-curation.ipynb
└── wiki_timeseries.png
```

<!-- DATA -->
## Data:

### Raw Data:

The raw data is contained in 5 JSON files formatted as follows:
* Filename: `apiname_accesstype_firstmonth-lastmonth.json`
* Data Structure:
    |     Column         | Value                                   | Description |
    |--------------------|-----------------------------------------|-------------|
    | project            | en.wikipedia                            |             |
    | access/access-site | desktop, mobile, mobile-web, mobile-app |             |
    | agent              | user                                    |             |
    | granularity        | monthly                                 |             |
    | timestamp          | YYYYMMDDHH                              |             |
    | views/count        | integer                                 |             |


### Processed Data:
* Filename: `en-wikipedia_traffic_200712-202108.csv`
* Data Structure:
    |     Column              | Value        |
    |-------------------------|--------------|
    | year                    | YYYY         |
    | month                   | MM           |
    | pagecount_all_views     | num_views    |
    | pagecount_desktop_views | num_views    |
    | pagecount_mobile_views  | num_views    |
    | pageview_all_views      | num_views    |
    | pageview_desktop_views  | num_views    |
    | pageview_mobile_views   | num_views    |

<!-- LICENSE -->
## License:

Distributed under the MIT License. See `LICENSE.txt` for more information.


<!-- CONTACT -->
## Contact:

Nicole Riggio - riggionicole@gmail.com

Project Link: [https://github.com/nriggio/data-512-a1](https://github.com/nriggio/data-512-a1)


<!-- ACKNOWLEDGMENTS -->
## Acknowledgments:

* [A1: Data Curation Assignment](https://docs.google.com/document/d/1groRZyhgOwBxlSyE4vKEhYa-khKet8iWVaVDAgOH_Y4/edit#)
* [Sample API Code](https://public.paws.wmcloud.org/User:Jtmorgan/data512_a1_example.ipynb)
* [Wikimedia REST API Documentation](https://www.mediawiki.org/wiki/Wikimedia_REST_API)
* [Wikimedia Legacy Pagecount API](https://wikimedia.org/api/rest_v1/#/Legacy%20data/get_metrics_legacy_pagecounts_aggregate__project___access_site___granularity___start___end_)
* [Wikimedia Pageview API](https://wikimedia.org/api/rest_v1/#/Pageviews_data/get_metrics_pageviews_aggregate_project_access_agent_granularity_start_end)
* [MIT License](https://opensource.org/licenses/MIT)
* [Best-README-Template: othneildrew](https://github.com/othneildrew/Best-README-Template)

