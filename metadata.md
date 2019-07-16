# Aqueduct 3.0 Country and Province Rankings
2019 update based on Aqueduct 3.0 data


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
| riverine flood risk   |                        |                           |                             |                             |                            | 1          | 



## Target regions

Aqueduct™ data is aggregated up to two spatial units: countries and sub-national units. Sub national unites can be states, provinces, prefectures etc. depending on the country. We used GADM level 0 (country) and GADM level 1 (state/province).  

The gridded weights and target regions are resampled to 30 arc seconds resolution.


## Results
Results are on Amazon S3://wri-projects/Aqueduct30/finalData/Y2019M04D15_RH_GA_Aqueduct_Results_V01 




