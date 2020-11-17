# A2-hcds-hcc-chki

## About the project
This project aims to visualize the number of page views on English Wikipedia from January in 2008 to October in 2020. Views on desktop, mobile devices and the total amount of views are considered.

### Structure of the project
* data_raw -> contains raw json data retrieved from the API
* data_clean -> contains the cleaned up data that was the basis for the analysis
* results -> contains results of the analysis (the visualization)
* src -> contains the source code (jupyter notebook) used for data aquisition, data cleaning and the analysis
* LICENSE -> License information - This project is licensed under the [MIT license](https://mit-license.org/)
* README -> The file you are reading right now :)
* poetry.lock and pyproject.toml -> These files make it easy to run this project (see 'How to run the code')

### How to run the code

1. Clone the repository and go to the root folder of the project (all the following commands have to be run there)

1. Run `poetry install` in the root folder of the project to install all dependencies

1. After the installation is finished, run `poetry shell` to enter a shell in which all dependencies are installed

1. Run `jupyter notebook` to open the project in your browser.


## About the data

### Data source (API)
The data was retrieved using the different endpoints of an API developed by the Wikimedia Foundation that serves analytical data.

#### License
[License of the source data](https://creativecommons.org/publicdomain/zero/1.0/)

#### Terms and conditions
* [Wikimedia Foundation REST API terms of use](https://www.mediawiki.org/wiki/Wikimedia_REST_API#Terms_and_conditions)

#### Documentation and endpoints
* [Legacy Pagecounts Documentation](https://wikitech.wikimedia.org/wiki/Analytics/AQS/Legacy_Pagecounts) and  [Legacy Pagecount Endpoint](https://wikimedia.org/api/rest_v1/#/Legacy%20data)
* [Pageviews Documentation](https://wikitech.wikimedia.org/wiki/Analytics/AQS/Pageviews) and [Pageviews Endpoint](https://wikimedia.org/api/rest_v1/#/Pageviews%20data)

### Description of the cleaned data
Header and content of the table that contains the cleaned data:

| year | month |pagecount_all_views|pagecount_desktop_views|pagecount_mobile_views|pageview_all_views|pageview_desktop_views|pageview_mobile_views|
|------| ------|-------------------|-----------------------|----------------------|------------------|----------------------|---------------------|
| YYYY | MM    |num_views          |num_views              |num_views             |num_views         |num_views             |num_views            | 

* year and month - together these columns indicate for which month and year the views were retrieved
* pagecount_desktop_views - monthly desktop views from Pagecounts API from 01.01.2008 to 01.07.2016 
* pagecount_mobile_views - monthly mobile views from Pagecounts API from 01.01.2014 to 01.07.2016 
* pagecount_all_views - sum of monthly mobile and desktop views from Pagecounts API
* pageview_desktop_views  monthly desktop views from Pageviews API from 01.07.2015 to 01.10.2020
* pageview_mobile_views - monthly mobile views from Pageviews API from 01.07.2015 to 01.10.2020
* pageview_all_views - sum of monthly mobile and desktop views from Pageviews API


#### Important notes 
* The Pageview API excludes spiders/crawlers, while data from the Pagecounts API does not.
* There is an overlap of the data from the Pagecounts and Pageviews API
* Data about mobile views exists since January 1st, 2014
* The views were retrieved on a monthly basis.
