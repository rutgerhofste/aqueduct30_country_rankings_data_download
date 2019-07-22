# Aqueduct 3.0 Country and Province Rankings  
2019 update based on Aqueduct 3.0 data  
 ** EMBARGO 6th August 2019 at 0601 cet/0501 bst **   

## Results
[Download xlsx](https://wri-projects.s3.amazonaws.com/Aqueduct30/finalData/Y2019M04D15_RH_GA_Aqueduct_Results_Clean_V01/Y2019M07D17_RH_GA_Aqueduct30_Rankings_V01.xlsx)

## Instructions
If you haven't opened the excel file, click the download excel link above. 

When you open the file, you will see multiple sheets. Click the sheets to display country or province results. 

![sheets](https://github.com/rutgerhofste/aqueduct30_country_rankings_data_download/raw/master/images/tabs.JPG)

The most important columns:  

| Column name | Description |
| ------------- | ------------- |
| name_0 | country name |
| score | water stress score [0-5] | 
|score_ranked | water stress scores ranked from 1 (highest water stress score) to 165 (lowest water stress score) |
| label | interpretation of the water stress score. |  

A full list of all column names can be found below. 

The results at a country level will look like this

![country_rankings](https://github.com/rutgerhofste/aqueduct30_country_rankings_data_download/raw/master/images/country_rankings.JPG)

There are 17 extremely high water stressed countries and 27 high stressed countries. 


Next, filtering.  
You can use the arrows at each columns to filter and sort the data. For example, in the province rankings, you can view a sigle country by clicking on the country name column (name_0) 

![sheets](https://github.com/rutgerhofste/aqueduct30_country_rankings_data_download/raw/master/images/filters.JPG)

Please note that the default filter view is for baseline water stress (bws) with the total withdrawal (tot) as gridded weights. To change the filter, clear **both** filters by clicking the dropdown and "clear". After no filter is applied, select a new indicator / weight combination. See the gridded weights table above for valid combinations of indicator and weights. As a final step, you can sort the table by clicking "score_ranked" and "Sort Smallest to Largest"

![Clear indicator](https://github.com/rutgerhofste/aqueduct30_country_rankings_data_download/raw/master/images/clear_indicator_v01.JPG)
![Clear weight](https://github.com/rutgerhofste/aqueduct30_country_rankings_data_download/raw/master/images/clear_weight.JPG)



## Baseline water stress

Baseline water stress measures the ratio of total water
withdrawals to available renewable surface and groundwater
supplies. Water withdrawals include domestic,
industrial, irrigation, and livestock consumptive and
nonconsumptive uses. Available renewable water supplies
include the impact of upstream consumptive water
users and large dams on downstream water availability.
Higher values indicate more competition among
users.

For more information, ask the Aqueduct team. The methodology document is almost ready. 




The updated country and province data builds on the previous version: 
[“a weighted aggregation of spatially distinct hydrological indicators”](https://wriorg.s3.amazonaws.com/s3fs-public/aqueduct_coutnry_rankings_010914.pdf) with updated data, updated weights and different spatial units.
In addition, the results are simplified to resonate better with the users. The method has three input datasets:
1.	Source indicators  
1.	Gridded (pixel) weights; and  
1.	Target regions (countries, provinces).  

## Source indicators

See Aqueduct 3.0 [metadata](https://github.com/wri/aqueduct30_data_download/blob/master/metadata.md) for a description of these indicators and the methodology.

Baseline water stress
Drought risk
Riverine flood rik

## Gridded weights

For baseline water stress and drought risk, we used sectoral and total gross water withdrawal as weights. Gross withdrawal is the same as in the Aqueduct™ water risk atlas. It is based on the hydrological model PCR-GLOBWB 2 over a period of 1960-2014. For more information, see the main reference. The sectors include: domestic, industrial, irrigation and livestock. The total is the simple sum of the four sectors. 

For riverine flood risk, gridded population is used as weights. See the main Aqueduct Floods reference for more info.

| Source indicator      | Total gross withdrawal | Domestic gross withdrawal | Industrial gross withdrawal | Irrigation gross withdrawal | Livestock gross withdrawal | Population | 
|-----------------------|------------------------|---------------------------|-----------------------------|-----------------------------|----------------------------|------------| 
| Baseline water stress | 1                      | 1                         | 1                           | 1                           | 1                          |            | 
| Drought risk          | 1                      | 1                         | 1                           | 1                           | 1                          |            | 
| Riverine flood risk   |                        |                           |                             |                             |                            | 1          | 



## Target regions

Aqueduct™ data is aggregated up to two spatial units: countries and sub-national units. Sub national unites can be states, provinces, prefectures etc. depending on the country. We used GADM level 0 (country) and GADM level 1 (state/province).  

The gridded weights and target regions are resampled to 30 arc seconds resolution.











### Columns

| Column name | type | Description |
| --- | --- | ---|
| gid_1 | string | GADM level 1 unique identifier for sub national level. Only available in province rankings|
| name_1 |string | GADM level 1 name. Name of the sub-national level. State in the US, Province in the Netherlands etc. |
| iso_a3 | string| ISO alphabetical code for country |
| iso_n3 | integer | ISO numerical code for country |
| primary | boolean | Primary Country i.e. UN member. | 
| name_0 | string | GADM level 0 name. Name of national level |
| indicator_name| string | Indicator name. Corresponds to Aqueduct 3.0 indicator names. See table below |
| weight | string | Weighting scheme used, see below |
| score | float | score for indicator, weight combination. Values 0-5 |
| score_ranked | integer | Score ranked, ascending |
| cat | integer | Category, can be used for visualizing the data |
| label | string | Label of category, depends on indicator. Same labels as in Aqueduct 3.0 Water Risk Atlas |
| sum_weights | float |  Sum of the weights (tot, ind etc.). Result of zonal statistics |
| sum_weighted_indicator | float | Sum of the weights * indicator scores. Result of zonal statistics |
| count_valid" | float | number of valid pixels. Valid if weight and indicator score are valid |
| fraction_valid | float | fraction of geometry with valid pixels. Used to mask out invalid geometries |
| valid_hybas6| boolean | True if hydrology is valid, false otherwise |
| un_region | string | name of UN region |
| wb_region | string | name of World Bank region |
| population_2019_million | float | Country population according to UN in 2019 |


#### Indicators
| Short    | Full |
|-------------|-----|
|**bws**| Baseline water stress|  
|**bwd**| Baseline water depletion|  
|**iav**| Interannual variability|  
|**sev**| Seasonal variability|  
|**rfr**| Riverine flood risk|  
|**drr**| Drought risk|



#### Weights
| Short    | Full |
|-------------|-----|
|**tot**| Total gross withdrawal|  
|**dom**| Domestic gross withdrawal|  
|**ind**| Industrial gross withdrawal|  
|**irr**| Irrigation gross withdrawal|  
|**liv**| Livestock gross withdrawal|  
|**pop**| Population|  
|**one**| Ones, i.e. no weights |  

## Known caveats

In the province rankings, the geometry for Magallanes y Antártica Chilena is split into two due to the maximum number of vertices in Google Earth Engine. You can use either one.

## Other formats:
for analysts or tool developers:  
S3://wri-projects/Aqueduct30/finalData/Y2019M04D15_RH_GA_Aqueduct_Results_V01 

direct links (version 05):  
[country  csv file for analysts or developers](https://wri-projects.s3.amazonaws.com/Aqueduct30/finalData/Y2019M04D15_RH_GA_Aqueduct_Results_V01/output_V05/Y2019M04D15_RH_GA_Aqueduct_Results_V01_country_V05.csv)   
[province csv file for analysts or developers](https://wri-projects.s3.amazonaws.com/Aqueduct30/finalData/Y2019M04D15_RH_GA_Aqueduct_Results_V01/output_V05/Y2019M04D15_RH_GA_Aqueduct_Results_V01_province_V05.csv)  


Encoding: UTF-8  

