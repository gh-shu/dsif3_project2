# Project 2: Ames Housing Data and Kaggle Challenge

--- 
### 
Shuyi 
---

## Problem Statement

Property flipping is an investment strategy of purchasing a property with a short holding period with the intent of selling it for a quick profit. All investments have risks. 

To help novice property flippers manage risks, we will provide consultation upon application, based on our home valuation application that predicts the sale prices of homes in Ames, Iowa. We have modeled Linear Regression, Ridge, Lasso and Elastic Net models. The sale price prediction is also helpful for property buyers or sellers.

To better manage risks for new property flippers, we recommend the Reno Flip. The reno flip, in which a property flipper improves undervalued properties with renovations and/or cosmetic changes, is deemed less risky. 

Thus, our recommendations will focus on features that are more likely to increase property value when renovated, and which features to de-prioritise.


### Data
*Kaggle's Ames Housing Data sets were provided as part of project material*

*Together with the data documentation of the Ames Housing dataset*
http://jse.amstat.org/v19n3/decock/DataDocumentation.txt)

1.Basic readings related to property flipping as an investment

https://www.investopedia.com/articles/mortgages-real-estate/08/house-flip.asp
https://www.investopedia.com/terms/f/flipping.asp
https://www.propertyguru.com.sg/property-guides/property-flipping-singapore-boomer-millennial-28396

2.Readings on how the limited access to information for a home buyer/seller can lead to loss in profits, thereby making a case for a property valuation tool

https://www.cbsnews.com/news/home-appraisal-race-lawsuit/
https://www.bostonfed.org/-/media/Documents/conference/36/conf36g.pdf?la=en
https://www.statista.com/statistics/226144/us-existing-home-sales/
https://ideas.repec.org/a/tpr/restat/v90y2008i4p599-611.html
https://fred.stlouisfed.org/series/ASPUS

3.Readings on actual Property Flipping agency in Ames and their metrics for property flipping

https://newsilver.com/flipping-houses-in/ames-ia/
https://newsilver.com/the-lender/flipping-houses-in-iowa/
https://newsilver.com/the-lender/how-to-calculate-arv-simple-guide/

4.Renovation cost estimator by actual Ames company

https://www.homeyou.com/ia/chimney-repair-ames-costs

5.Information on the two most important rooms that affect sale price in a home. The kitchen & the master bedroom toilet. 

https://www.trulia.com/blog/2-most-important-rooms-in-a-house/

6.Very helpful sites for their analysis and codes

https://www.analyticsvidhya.com/blog/2021/05/yellowbrick-visualization-for-model-predictions/
https://medium.com/mlearning-ai/a-thorough-dive-into-the-ames-iowa-housing-dataset-part-1-of-5-7205093a5a53
https://nycdatascience.com/blog/student-works/predicting-housing-prices-in-ames-iowa-6/
https://towardsdatascience.com/wrangling-through-dataland-modeling-house-prices-in-ames-iowa-75b9b4086c96
https://towardsdatascience.com/understanding-the-ols-method-for-simple-linear-regression-e0a4e8f692cc
https://www.youtube.com/watch?v=VSeGseoJsNA
https://web.missouri.edu/segerti/capstone/northcraft_neale.pdf

### Data Dictionary
|Columns|Type|Dataset|Description|
|---|---|---|---|
|**Sales Price**|*int64*|train_clean|The sales price of properties| 
|**Building Age**|*int64*|train_clean|The age of house at time of sale|
|**Neighboorhood Quality Index**|*int64*|train_clean|Ranked based on interquartile percentile sale price| 
|**Local Positive Features**|*int64*|train_clean|Surrouding parks and green belt|
|**Remodeled Building**|*int64*|train_clean|Building with extensive renovation| 
|**Overall Building Quality**|*int64*|train_clean|Rates the overall material and finish of the house| 
|**Single Story Building**|*uint8*|train_clean|A single storey building|
|**Multiple Story Building**|*uint8*|train_clean|A mutliple storey building|
|**External Quality**|*int64*|train_clean|Evaluates the quality of the material on the exterior| 
|**Type of External Building Feature**|*int64*|train_clean|Building material used on exterior| 
|**Middle-unit Townhouse**|*uint8*|train_clean|Town house in the middle of the row|
|**End-unit Townhouse**|*uint8*|train_clean|Town house at the end of the row|
|**Family House**|*uint8*|train_clean|Detached house| 
|**High Roof Quality**|*int64*|train_clean|Roof material of expensive finish| 
|**Masonry Vaneer Sqft**|*float64*|train_clean|Masonry veneer area in square feet| 
|**Building Functionality**|*int64*|train_clean|Home functionality|
|**Lot Frontage**|*float64*|train_clean|Linear feet of street connected to property|
|**Lot Size**|*int64*|train_clean|Lot size in square feet|
|**Outside Grill Space**|*int64*|train_clean|Developed outdoor area|
|**Workshop Space**|*float64*|train_clean|Sheltered garage area|
|**Additional Car Garage**|*float64*|train_clean|Garage for additional car|
|**Paved Driveway**|*int64*|train_clean|Paved driveway into property|
|**Basement Quality**|*int64*|train_clean|Finishing of basement|
|**Finished Basement Sqft**|*float64*|train_clean|Area of finished basement|
|**Basement Ceiling Height**|*int64*|train_clean|Height of basement|
|**Heater Quality**|*int64*|train_clean|Heating quality and condition|
|**Kitchen Quality**|*int64*|train_clean|Kitchen quality and condition|
|**Fireplace Quality**|*int64*|train_clean|Fireplace quality and condition|
|**Finished Upstairs Sqft**|*int64*|train_clean|Finished area|
|**Rooms Upstairs**|*int64*|train_clean|No of rooms|
|**Size of Rooms**|*float64*|train_clean|Area of rooms|
|**Paved Alley**|*int64*|train_clean|Paved alley|
|**Hill Side Location**|*int64*|train_clean|Property location land contour|



### Brief Summary of Analysis
Of the models, OLS, Linear Regression, Lasso, Ridge and ElasticNet, the ElasticNet model with best_params_ had the best capability to predict sales price.
Training score: 0.8942311203735395
Testing score: 0.9046469045591974
Baseline score: 0.8916641493367219
R^2 score: 0.9046469045591974
RMSE: 22007.045039428533

The difference between scores are about 0.01 and the RMSE is $22,007.05

### Conclusion & Recommendation
1) Overall quality and finished livable, sheltered areas have the most bearing on Sales Price. Over quality and the other feature qualities have a much higher impact than expected. Perhaps, the typical buyer is willing and ready to buy a premium for what they can see, or to avoid the hassle of renovation, a good quality ready-to-move-into home is desirable.
2) For renovation that will increase Sales Price for property flipping/selling, the kitchen is the Top Feature. Followed by fireplace, basement, roof and heater. 
3) It will be quite pointless to spend on improving the driveway or worrying about the housing height/type. Building age does not have a high positive coefficient. It has less of an impact than expected.
