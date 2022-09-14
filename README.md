# Retail_Sales_Prediction
A giant retail store has worldwide operations. It operates across the globe and deals with all the major product categories - consumer, corporate & home office. In this analysis, a forecasting model is developed using Deep learning algorithms to improve the accuracy of forecasts of sales and we will use a TensorFlow neural network to make our predictions.. The proposed model is especially targeted to support the future purchase and more accurate forecasts product sales.
## Dataset.
A retail data which contain sales of various product of different categories and sub_categories.
* Number of rows:    51290
* Number of columns: 16
### Column details.
* Row ID.
  * Unique Value: 51290.
  * Missing Value: 0.
  * Type: Integer.
  * Datatype: Integer.
* Order ID.
  * Unique Value: 20035.
  * Missing Value: 0.
  * Type: Category.
  * Datatype: Object.
* Order Date.
  * Unique Value: 1430.
  * Missing Value: 0.
  * Type: Datetime.
  * Datatype: Object.
* Customer ID.
  * Unique Value: 1590.
  * Missing Value: 0.
  * Type: Category.
  * Datatype: Object.
* Customer Name.
  * Unique Value: 795.
  * Missing Value: 0.
  * Type: Category.
  * Datatype: Object.
* City.
  * Unique Value: 3636.
  * Missing Value: 0.
  * Type: Category.
  * Datatype: Object.
* State.
  * Unique Value: 1094.
  * Missing Value: 0.
  * Type: Category.
  * Datatype: Object.
* Country.
  * Unique Value: 147.
  * Missing Value: 0.
  * Type: Category.
  * Datatype: Object.
* Product ID.
  * Unique Value: 10292.
  * Missing Value: 0.
  * Type: Category.
  * Datatype: Object.
* Category.
  * Unique Value: 3.
  * Missing Value: 0.
  * Type: Category.
  * Datatype: Object.
* Sub-Category.
  * Unique Value: 17.
  * Missing Value: 0.
  * Type: Category.
  * Datatype: Object.
* Product Name.
  * Unique Value: 3768.
  * Missing Value: 0.
  * Type: Category.
  * Datatype: Object.
* Sales.
  * Unique Value: 22995.
  * Missing Value: 0.
  * Type: Float.
  * Datatype: Float.
* Quantity.
  * Unique Value: 14.
  * Missing Value: 0.
  * Type: Integer.
  * Datatype: Integer.
* Discount.
  * Unique Value: 27.
  * Missing Value: 0.
  * Type: Float.
  * Datatype: Float.
* Profit.
  * Unique Value: 24575.
  * Missing Value: 0.
  * Type: Float.
  * Datatype: Float.

## Data Pre-Processing.
### Feature Selection.
  * Remove un-necessary features that does not have great impact on sale and these features are 'Row ID','Order ID','Customer ID','Customer Name','Product ID'.

### Feature engineering.
  * Convert datatype of 'Order date' to datetime.
  * Extract day of the week from 'Order date' and name as 'Week_day'.
  * Remove 'Order date' as machine only learn numbers.
#### Corelation - Numerical.
![NUMERICAL](https://github.com/NisilNas/Retail_Sales_Prediction/blob/main/Image/Corelation_Numeric.png)
 * This is corelation of Numerical Features which is 'Profit','Quantity','Discount','Sales'.
 * From above we can see that each of the features are not corelated so there is not needed to drop these features.
#### Corelation - Categorical
##### ![Country VS Sales](https://github.com/NisilNas/Retail_Sales_Prediction/blob/main/Image/Corelation_SalesVSCountry.png)
 * Corelation between Country and sales.
##### ![Category VS Sales](https://github.com/NisilNas/Retail_Sales_Prediction/blob/main/Image/Corelation_SalesVSCategory.png)
 * Corelation between Category and sales.
##### ![Sub_Category VS Sales](https://github.com/NisilNas/Retail_Sales_Prediction/blob/main/Image/Corelation_SalesVSSub_Category.png)
 * Corelation between Sub_Category and sales.
##### ![Week_Days VS Sales](https://github.com/NisilNas/Retail_Sales_Prediction/blob/main/Image/Corelation_SalesVSWeekDay.png)
 * Corelation between Week_Days and sales.
 * As we can see 'Country','Category','Sub_Category','Product Name' are negatively corelated and hase no corelation with sales.
 * 'Country','City','State' are Corelated and constitute for 'Country'.
 * So we can drop 'City','State'.
### Data Cleaning.
 * Remove outlier using z score by setting value less than threshold.
 * Remove Duplicate.
 * Convert Object datatype to categorical datatype.
### Natural Language Processing.
 * OneHotEnconding using dummies function.
## Exploratory Data Analysis.
### Bar Plot
#### Country Wise Sales.
##### ![Country Wise Sales](https://github.com/NisilNas/Retail_Sales_Prediction/blob/main/Image/BarPlot_SalesVSCountry.png)
#### Category Wise Sales.
##### ![Category Wise Sales](https://github.com/NisilNas/Retail_Sales_Prediction/blob/main/Image/BarPlot_SalesVSCategory.png)
#### Sub Category Wise Sales.
##### ![Sub Category Wise Sales](https://github.com/NisilNas/Retail_Sales_Prediction/blob/main/Image/BarPlot_SalesVSSub_Category.png)
#### Product Name Wise Sales.
##### ![Product Name Wise Sales](https://github.com/NisilNas/Retail_Sales_Prediction/blob/main/Image/BarPlot_SalesVSProductName.png)
#### Week_Day Wise Sales.
##### ![Week_Day Wise Sales](https://github.com/NisilNas/Retail_Sales_Prediction/blob/main/Image/BarPlot_SalesVSWeekDay.png)
 * Since 'Product Name' has 3768 unique value and 'Country has 147 unique value the Bar Plot is little bit Squed

