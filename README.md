# Practical Application II
AI ML practical application 2
Link to my gibhub URL: 
Key Findings
 1. Of the 426836 records, after setting index on id, Total duplicate records removed: 56202.
 ![alt text](https://github.com/Pankil-Patel/practical_application_II/blob/main/images/1_Barplot_records_with_null_values.PNG)?raw=true)
 2. Of those amount, after dropping VIN, model, region, state and cleaning the price and odometer values, 101646 records remained. 
 3. Once One Hot Encoding of specific columns was done, the number of columns increased to 82
 4. On evaluating using PCA, with different r values, the variance continued to stay at 1 indicating that all the values are 
    important and cannot be removed. 
 5. On using the Linear Regression model, the MSE was very high.
 6. On using the Sequential Feature Selector, the following features were selected: 
       a. fuel_diesel  
       b. type_truck
       c. year 
       d. cylinders
       e. odometer
 7. On using the Linear Regression model, the train and test MSE was very high indicating that the model is not a good fit.
 8. On using the Sequential Feature Selector with backward direction, the following features were selected:
       a. fuel_diesel
       b. type_truck
       c. year
       d. cylinders
       e. odometer
    Eventhough the Train and Test MSE were high, the features selected were the same as the Sequential Feature Selector.
 9. On using the Ridge Regression model, the MSE came high as well. The following top 5 features were selected:
       a. manufacturer_ferrari
       b. manufacturer_tesla
       c. manufacturer_datsun
       d. manufacturer_aston-martin
       e. manufacturer_fiat
 10. On using the Ridge Regression model with RFE, the MSE came high as well. The following top 5 features were selected:
       a. condition_fair
       b. manufacturer_alfa-romeo
       c. manufacturer_ferrari
       d. manufacturer_tesla
       e. fuel_diesel

 Based on the above findings, none of the models were able to predict the price of the vehicles accurately.
 The size of the data set after the null record removal was very small and perhaps that is the reason for it not able to predict
 the price accurately. The data set needs to be larger and more features need to be added to the data set to make it more 
 accurate.
