<table>
  <tr>
    <th>Title</th>
    <th>Author</th>
    <th>Date</th>
  </tr>
  <tr>
    <th>WesleyLife Meals on Wheels Expansion: STAT 172 Final Project</th>
    <th>Anthony Esboldt, Jason Nguyen, Eric Pfaffenbach, Riley Schultz</th>
    <th>12/12/2024</th>
  </tr>
</table>
<h1>Introduction</h1>
<p>This repository contains the code and data required to reproduce the results of the WesleyLife Meals on Wheels Expansion recommendations completion in STAT 172: Data Mining and General Linear Models. Specifically, the code to produce a linear model and create choropleth maps to visualize food insecurity in the state of Iowa.</p>
<h1>Requirements</h1>
<p>To install the required packages, run the following code in R:<br>
<br>
install.packages(c("tidyverse", "pROC", "glmnet", "lubridate", "sf", "tigris", "ggplot2", "rmapshaper", "ggthemes", "logistf", "haven"))</p>

<h1>Data</h1>
<p>We used three sources of data to train our model and then make predictions on. The dataset we used to train and fine tune our model comes from the Current Population Survey(CPS) completed by IPUMS(Integrated Public Use Microdata Series). This data provides us with a variety of demographic data about individuals and different food insecurity measures. this file is named as "cps_00006.csv" in the data files folder.</p>
<br>
<p>We also used data from the American Community Survey(ACS) This data contains Supplemental Poverty Measures, including many of the same variables as the CPS data. The key to using the ACS data was the inclusion of PUMA, which gives us geographical locations for food insecurity. Due to the file size, I am unable to upload it into the repository, but the SAS dataset can be downloaded at <a href="https://www.census.gov/data/datasets/time-series/demo/supplemental-poverty-measure/acs-research-files.html">this link</a>.</p>
<br>
<p>The final dataset we used is the file "total_iowa_seniors_by_puma.csv". This dataset allowed us to make predictions on the estimated number of seniors facing food insecurity. We used the proportions that we get from our predictions in order to estimate total senior facing food insecurity by PUMA.</p>
<h1>Reproduce</h1>
<p>1. After the files are downloaded, you have to change the file path for each of the datasets and the r files that are being sourced.</p>
<p>2. Run clean_cps.R to get the clean version of the CPS dataset.</p>
<p>3. Run both predict_FSBAL.R and predict_wrouty.R to get the predictions based on the CPS data.</p>
<p>4. Run ACSCleaning.R to get the cleaned version of the ACS dataset.</p>
<p>5. Run ACS_FSBAL.R and ACS_WROUTY.R to get the results and the choropleth maps for food insecurity.</p>
