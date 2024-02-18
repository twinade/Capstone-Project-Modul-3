# Capstone-Project-Modul-3


# Context
Syarah App is an application specialized in selling guaranteed used cars and new cars, the application provides customers with a smooth and convenient online buying experience. Through it, customers can browse and buy the car from the mobile phone without fatigue or trouble, as we ship the car to the door of the house. The application offers the advantages of a comprehensive warranty for used cars, our used cars are checked for more than 200 points, with a one-year warranty, and the most important is a 10-day return guarantee through which you can try the car and if you like it, you can return it without any reason.


# Problem Statement
As a business owner, Syarah.com, seeing incorrect car selling prices on the market will also have an impact on the company. Because one of the advantages of this business is advertising costs and the proportion of profits obtained from car sales. If many cars with specifications are sold at prices that are too expensive (OVERPRICE), then there will be fewer car buyers through the Syarah website so that the company's profits will also decrease. As time goes by, sellers also don't want to advertise their cars on Syarah.com because there are fewer visitors/buyers on the site. Then if many cars are sold at too cheap a price, then the company also gets little profit from selling them.

In this way, the question arises, "How can Syarah.com help determine the right car selling price for sellers based on the car's specifications?" So the seller only needs to enter the specifications of the car and Syarah will automatically suggest a selling price for the car. Later on the Syarah website there will be a prediction tool to make it easier for sellers to sell cars with the right specifications and the right price. It is hoped that the public will feel confident that the car selling price advertised on Syarah is the right price so that many visitors and sellers will make transactions through Syarah. In other words, the more transactions, the higher the company's income, in this case obtained from advertising costs from the seller's side and the proportion of sales profits from the buyer's side.


# Problem Statement
For Syarah.com, a prediction tool that can provide fair price predictions can certainly increase the number of buyers and sellers. In other words, more buyers and sellers means increasing company profits. The prediction tool is to help them predict prices so that sellers can offer the right price. Price variations can be given based on features, mileage, brand, car origin, transmission type, seller's area, and of course the appropriate price.

# Analytic Approach
In this case, data analysis is needed to identify patterns in existing features that differentiate each vehicle.

Regression analysis is needed to determine the causal relationship between one variable and another variable. Regression analysis will be carried out using <u>**machine learning**</u>. So you will get a prediction tool for the right car selling price and at the same time it can be useful for buyers in determining the right price for the Saudi Arabian used car they want to buy.

The algorithm model approach that will be used is <u>**Linear Regression, KNN Regression, Decision Tree Regression, RandomForest Regression, and XGBoost Regression**</u>. By comparing the five algorithm models, the best algorithm model will be selected and then the hyperparameter tuning process will be carried out for better model performance.


# Evaluation Metric
Metric evaluation MAE, MAPE, RMSE, and r2 are used in various scenarios while training a regression model to solve the desired problem. Each metric provides a different lens for evaluating the performance of a regression model. Selecting the right metrics depends on the specific context and analysis goals.

<u>**MAE**</u> measures the average absolute difference between predicted and actual values. <u>**MAPE**</u> expresses the error as a percentage of the true value, providing an easy-to-understand metric. <u>**RMSE**</u> is the square root of the mean square error, so the error scale is the same as the target scale. <u>**R-Squared**</u> shows the proportion of variance in the dependent variable that can be predicted from the independent variable. <u>**R-Squared**</u> shows how well the predictions approximate the actual data points. A high <u>**R-Squared**</u> (close to 1) means the model can predict the true value very closely.

# Data Understanding
- Dataset contains 5624 used car records collected from syarah.com.
- Each row represents information about each used car.
**Features Information**

| **Feature** | **Description** |
| --- | --- |
| Type | Type of used car |
| Region | The region in which the used car was offered for sale |
| Make | The company name |
| Gear_Type | Gear type size of used car |
| Origin | Origin of used car |
| Options | Options of used car |
| Year | Manufacturing year |
| Engine_Size | The engine size of used car |
| Mileage | Mileage of used car |
| Negotiable | True if the price is 0, that means it is negotiable |
| Price | Used car price |


# Content
**1. Data Preprocessing**
  * Checking Data Information
  * Checking Data Duplicate
  * Checking Missing Value
    
**2. Exploratory Data Analysis**
    At this stage, we explore details of each features to see insight and what act should we do next.
    The data contains numerical and categorical
    
**3. Feature Engineering**
  * Encoding
    --> At this stage, we encode categorical feature by using OneHotEncoding and BinaryEncoding.
    OneHotEncoding is used for feature which have only few unique value such feature 'Origin', 'Transmission', and 'Options'.
    Binary Encoding is used for feature which have many unique values (more than 10 unique values) such as feature 'Model', 'Brand', and 'Region'
  * Scaling
    --> At this stage, we scale numerical feature by using RobustScaler. RobustScaler is chosen because of numerical feature have outlier, RobustScaler is resisted to outlier.
    RobustScaler is used for all numerical feature (except feature 'Price')
    
**4. Modelling**
    --> Model algorithm using Linear Regression, K Nearest Neighbor, Decission Tree, Random Forest, dan XGBoost
    
**5. Conclusion & Recommendation**
    --> XGBoost become the best model algorithm compared to other model algorithm.
    --> After XGBoost parameter tuning:
        * Score MAE : 19802 -> 17847        **<u>(11% better)**</u>
        * Score MAPE : 24.11% -> 22.47%     **<u>(1.64% better)**</u>
        * Score r2 : 75.47% -> 79.23%       **<u>(3.76% better)**</u>


