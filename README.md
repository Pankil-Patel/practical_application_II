# Practical Application II
AI ML practical application 2
Link to my gibhub URL: 
Key Findings
1. Original total records in the dataset was as shown below.
![alt text](https://github.com/Pankil-Patel/practical_application_II/blob/main/images/1_Barplot_records_with_null_values.PNG)?raw=true)
   Of the 426836 records, after setting index on id, Total duplicate records removed: 56202. Below is the plot showing the total remaining records.
 ![alt text](https://github.com/Pankil-Patel/practical_application_II/blob/main/images/2_Barplot_records_after_duplicates.PNG)?raw=true)
 2. Of those amount, after dropping VIN, model, region, state and cleaning the price and odometer values, 101646 records remained. 
 ![alt text](https://github.com/Pankil-Patel/practical_application_II/blob/main/images/3_Barplot_records_after_removing_unwanted_columns.PNG)?raw=true)
 3. After evaluating the records and cleaning them up, the final dataset was created. After evaluating the records within it, the following histograms were plotted to understand the type of data and it's frequency.
 ![alt text](https://github.com/Pankil-Patel/practical_application_II/blob/main/images/4a_Histogram_Price.PNG)?raw=true)
 ![alt text](https://github.com/Pankil-Patel/practical_application_II/blob/main/images/4b_Histogram_year.PNG)?raw=true)
 ![alt text](https://github.com/Pankil-Patel/practical_application_II/blob/main/images/4c_Histogram_manufacturer.PNG)?raw=true)
 ![alt text](https://github.com/Pankil-Patel/practical_application_II/blob/main/images/4d_Histogram_condition.PNG)?raw=true)
 ![alt text](https://github.com/Pankil-Patel/practical_application_II/blob/main/images/4e_Histogram_cylinders.PNG)?raw=true)
 ![alt text](https://github.com/Pankil-Patel/practical_application_II/blob/main/images/4f_Histogram_fuel.PNG)?raw=true)
 ![alt text](https://github.com/Pankil-Patel/practical_application_II/blob/main/images/4g_Histogram_odometer.PNG)?raw=true)
 ![alt text](https://github.com/Pankil-Patel/practical_application_II/blob/main/images/4h_Histogram_titlestatus.PNG)?raw=true)
 ![alt text](https://github.com/Pankil-Patel/practical_application_II/blob/main/images/4i_Histogram_transmission.PNG)?raw=true)
 ![alt text](https://github.com/Pankil-Patel/practical_application_II/blob/main/images/4j_Histogram_drive.PNG)?raw=true)
 ![alt text](https://github.com/Pankil-Patel/practical_application_II/blob/main/images/4k_Histogram_type.PNG)?raw=true)
 ![alt text](https://github.com/Pankil-Patel/practical_application_II/blob/main/images/4l_Histogram_paint_color.PNG)?raw=true)
 
 4. A scatterplot was created to identify the outliers for odometer & year. 
 ![alt text](https://github.com/Pankil-Patel/practical_application_II/blob/main/images/5a_year_vs_price.PNG)?raw=true)
 ![alt text](https://github.com/Pankil-Patel/practical_application_II/blob/main/images/5b_odometer_vs_price.PNG)?raw=true)

 5. Now, using IQR, the first quartile & last quartile outliers were identified and removed from the dataset. 
      First Quartile 6000.0
      Third Quartile 23990.0
      Total count 74330 after removing outliers.
    Below plots depicting the data with outliers removed.
 ![alt text](https://github.com/Pankil-Patel/practical_application_II/blob/main/images/5c_year_vs_price_nooutliers.PNG)?raw=true)
 ![alt text](https://github.com/Pankil-Patel/practical_application_II/blob/main/images/5d_odometer_vs_price_nooutliers.PNG)?raw=true)

 6. Label Encoder was used for object columns that had less than 15 unique values.
 7. For manufacturer, One Hot Encoding was used using getdummies() method. The resulting dataset contained 53 columns.
 8. On evaluating using PCA, with different r values, the variance continued to stay at 1 indicating that all the values are 
    important and cannot be removed. 
 9. On using the Linear Regression model, the MSE was very high.

 10. On using the Sequential Feature Selector, the following features were selected:   
 ![alt text](https://github.com/Pankil-Patel/practical_application_II/blob/main/images/10_LinearRegression_SequentialFeatureSelection.PNG)?raw=true)
 7. On using the Linear Regression model, the train and test MSE was very high indicating that the model is either overfitting or underfitting.
 8. On using the Sequential Feature Selector with backward direction, the following features were selected:
  ![alt text](https://github.com/Pankil-Patel/practical_application_II/blob/main/images/11_TrainTestMSE_SFS_LinearRegression_BackwardSelector.PNG)?raw=true)
   ![alt text](https://github.com/Pankil-Patel/practical_application_II/blob/main/images/11_TrainTestMSE_SFS_LinearRegression.PNG)?raw=true)
    Eventhough the Train and Test MSE were high, the features selected were as follows:
       ![alt text](https://github.com/Pankil-Patel/practical_application_II/blob/main/images/12_SelectedFeatures_BackwardSelection.PNG)?raw=true)
 9. On using the Ridge Regression model, the MSE came high as well. The following top 5 features were selected:
 ![alt text](https://github.com/Pankil-Patel/practical_application_II/blob/main/images/13_RidgeRegression_MSE_FeatureSelection.PNG)?raw=true)
 10. On using Recursive Feature Elimination(RFE) with Ridge Regression model, the MSE came high as well. The following top 5 features were selected:
  ![alt text](https://github.com/Pankil-Patel/practical_application_II/blob/main/images/14_RFE_RidgeRegression_MSE_FeatureSelection.PNG)?raw=true)
11. And the Best model selected based on GridSearchCV was as follows:
  ![alt text](https://github.com/Pankil-Patel/practical_application_II/blob/main/images/15_CrossValidation_GridSearchCV_BestModel_MSE.PNG)?raw=true)
12. Doing R2 analysis with CV=5, the score came out to 0.45 indicating it's not the best model fit.
  ![alt text](https://github.com/Pankil-Patel/practical_application_II/blob/main/images/16_R2_CoefficientofDetermination.PNG)?raw=true)

 Based on the above findings, even though the model is not the best fit, some key features seemed to repeat indicating they are impacting the price of the car. Newer model car, along with 8 cylinders, type of fuel, odometer and transmission are a good indicator of what people buy. Along with that, some key manufacturers like Tesla, Mini, Fiat and Chrysler are cars that users are interested in.