# **PROJECT 2**: Morgan Hofmann  


# Problem Statement  
*Determine which variables of a home in Ames, IA have a strong impact on the sale price, with the goal of helping first-time homebuyers in Ames better understand the local housing market so they can strategically buy their first home.*  
  

# File Directory 
* README.md   
* code_for_predicting_saleprice.ipynb  
* original_data  
    * train.csv  
    * test.csv  
    * sample_sub_reg.csv  
* submits  
    * eighth_submit.csv    
    * eleventh_submit.csv  
    * fifth_submit.csv  
    * first_submit.csv  
    * fourteenth_submit.csv  
    * fourth_submit.csv  
    * ninth_submit.csv  
    * second_submit.csv  
    * seventh_submit.csv  
    * sixth_submit.csv  
    * tenth_submit.csv  
    * third_submit.csv  
    * thirteenth_submit.csv  
    * twelfth_submit.csv  
    * zeroth_submit.csv  
* presentation  
    * project_2_presentation_saleprice_of_homes_in_ames.pdf  
    * images  
        * distribution_house_sale_price.png  
        * iowa_flag.jpeg  

  
# Data and Data Dictionary  
Data Sources:  
* [`train.csv.csv`](./original_data/train.csv): Housing data for home sales in Ames, IA, used for modeling the data   
* [`test.csv`](./original_data/test.csv): Housing data for home sales in Ames, IA, used for testing the data in Kaggle    
* [`sample_sub_reg.csv`](./original_data/sample_sub_reg.csv): Formatting guide for Kaggle submissions  
    
The above data sources have been provided by General Assembly instructors.  

The train dataset listed above includes information on homes and house sale prices in Ames, IA from 2006-2010. The data includes 80 unique varaibles (including sale price) and 2051 homes/properties. More information on the 80 unique varaibles can be found here: https://www.kaggle.com/c/dsir1213/data    

The test dataset is very similar to the train dataset, but it's a smaller portion of data on homes that sold in Ames, IA from 2006-2010. This dataset contains information on 878 homes/properties and only 79 unique variables (SalePrice is not a variable in this dataset).

The sample sub reg data set is contains two columns - Id & Saleprice - and this data set is included only to show the format needed for Kaggle submissions.

**Features contained in the submit csv's**:  

|Feature|Type|Dataset|Description|  
|---|---|---|---|  
|Id|int|zeroth_submit.csv|Testing ID|   
|SalePrice|float|zeroth_submit.csv|SalePrice prediction using train_test_split with a StandardScalar/LassoCV model fitted on 35 features|   
|Id|int|first_submit.csv|Testing ID|   
|SalePrice|float|first_submit.csv|SalePrice prediction using baseline (mean) model|   
|Id|int|second_submit.csv|Testing ID|   
|SalePrice|float|second_submit.csv|SalePrice prediction using a LinearRegression model fitted on 1 feature|   
|Id|int|third_submit.csv|Testing ID|   
|SalePrice|float|third_submit.csv|SalePrice prediction using a LinearRegression model fitted on 7 features|   
|Id|int|fourth_submit.csv|Testing ID|   
|SalePrice|int|fourth_submit.csv|SalePrice prediction using a StandardScalar/LogisticRegression model fitted on 7 features|   
|Id|int|fifth_submit.csv|Testing ID|   
|SalePrice|float|fifth_submit.csv|SalePrice prediction using a LinearRegression model fitted on 8 features|   
|Id|int|sixth_submit.csv|Testing ID|   
|SalePrice|float|sixth_submit.csv|SalePrice prediction using a RidgeCV model fitted on 8 features|   
|Id|int|seventh_submit.csv|Testing ID|   
|SalePrice|int|seventh_submit.csv|SalePrice prediction using a PolynomialFeatures/StandardScalar/RFE(RidgeCV)/LogisticRegression model fitted on 35 features|   
|Id|int|eighth_submit.csv|Testing ID|   
|SalePrice|float|eighth_submit.csv|SalePrice prediction using a StandardScalar/RFE(LogisticRegression)/RidgeCV model fitted on 35 features|   
|Id|int|ninth_submit.csv|Testing ID|   
|SalePrice|float|ninth_submit.csv|SalePrice prediction using a StandardScalar/RidgeCV model fitted on 35 features|   
|Id|int|tenth_submit.csv|Testing ID|   
|SalePrice|float|tenth_submit.csv|SalePrice prediction using a OneHotEncoder/StandardScalar/RidgeCV model fitted on 11 features|   
|Id|int|eleventh_submit.csv|Testing ID|   
|SalePrice|float|eleventh_submit.csv|SalePrice prediction using a OneHotEncoder/StandardScalar/RidgeCV model fitted on 10 features|   
|Id|int|twelfth_submit.csv|Testing ID|   
|SalePrice|float|twelfth_submit.csv|SalePrice prediction using train_test_split with a StandardScalar/RidgeCV model fitted on 35 features|   
|Id|int|thirteenth_submit.csv|Testing ID|   
|SalePrice|float|thirteenth_submit.csv|SalePrice prediction using train_test_split with a StandardScalar/LinearRegression model fitted on 35 features|   
|Id|int|fourteenth_submit.csv|Testing ID|   
|SalePrice|float|fourteenth_submit.csv|SalePrice prediction using train_test_split with a StandardScalar/LassoCV model fitted on 8 features|   
  

# Executive Summary  
*I used the training data for homes sold in Ames, IA in the years 2006-2010 to determine what home features are likely to be major contributors to the sale price of a home in Ames. In reviewing the correlation of many variables with the sale price, I determined that the following 8 features would be best highlighted in a model: overall quality, above grade living area, year built, garage area, total basement area, 1st floor area, total rooms above grade, and total bathrooms above grade. I chose 8 features that have a high correlation with sale price(greater than .5 correlation), but failed to check multicollinearity, which likely exists between a few of my chosen variables. I kept my model limited to 8 features because I wanted to keep the takeaways simple for first time homebuyers.*  
  
*According to the data, the average house in Ames, IA at this time looked like:*  
* *Sale price of $181.5K*
* *Overall quality of 6/10*
* *Built in 1972*
* *1,499 SF living area above grade*
* *1,164 SF 1st floor*
* *1,057 SF total basement area*
* *473 SF garage*
* *6 total rooms above grade (not including bathrooms)*
* *2 bathrooms above grade*  
  
*I executed 15 models total, some of which were for learning purposes and not a good fit for the data set. I found that keeping my variables constant, I had slightly lower RMSE with LassoCV models in comparison to RidgeCV and LinearRegression models. Thus, the model I used to predict housing prices in Ames was a LassoCV model transformed first by StandardScalar. This model could account for 79% of the variance in the sales prices of homes in Ames, IA.
  
    
# Conclusions and Recommendations  
*My recommendation to first time homebuyers is to figure out their non-negotiables, and consider how they can use the details of what an average house in Ames, IA looks like and compare it with my conclusions to figure out if certain house features are worth the cost to get into the housing market. (I am assuming that getting into the market is hard for first time homebuyers, since recent news from KCRG affirms this assumption **(3)**):*
* *Overall quality has the largest impact on sale price - if overall quality increases by 1 standard deviation, holding all other variables constant, we expect sale price to increase by $28,823.* 
* *If above grade (ground) living area square feet increases by 1 standard deviation, holding all other variables constant, we expect sale price to increase by $23,108.*  
* *If the year built increases by 1 standard deviation, holding all other variables constant, we expect sale price to increase by $12,137.*  
* *If the garage area increases by 1 standard deviation, holding all other variables constant, we expect sale price to increase by $9,530.*
* *If the total SF of the basement area increases by 1 standard deviation, holding all other variables constant, we expect sale price to increase by $7,530.*    
* *If the 1st floor SF increases by 1 standard deviation, holding all other variables constant, we expect sale price to increase by $7,036.*  
* *If the total rooms above grade (not including bathrooms) increases by 1 standard deviation, holding all other variables constant, we expect sale price to increase by $733.*  
* *If the total bathrooms above grade increases by 1 standard deviation, holding all other variables constant, we expect sale price to DEcrease by $2,680.*  
  
*More succinctly, saving to buy your first home can take a long time, so having a clear idea of non-negotiables and assessing how higher quality, larger living spaces with more rooms, garage space, and a basement make a home more desirable to buyers, and more expensive for buyers. To get into the market at an affordable price, first time homebuyers may need to scale back on house size or amenities.*
  
  
# Sources
**(1):** https://www.iowafinance.com/programs-for-property-developers/home-program/ - Referenced to position my presentation: presented to an audience of first time home buyers saying that the Iowa Finance Authority (who runs Iowa’s Homebuyer Assistance Program) asked me to present to this group of first time homebuyers
  
**(2):** https://en.wikipedia.org/wiki/File:Flag_of_Iowa.svg - Resource to obtain the Iowa state flag  
  
**(3):** https://www.kcrg.com/2021/12/27/new-home-buyers-struggle-purchase-homes-current-housing-market/ - reference that discusses more about the current challenged in the Iowa housing market