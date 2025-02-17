# USA HOUSING- Data Science Model

Welcome to the "Exploring US Home Price Trends" project repository! In this project, we embark on a data-driven journey to understand the key factors influencing home prices in the United States over the past two decades. By leveraging publicly available data and advanced data science techniques, our goal is to build a comprehensive model that sheds light on the intricate relationship between various factors and home prices.


- [🔗 Data Cleaning](https://github.com/pritamkumar143/US_house/blob/main/Data_Cleaning_LLC.ipynb): Details on data cleaning and preprocessing.
- [🔗 EDA_and_Feature_Engineering](https://github.com/pritamkumar143/US_house/blob/main/EDA_LLC.ipynb): Information about data relations and distributions.
- [🔗 Model_Training](https://github.com/pritamkumar143/US_house/blob/main/model_training_LLC.ipynb): Model Training and Evaluation of features.

Feel free to explore each section for a deeper understanding of the project.


## Libraries and Tools used:

- Programming Languages: Python
- Data Analysis Libraries: NumPy, pandas, matplotlib, seaborn
- Machine Learning Libraries: scikit-learn
- Data Visualization: Matplotlib, Seaborn
- Version Control: Git, GitHub
- Jupyter Notebooks for data exploration and analysis

## Data Collected

- Target: S&P/Case-Shiller U.S. National Home Price Index
- Population: Population includes resident population plus armed forces overseas
- Personal Income: Income that persons receive in return for their provision of labor, land, and capital used in current production and the net current transfer payments that they receive from business and from government
- Gross Domestic Product: Market value of goods and services produced by labor and property located in the United States
- Unemployment Rate: Percentage of the labor force unemployed (16 years and above)
- Mortgage Rate: Interest rate charged for a home loan (Percentage)
- Employment: Population Ratio (emratio)
- Building Construction Permits: Total units issued in the U.S.
- Labor Force Participation Rate: Percentage of the population either working or actively looking for work
- Monthly Supply of New Houses: Ratio of new houses for sale to new houses sold
- Housing Starts: Number of new housing projects started
- Median Sales Price: Median sales price of houses sold in the U.S. (USD)
- Producer Price Index: Cement Manufacturing and Concrete Brick
- All Employees, Residential Building Construction: Thousands of people
- All Employees, Construction: Thousands of people in construction
- Industrial Production: Cement output
- Homeownership Rate: Percentage of households that are owner-occupied
- Personal Saving Rate: Personal saving as a percentage of disposable personal income
- New Privately-Owned Housing Construction Completed: Total units in thousands
- New Privately-Owned Housing Units Under Construction: Total units in thousands


## Feature Selection

In our analysis, we identified several key features and their correlations with the target variable, represented by the S&P Case-Shiller Home Price Index.

| Feature                | Correlation with Home Price Index |
|------------------------|-----------------------------|
| MSPUS                  | 0.980144                    |
| PPI_Cement             | 0.964074                    |
| GDP                    | 0.960633                    |
| income                 | 0.955608                    |
| PPI_Concrete           | 0.939072                    |
| population             | 0.896974                    |
| total_emp_cons         | 0.812130                    |
| new_private_hw_under   | 0.634935                    |
| all_Const_Emp          | 0.560479                    |
| home_ow_rate           | 0.207294                    |
| monthly_supply         | 0.169504                    |
| permit                 | 0.127189                    |
| house_st               | -0.001742                   |
| new_private_house      | -0.068468                   |
| unemployed_rate        | -0.249211                   |
| IPI_Cement             | -0.260807                   |
| p_saving_rate          | -0.286001                   |
| emratio                | -0.538776                   |
| mortgage_rate          | -0.730709                   |
| labor_percent          | -0.788313                   |

The positive correlation values indicate a direct relationship with home prices, while negative values suggest an inverse relationship. Features with higher absolute correlation values have a larger impact on home prices.

## Model Selection and Cross-Validation

In this project, we employed the **Lasso regression** model due to indications of significant collinearity in the dataset. The Lasso regression model is known for its ability to handle collinearity by applying L1 regularization, which encourages sparsity in feature coefficients.

To optimize the Lasso model's performance and select the best regularization hyperparameter (alpha), we utilized **cross-validation**.

- Optimal alpha: **0.0576**.

The cross-validation process resulted in the following **R-squared** scores for different folds:
- Fold 1: 0.9952
- Fold 2: 0.9939
- Fold 3: 0.9933
- Fold 4: 0.9926
- Fold 5: 0.9932

![image](https://github.com/Npps1997/USA-HOUSING--Data-Science-Model/assets/96871890/9d8ecd9b-c3a5-40d9-86a4-e230de4783ab)


- **mean R-squared** : **0.9937**
- **standard deviation R squared** : **0.0009**

## Best Features With non-zero Coefficients

Here are the features and their respective coefficients obtained from our Lasso regression model:

| Feature                | Coefficient  |
|------------------------|--------------|
| p_saving_rate          | -0.923351    |
| IPI_Cement             | 0.196152     |
| PPI_Concrete           | 16.893031    |
| population             | -8.945503    |
| new_private_hw_under   | 4.770749     |
| GDP                    | 18.499826    |
| house_st               | 2.103615     |
| labor_percent          | 1.501053     |
| all_Const_Emp          | 10.887265    |
| monthly_supply         | 3.212566     |
| unemployed_rate        | 7.251776     |
| MSPUS                  | 26.852562    |

These coefficients represent the impact of each feature on the prediction of home prices. Positive coefficients indicate a direct relationship with home prices, while negative coefficients suggest an inverse relationship.

## Features with zero Coefficient

In our analysis, some features in our Lasso regression model had coefficients of 0.0, indicating that they do not significantly impact the prediction of home prices. Here are the features with coefficients of 0.0:

| Feature               | Coefficient  |
|-----------------------|--------------|
| mortgage_rate         | 0.0          |
| PPI_Cement            | 0.0          |
| permit                | 0.0          |
| new_private_house     | 0.0          |
| emratio               | 0.0          |
| income                | 0.0          |
| home_ow_rate          | 0.0          |
| total_emp_cons        | 0.0          |

These features do not have a significant impact on the prediction of home prices in our model.

## Sources

https://fred.stlouisfed.org/
