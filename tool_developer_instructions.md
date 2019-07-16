### Geometries

Use [GADM version 3.6](https://gadm.org/download_world.html) level 0 for country ranking. Join key: GID_0  
Use [GADM version 3.6 level](https://gadm.org/download_world.html) 1 for province ranings. Join key: GID_1  

Consider using [mapshaper](https://mapshaper.org/) to simplify the geometries for better in-browser performance. If using mapshaper, please log the settings for future reference.

### Exclude indicators

We decided to only use:

Baseline Water Stress (bws)  
Drought Risk (drr)  
Riverine Flood Risk (rfr) 

Please ignore the other indicators.  


### Visualize

Please visualize using fill and stroke colors based on the values below:

#### Baseline water stress
|label| hex |
| --- | --- | 
| 1. Low (<10%)|#FFFF99 |
|2. Low to medium (10-20%)|#FFE600 |
|3. Medium to high (20-40%)|#FF9900 |
|4. High (40-80%)|#FF1900 |
|5. Extremely high (>80%)|#990000 |
|None|#4E4E4E |
