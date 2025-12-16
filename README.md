# Coupon Acceptance Analytics
**This project explores how drivers’ profile characteristics, such as age, income, passenger type, and marital status, influence their responses to different coupon types. Using data analysis and visualization techniques, we aim to uncover patterns and insights that can inform targeted promotional strategies.**

## Background / Motivation
This project uses the Coupon dataset (from a survey via Amazon Mechanical Turk, available through the UCI Machine Learning Repository) with a learning-focused approach to practice core data analytics skills. It provides an opportunity to explore, clean, and visualize data; examine behavioral patterns based on demographic and situational factors; calculate acceptance probabilities; segment driver groups; and derive actionable insights. The ultimate aim is to understand which drivers are most likely to accept coupons, helping marketers optimize promotional campaigns—all within a structured, hands-on learning context.

## Objective / Goal
- Explore patterns in driver behavior and decision-making related to coupon acceptance.
- Identify key factors—such as passenger type, age, income, destination, and visit frequency—that influence whether a coupon is accepted.
- Generate visual insights and data-driven hypotheses to support targeted marketing and promotional strategies.

## Dataset Description
- **Number of Observations:** ~12,680  
- **Key Features:**
  - `coupon` – Type of coupon delivered (e.g., Bar, Coffeehouse, Restaurant).  
  - `Bar`, `CoffeeHouse`, `RestaurantLessThan20`, `Restaurant20To50` – Frequency of visits to these establishments.  
  - `passanger`, `maritalStatus`, `age`, `income`, `weather`, `time` – Demographic and situational characteristics.  
  - `Y` – Target variable: 1 if the driver accepted the coupon, 0 otherwise.  
  - Detailed description of various data attributes is provided in the jupyter notebook.

## Data Cleaning / Preprocessing
- Converted categorical frequency values (e.g., `never`, `1~3`, `4~8`, `gt8`) to numeric counts.  
- Converted `age` and `income` to numeric types.  
- Filtered subsets for targeted analysis (e.g., bar coupons).  
- **Missing Values:** Present in below features and handled during preprocessing. For example, `car` is more likely to be dropped as it is missing in 99% times whereas it was more reasonable to impute the other columns with mode (or another meaningful value).
    ```
    Missing Data Report:
                        Missing Values  Percent Missing
    car                            12576        99.148534
    Bar                              107         0.843582
    CoffeeHouse                      217         1.710817
    CarryAway                        151         1.190476
    RestaurantLessThan20             130         1.024913
    Restaurant20To50                 189         1.490066
    ```

## Exploratory Data Analysis & Key Findings

The purpose of EDA is to **understand the data, discover patterns, and identify trends** before performing any predictive analysis. This project examines **driver behavior and coupon acceptance** across different coupon types, demographics, and situational factors and present the analyses and corresponding visualizations as follows:

1. **Coupon Distribution**  
   - Shows the frequency of each coupon type (e.g., Bar, Coffeehouse, Cheap/Expensive Restaurants) to help understand the dataset composition and which coupon types are more common.
   ![Coupon Distribution Bar Plot](images/coupon_distribution.png)

2. **Acceptance by Coupon Types**  
   - Compares how likely drivers are to accept each coupon type.
   ![Acceptance by Coupon Type](images/coupon_stacked_bar.png)

3. **Coupon Acceptance by Age, Income and Temprature**  
   - Visualize the distribution of age, income and temperature that reveals trends like the most likely age group, income range, or weather conditions during trips to accept the coupons.
    ![Combined Distribution](images/combined_acceptance_pie.png)

4. **Passenger Influence**  
   Passenger presence significantly influences coupon acceptance. Drivers traveling with children show lower acceptance rates, while those driving alone or with adult passengers are more likely to accept coupons, suggesting situational constraints play a key role in decision-making.
   ![Coupon Acceptance Counts by Passenger Type](images/acceptance_by_passenger_count.png)

5. **Correlations Between Features**  
   - Correlation between numeric features and coupon acceptance (Y). High visit frequency is positively associated with acceptance.
   ![Correlation Heatmap](images/correlation_heatmap.png)

.
.
.
.
[In progress]

## Future Work
- Build a **predictive model** (logistic regression, decision tree, or random forest) for coupon acceptance.  
- Include additional features such as **time of day, proximity, or weather**.  
- Test model performance and interpret feature importance for marketing insights.  

## Technologies Used
- Python (pandas, NumPy)  
- Data visualization: matplotlib, seaborn  
- Jupyter Notebook for analysis and exploration  

## References / Dataset Source
- UCI Machine Learning Repository – [Coupon Dataset](https://archive.ics.uci.edu/ml/datasets/Coupon+Recommendation)  
