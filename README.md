# data-512-a7
Final Project for Data 512. Focuses on the impact of COVID-19 on domestic violence in Atlanta, Georgia.

### Author: Grant Savage

## Project Structure

```
data-512-a7
│   README.md
│   LICENSE
│   .gitignore
|   A4 Common Analysis.pdf
|   A5 Extension Plan.pdf
|   A6 Presentation.pptx
|   A7 Notebook.ipynb
|   domestic_crime_data.csv
|
└───images
│   │   Yearly_Reported_DV_Cases.png
|   |   pre_post_vaccine_domestic_violence_cases.png
|   |   monthly_domestic_violence_cases.png
|   |   pre_post_pandemic_weekly_domestic_violence_cases.png
```

## Goal of the project
To explore the impact of COVID-19 on domestic violence in Atlanta, Georgia.

## Known Limitations

## Data Sources and Description

- [Kaggle repository of Johns Hopkins University COVID-19 data](https://www.kaggle.com/antgoldbloom/covid19-data-from-john-hopkins-university?select=RAW_us_confirmed_cases.csv): COVID-19 total case number by day by county.
- [The New York Times mask compliance survey data](https://github.com/nytimes/covid-19-data/tree/master/mask-use): Mask compliance data from a survey conducted by the New York Times
    * Note: the NYT data is not applicable for A7 project, but required for A4.
- [CDC Masking Mandate by State](https://data.cdc.gov/Policy-Surveillance/U-S-State-and-Territorial-Public-Mask-Mandates-Fro/62d6-pm5i): CDC masking mandate by state 
    * Note: the CDC data is not applicable for A7 project, but required for A4.
- [Domestic Crime Data](./domestic_crime_data.csv): Domestic crime data scraped from the [Atlanta Police Department's weekly crime reports](https://www.atlantapd.org/i-want-to/crime-data-downloads). This data consists of the reported number of domestic violence cases in Atlanta Georgia from January 2018 to November 2021. The data structure of this file was created by me and is as follows:

|Column        | Description                                              |
|--------------|----------------------------------------------------------|
|Week          | The week number from 1 to 52                             |
|weekly_21     | The weekly reported domestic violence cases in 2021      |
|weekly_20     | The weekly reported domestic violence cases in 2020      |
|weekly_19     | The weekly reported domestic violence cases in 2019      |
|weekly_18     | The weekly reported domestic violence cases in 2018      |
|ytd_21        | The year to date reported domestic violence cases in 2021|
|ytd_20        | The year to date reported domestic violence cases in 2020|
|ytd_19        | The year to date reported domestic violence cases in 2019|
|ytd_18        | The year to date reported domestic violence cases in 2018|

- The dataframe "mcc_cobb" is used to plot COVID-19 cases was created using the John Hopkins University COVID-19 dataset and has the following format:

|Column                | Description                                                                                                           |
|----------------------|-----------------------------------------------------------------------------------------------------------------------|
|Date                  | Python Timestamp Datetime used as index                                                                               |
|confirmed_cases       | The cumulative total confirmed cases of COVID-19                                                                      |
|ma                    | The 7 day moving average of cumulative total confirmed cases of COVID-19                                              |
|ma_delta              | The diff of ma. This represents smoothed daily cases                                                                  |
|at_risk_pop           | The population of the county minus the confirmed cases                                                                |
|infection_rate        | Assumes people are infected for 14 days. This is the 14 day rolling sum of ma_delta divided by the at risk population.|
|infection rate delta  | The diff of infection_rate                                                                                            |
|infected              | The total number of infected population, assuming a 14 day infection.                                                 |

- The dataframe "ts" is used to plot domestic violence cases was created using the dataset I created from the APD reports and has the following format:
|Column          | Description                                                                   |
|----------------|-------------------------------------------------------------------------------|
|Date            | The date the data was captured                                                |
|Year            | The year the data was captured                                                |
|pandemic_status | indicator of whether the data was captured prepandemic or during the pandemic |
|weekly_cases    | The weekly reported domestic violence cases                                   |

## License and Terms of Use
- [Kaggle repository of Johns Hopkins University COVID-19 data](https://www.kaggle.com/antgoldbloom/covid19-data-from-john-hopkins-university?select=RAW_us_confirmed_cases.csv) is licnesed under Attribution 4.0 International (CC BY 4.0).
- License for [The New York Times mask compliance survey data](https://github.com/nytimes/covid-19-data/tree/master/mask-use) can be found [here](https://github.com/nytimes/covid-19-data/blob/master/LICENSE). It allows for non-commercial use and requires credit to New York Times. 
- [CDC Masking Mandate by State](https://data.cdc.gov/Policy-Surveillance/U-S-State-and-Territorial-Public-Mask-Mandates-Fro/62d6-pm5i) is available for public use.
