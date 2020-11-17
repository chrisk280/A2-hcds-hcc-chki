# A2-hcds-hcc-chki

## About the project
This project aims to visualize the number of page views on English Wikipedia from January in 2008 to October in 2020. Views on desktop, mobile devices and the total amount of views are considered.

### Structure of the project
* data_raw -> contains raw json data retrieved from the API
* data_clean -> contains the cleaned up data that was the basis for the analysis
* results -> contains results of the analysis (the visualization)
* src -> contains the source code (jupyter notebook) used for data aquisition, data cleaning and the analysis
* LICENSE -> License information - This project is licensed under the MIT license
* README -> The file you are reading right now :)
* poetry.lock and pyproject.toml -> These files make it easy to run this project (see 'How to run the code')

### How to run the code

1. Clone the repository and go to the root folder of the project (all the following commands have to be run there)

1. Run `poetry install` in the root folder of the project to install all dependencies

1. After the installation is finished, run `poetry shell` to enter a shell in which all dependencies are installed

1. Run `jupyter notebook` to open the project in your browser.


## About the data
* [License of the source data](https://creativecommons.org/publicdomain/zero/1.0/)

### Data source (API)
The data was retrieved using the different endpoints of an API developed by the Wikimedia Foundation that serves analytical data.

#### Terms and conditions
* [Wikimedia Foundation REST API terms of use](https://www.mediawiki.org/wiki/Wikimedia_REST_API#Terms_and_conditions)

#### Documentation and endpoints
* [Legacy Pagecounts Documentation](https://wikitech.wikimedia.org/wiki/Analytics/AQS/Legacy_Pagecounts) and  [Legacy Pagecount Endpoint](https://wikimedia.org/api/rest_v1/#/Legacy%20data)
[Pageviews Documentation](https://wikitech.wikimedia.org/wiki/Analytics/AQS/Pageviews) and [Pageviews Endpoint](https://wikimedia.org/api/rest_v1/#/Pageviews%20data)

#### Description of the cleaned data
a description of values of all fields in your final data file. \
The header of the table containing the cleaned data looks like this:

| year | month |pagecount_all_views|pagecount_desktop_views|pagecount_mobile_views|pageview_all_views|pageview_desktop_views|pageview_mobile_views|
|------| ------|-------------------|-----------------------|----------------------|------------------|----------------------|---------------------|
| YYYY | MM    |num_views          |num_views              |num_views             |num_views         |num_views             |num_views            | 

#### Important notes 
* The Pageview API excludes spiders/crawlers, while data from the Pagecounts API does not.
* The views were retrieved on a monthly basis.
