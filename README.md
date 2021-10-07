# Monthly Traffic on English Wikipedia 
## January 1, 2008 - September 30, 2021
Data 512: A1 - Data Curation

<!-- ABOUT THE PROJECT -->
## About the Project:
Construct, analyze, & publish a dataset of monthly traffic on English Wikipedia from January 1, 2008 - September 30, 2021.

This project is meant to be fully reproducible by others, this includes all steps from acquiring the data to producing the png of the final timeseries.

<!-- PREREQUISITES -->
### Prerequisites:

* pandas
* numpy
* matplotlib.pyplot
* matplotlib.dates
* json
* requests

<!-- PROJECT STRUCTURE -->
## Project Structure:

### Project Structure

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


------------------------------
<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/othneildrew/Best-README-Template.svg?style=for-the-badge
[contributors-url]: https://github.com/othneildrew/Best-README-Template/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/othneildrew/Best-README-Template.svg?style=for-the-badge
[forks-url]: https://github.com/othneildrew/Best-README-Template/network/members
[stars-shield]: https://img.shields.io/github/stars/othneildrew/Best-README-Template.svg?style=for-the-badge
[stars-url]: https://github.com/othneildrew/Best-README-Template/stargazers
[issues-shield]: https://img.shields.io/github/issues/othneildrew/Best-README-Template.svg?style=for-the-badge
[issues-url]: https://github.com/othneildrew/Best-README-Template/issues
[license-shield]: https://img.shields.io/github/license/othneildrew/Best-README-Template.svg?style=for-the-badge
[license-url]: https://github.com/othneildrew/Best-README-Template/blob/master/LICENSE.txt
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: https://linkedin.com/in/othneildrew
[product-screenshot]: images/screenshot.png
