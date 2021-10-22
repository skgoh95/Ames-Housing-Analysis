# Project 2 - Ames Housing Data and Kaggle Challenge



## Executive Summary

In the real estate market, housing prices are determined by the attributes of the property itself and by the characteristics of the neighbourhood within which it resides. This method of pricing is known as hedonic pricing. It is reasonable to expect internal factors (such as property size) and external factors (such as availability of amenities) to have an impact on housing prices. The attributes and characteristics that are believed to have a considerable impact on housing prices were selected. This project aims to help real estate buyers and sellers predict the price of a house in Ames, Iowa based on a set of property- and neighbourhood-specific traits. The prediction will be made with the best linear regression model as evaluated by R-Squared and Mean Squared Error. Three linear regression models (Ordinary Least Squares, Ridge, Lasso) were evaluated. The entire dataset was first split into a training dataset and a testing dataset. After cross validation on the training dataset, the models had an R-Squared of around 0.78 and a Mean Squared Error of around 1.28 billion. When fitted on the training dataset and testing dataset, the models had an R-Squared of around 0.81 on the training dataset and around 0.83 for the testing dataset, and a Mean Squared Error of around 1.11 billion on the training dataset and around 1.08 billion on the testing dataset. Lasso was selected as the model of choice. After training on the entire dataset, the final R-Squared obtained was 0.82 while the final Mean Squared Error obtained was 1.07 billion. The Lasso model outperformed the Null model, which gave a baseline R-Squared of 0.00 and a baseline Mean Squared Error of 6.28 billion. The 5 biggest determinants of housing sale price were found to be Above Ground Living Area, Kitchen Quality, Location Rank, Total Basement Area, and Garage Area. Interested real estate buyers and sellers may utilise this model to predict the price of a house in Ames, Iowa and make more informed buy-sell decisions. Buyers will be able to know if they are under- or over-paying for a house at the current quoted market price, and sellers will be able know if they are under- or over-asking for their house with reference to how much a house like theirs has sold for historically.

## Problem Statement

This project aims to help real estate buyers and sellers predict the price of a house in Ames, Iowa based on a set of property- and neighbourhood-specific traits and decide if the current quoted market price is above or below what the house would reasonably be bought or sold at. The prediction will be made with the best linear regression model amongst the trio (Ordinary Least Squares, Ridge, Lasso) as evaluated by R-Squared and Mean Squared Error.

## Background & Research


In the real estate market, housing prices are determined by the attributes of the property itself and by the characteristics of the neighbourhood within which it resides. This method of pricing a marketed good is known as hedonic pricing, wherein an item is treated as the sum of its individual qualities that cannot be sold separately in the market, with the objective of estimating the extent to which each of these qualities affect the market price of the item. 

Hedonic pricing is used traditionally to estimate economic values for environmental or ecosystem services that directly affect market prices. Essentially, the basic premise of the hedonic pricing method is that the price of a marketed good is related to its traits. 

With respect to housing prices, it is reasonable to expect internal factors (such as property size, age, material quality, physical condition, and features like fireplaces or pools) and external factors (such as availability of amenities, proximity to public transportation, crime rate, socioeconomic status of households, and level of air or water pollution) to have an impact on housing prices. The attributes and characteristics that are believed to have a considerable impact on housing prices were selected as the starting features for the development of the predictive model.

## Data Dictionary
|Feature       |Type   |Dataset    |Description                                                                    |
|:-------------|-------|-----------|:------------------------------------------------------------------------------|
|age_at_remod  |int64  |train-final|Number of years till any remodeling or addition done                           |
|bldg_type     |object |train-final|Type of dwelling                                                               |
|bsmt_qual     |float64|train-final|Evaluates the height of the basement                                           |
|central_air   |object |train-final|Central air conditioning                                                       |
|condition_1   |object |train-final|Proximity to various conditions                                                |
|exter_qual    |float64|train-final|Evaluates the quality of the material on the exterior                          |
|exterior_1st  |object |train-final|Exterior covering on house                                                     |
|fireplace_qu  |float64|train-final|Fireplace quality                                                              |
|foundation    |object |train-final|Type of foundation                                                             |
|full_bath     |int64  |train-final|Full bathrooms above grade                                                     |
|garage_overall|float64|train-final|Interaction feature obtained from the product of garage quality and garage cars|
|garage_type   |object |train-final|Garage location                                                                |
|gr_liv_area   |int64  |train-final|Above grade (ground) living area square feet                                   |
|heating       |object |train-final|Type of heating                                                                |
|heating_qc    |float64|train-final|Heating quality and condition                                                  |
|house_age     |int64  |train-final|Age of house                                                                   |
|house_style   |object |train-final|Style of dwelling                                                              |
|kitchen_qual  |float64|train-final|Kitchen quality                                                                |
|land_contour  |object |train-final|Flatness of the property                                                       |
|lot_config    |object |train-final|Lot configuration                                                              |
|mas_vnr_area  |float64|train-final|Masonry veneer area in square feet                                             |
|mas_vnr_type  |object |train-final|Masonry veneer type                                                            |
|neighborhood  |object |train-final|Physical locations within Ames city limits                                     |
|overall_qual  |int64  |train-final|Rates the overall material and finish of the house                             |
|roof_matl     |object |train-final|Roof material                                                                  |
|roof_style    |object |train-final|Type of roof                                                                   |
|sale_type     |object |train-final|Type of sale                                                                   |
|saleprice     |int64  |train-final|Sale price $$                                                                  |
|street        |object |train-final|Type of road access to property                                                |
|total_baths   |float64|train-final|Total Number of bathrooms                                                      |
|total_bsmt_sf |float64|train-final|Total square feet of basement area                                             |

# Results & Analysis
A total of three linear regression models (Ordinary Least Squares, Ridge, Lasso) were evaluated to determine the best one for predicting housing prices. The entire dataset was first split into a training dataset and a testing dataset before proceeding to do modelling.

Cross validation was done on the training dataset for all three models. The results obtained were comparable across all three models. Linear and Ridge models had an R-Squared of around 0.88, while lasso had an R-Squared of around 0.77.

Further to that, all three models were fitted on the training dataset and testing dataset to obtain their performance scores. Once again, the results obtained were similar across all three models. All three models had an R-Squared of around 0.91 on the training dataset and around 0.90 for the testing dataset. The Mean Squared Error of all three models was around 0.6 billion on the training dataset and around 0.5 billion on the testing dataset.

The Ridge model was selected as the model of choice as it scored the highest R-Squared and an intermediate Mean Squared Error on the testing dataset. When the Ridge model was finally trained on the entire dataset, the final R-Squared obtained was 0.91 while the final Mean Squared Error obtained was 0.59 billion. The Ridge model also outperformed the Null model, which gave a baseline R-Squared of 0.00 and a baseline Mean Squared Error of 6.28 billion.

The 5 biggest determinants of housing sale price were found to be Above Ground Living Area, Overall Quality, Total Bathrooms, Total Basement Area, and Masonry Veneer Area. Variables that measure some form of area have emerged as stronger predictors of housing sale price than any other variables like, for instance, those that measure quality or condition. Total Bathrooms, which was engineered from a set of underlying features to serve as a measure of all bathrooms in a house, was one of the most important determinants of housing sale price. Despite there being many variables that measure quality, the Overall Quality was the only one that stood out as being a major influencer of housing sale price.

# Recommendations & Conclusions
Interested real estate buyers and sellers may utilise this model to predict the price of a house in Ames, Iowa after entering the required set of property- and neighbourhood-specific traits. This will allow firstly, the buyers to know if they will be under- or over-paying for a house at the current quoted market price, and secondly, the sellers to know if they are under- or over-asking for their house with reference to how much a house like theirs has sold for historically. Hence, both buyers and sellers will be able to make more informed buy-sell decisions off of the model.

With regards to the top predictors of housing sale price, some recommendations can be made to real estate buyers and sellers. For buyers who wish to buy their house at a bargain, they should go for houses that are generally small, situated in an inferior neighbourhood, and have a poor quality overall, as these factors will have the largest effect on bringing down the price. For sellers who wish to sell their house at a premium, they could spend some money sprucing up the quality of their home, seeing that houses with a higher overall quality tend to command higher prices.

In conclusion, housing sale price prediction based on the principles of hedonic pricing, where both internal and external influencing factors of the item are considered, has proven to be a reliable method. Moving forward, data on more neighbourhood-specific traits (such as proximity to public transportation, crime rate, socioeconomic status of households, and level of air or water pollution), which is lacking in the provided data sources, can be collected to not only elucidate the extent to which these traits affect housing sale price but also to improve the predictive ability of the model.


# References
https://www.investopedia.com/terms/h/hedonicpricing.asp

https://link.springer.com/referenceworkentry/10.1007%2F978-94-007-0753-5_1279

https://www.ecosystemvaluation.org/hedonic_pricing.htm