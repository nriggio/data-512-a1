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


<!-- SPECIAL CONSIDERATIONS -->
## Special Considerations:

Note that the data from the Pageview API is filtered to only include `user` data (i.e. eliminating "inorganic" traffic from spiders/crawlers). This option does not exist for the Pagecount API and therefore is likely included in this analysis.

When looking at `wiki_timeseries.png` for the final timeseries plot, note that until late 2014, we do not have any mobile views so the Pagecount-All and Pagecount-Desktop lines overlap exactly. Also note the scale on the y-axis (which shows views on the order of 1E10) and the switch from dashed to solid lines representing the transition from the legacy Pagecount API to the Pageview API.


<!-- DATA -->
## Data:

### Raw Data:

The raw data is contained in 5 JSON files formatted as follows:
* Filename: `apiname_accesstype_firstmonth-lastmonth.json`
* Data Structure:
    |     Column         | Value                                   | Description |
    |--------------------|-----------------------------------------|-------------|
    | project            | en.wikipedia                            | Represents the Wikimedia project we are viewing. In this case all data is from English Wikipedia.            |
    | access/access-site | desktop, mobile, mobile-web, mobile-app | The Pageview API refers to this as access with options of desktop, mobile-web, or mobile-app. The Pagecount API calls this access-site and the value is either desktop or mobile.             |
    | agent              | user                                    | This flag is only present for the Pageview API. We have filtered to `user` as we are only focused on organic traffic data.            |
    | granularity        | monthly                                 |  The data for each API call is bucketed monthly.           |
    | timestamp          | YYYYMMDDHH                              |              |
    | views/count        | integer                                 | The Pageview API uses `views` while the Pagecount API uses `count`, both represent the number of views in a given time period.             |


### Processed Data:
* Filename: `en-wikipedia_traffic_200712-202108.csv`
* Data Structure:
    | Column                  | Value     | Description                                  |
    |-------------------------|-----------|----------------------------------------------|
    | year                    | YYYY      |                                              |
    | month                   | MM        |                                              |
    | pagecount_all_views     | num_views | All traffic data from the Pagecount API.     |
    | pagecount_desktop_views | num_views | Desktop traffic data from the Pagecount API. |
    | pagecount_mobile_views  | num_views | Mobile traffic data from the Pagecount API.  |
    | pageview_all_views      | num_views | All traffic data from the Pageview API.      |
    | pageview_desktop_views  | num_views | Desktop traffic data from the Pageview API.  |
    | pageview_mobile_views   | num_views | Mobile traffic data from the Pageview API.   |


<!-- LICENSE -->
## License:

Distributed under the MIT License. See `LICENSE.txt` for more information.


<!-- CONTACT -->
## Contact:

Nicole Riggio - riggionicole@gmail.com

Project Link: [https://github.com/nriggio/data-512-a1](https://github.com/nriggio/data-512-a1)


<!-- ACKNOWLEDGMENTS -->
## Acknowledgements:

* [A1: Data Curation Assignment](https://docs.google.com/document/d/1groRZyhgOwBxlSyE4vKEhYa-khKet8iWVaVDAgOH_Y4/edit#)
* [Sample API Code](https://public.paws.wmcloud.org/User:Jtmorgan/data512_a1_example.ipynb)
* [Wikimedia REST API Documentation](https://www.mediawiki.org/wiki/Wikimedia_REST_API)
* [Legacy Pagecount API Endpoint](https://wikimedia.org/api/rest_v1/#/Legacy%20data/get_metrics_legacy_pagecounts_aggregate__project___access_site___granularity___start___end_)
* [Pageview API Endpoint](https://wikimedia.org/api/rest_v1/#/Pageviews_data/get_metrics_pageviews_aggregate_project_access_agent_granularity_start_end)
* [Legacy Pagecount API Documentation](https://wikitech.wikimedia.org/wiki/Analytics/AQS/Legacy_Pagecounts)
* [Pageview API Documentation](https://wikitech.wikimedia.org/wiki/Analytics/AQS/Pageviews)
* [MIT License](https://opensource.org/licenses/MIT)
* [Best-README-Template: othneildrew](https://github.com/othneildrew/Best-README-Template)

