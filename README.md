The dataset included in this repository provides an estimate of winter soil cover before spring-sown crops at municipality level for mainland France for two years (2018 and 2019). These estimates were obtained through the monitoring of all fields with spring-sown crops, declared within the context of the European Common Agricultural Policy. For each of these fields, the soil cover rate during the winter prior to sowing spring crops was estimated from the computation of the Normalized Difference Vegetation Index (NDVI) from multi-spectral images.

The NDVI is especially appropriate for monitoring winter soil cover because, contrary to biomass, soil cover has a linear relationship with NDVI (see **Figure 1** below). 
<p align="center" text-align="center">
<img src="https://github.com/BjnNowak/WinterSoilCover/blob/main/figures/Figure1.png" alt="Estimation of soil cover by vegetation from the Normalized Difference Vegetation Index (NDVI). Based on the literature, a 50% soil cover corresponds to a threshold NDVI value between 0.45 and 0.59." width="500"/>
</p>

<div align="center"><b>Figure 1</b> <i>Estimation of soil cover by vegetation from the Normalized Difference Vegetation Index (NDVI).<br>Based on the literature, a 50% soil cover corresponds to a threshold NDVI value between 0.45 and 0.59.</i>
</div>
<br>


The field was considered covered if NDVI exceeded a given threshold. Soil characteristics, such as colour or moisture, and crop residues influence NDVI measurements, especially in the early stages of crop development, when the soil is still poorly covered. In order to limit these effects, it was therefore considered that soil cover had to exceed 50% for a field to be considered as covered by vegetation. Based on the literature, this corresponds to a threshold NDVI value between 0.45 and 0.59 (Figure 1). Thus, to facilitate the sensitivity and uncertainty analyses that can be performed from this data set, three estimates of winter soil cover are given: a minimum value (corresponding to the threshold of 0.59), a maximum value (threshold of 0.45) and a mean value (threshold of 0.52).

The NDVI computation was carried out through the Google Earth Engine platform, using Sentinel-2 multispectral images at 10 m spatial resolution, corrected to surface reflectance using Sen2Cor. For each year, winter soil cover monitoring was carried out for two months (December and January) during the winter before sowing the spring-sown crop (Figure 2). 

<p align="center">
<img src="https://github.com/BjnNowak/WinterSoilCover/blob/main/figures/Figure2.png" alt="Figure 2 Timeline for cover crop detection" width="500"/>
</p>
  
<div align="center"><b>Figure 2</b> <i>Timeline for cover crop detection</i>
</div>
<br>
  
  
December was chosen as the beginning of the study period to limit the risk of detecting unharvested spring-sown crops on the plots, such as grain maize or sugar beet that can be harvested late in the year. January was chosen as the end of the study period because some spring-sown crops, such as peas, can be sown as early as February. Furthermore, if a cover crop was present on the plot, it must have been already detected in December or January.

Two levels of filters were applied to remove invalid observations. First, for the study period, only the least cloudy images (20% threshold) were selected. Then, a second filter at the pixel scale was applied to remove observations identified as clouds, shadows or snow (using the Scene Classification map provided with Sentinel 2 observations).

Finally, results were aggregated at the municipality level. For each crop and for each commune, the total area occupied by the crop (in hectares) is specified, as well as three estimates (also in hectares) of the area covered, corresponding to the three NDVI thresholds defined above. For each crop and municipality combination, the given year corresponds to the year of harvest of the following spring crops (e.g. the year 2019 refers to the soil cover in December 2018 and January 2019).

