<h1><p align = "center"> Medical Insurance Cost Prediction</p></h1>

## PROJECT OVERVIEW
Over the past decade, health insurance expenses have surged, largely due to the increasing costs of medical care and several influencing factors. This project aims to analyze healthcare costs for a sample population based on attributes like age, gender, BMI, number of children, smoking status, and region.

The goal is to identify the main drivers and predict health insurance expenses through exploratory data analysis and predictive modeling using the Health Insurance dataset. The project leverages Numpy, Pandas, Scikit-learn, and various data visualization tools. 

<b>Overview:</b> <br>
- Explored the dataset for patterns with exploratory data analysis <br>
- Executed data processing, feature engineering, and transformation to prep the data for modeling <br>
- Developed models to estimate insurance costs from the selected features <br>
- Assessed model performance using metrics such as RMSE, R2, Test Accuracy, Train Accuracy, and MAE <br>

## DATA DESCRIPTION
1. age: age of primary beneficiary
2. sex: insurance contractor gender, female, male
3. bmi: Body mass index, providing an understanding of body, weights that are relatively high or low relative to height,
objective index of body weight (kg / m ^ 2) using the ratio of height to weight, ideally 18.5 to 24.9
4. children: Number of children covered by health insurance / Number of dependents
5. smoker: Smoking
6. region: the beneficiary's residential area in the US, northeast, southeast, southwest, northwest
7. charges: Individual medical costs billed by health insurance

Data source : https://www.kaggle.com/mirichoi0218/insurance

## EXPLORATORY DATA ANALYSIS (EDA)
- Feature sex, region has an almost balanced amount, meanwhile most people are non smoker & obese <br>
![image](https://user-images.githubusercontent.com/80570935/130601931-826570ec-df1d-4b85-918f-00eb740ed212.png)

- A person who smoke and have BMI above 30 tends to have a higher medical cost <br>
![image](https://user-images.githubusercontent.com/80570935/130602334-b62a7f7e-e1c8-45eb-be7d-ff752853d158.png)

- Older people who smoke have more expensive charges <br>
![image](https://user-images.githubusercontent.com/80570935/130602565-2cb73fa9-769b-4822-880e-c009d2fbef39.png)

- People who smoke and obese have the highest average charges compared to others <br>
![image](https://user-images.githubusercontent.com/80570935/130602770-c008fb2b-2041-440e-b92e-373e7cbed2ce.png)

## INSIGHTS
The insights drawn by performing `Exploratory Data Analysis` (EDA) are:

- Most people are a non smokers & obese.
- Feature sex, region has an almost balanced amount.
- People who smoke & have a higher BMI, has higher medical charges.
- Older people who smoke have more expensive charges.
- An obese person who smokes have higher charges.

## DATA PROCESSING 
1. Check missing value - there are none <br>
2. Check duplicate value - there are 1 duplicate, will be remove <br>
3. Feature engineering - make a new column `weight_status` based on BMI score <br>
4. Feature transformation: <br>
 A) Encoding `sex`, `region`, & `weight_status` attributes <br>
 B) Ordinal encoding `smoker` attribute <br>
5. Modeling: <br>
 A) Separating target & features <br>
 B) Splitting train & test data <br>
 C) Modeling using Linear Regression, Random Forest, Decision Tree, Ridge, & Lasso algorithm <br>
 D) Find the best algorithm <br>
 E) Tuning Hyperparameter <br>
 
## MODEL EVALUATION 
| Score | LinearRegression | DecisionTree | RandomForest | Ridge |
| ----------- | ----------- | ----------- | ----------- | ----------- |
| R2 | 0.77 | 0.78 | 0.78 | 0.86 |
| Train Accuracy | 0.74 | 1.0 | 0.97 | 0.74 |
| MAE | 4305.20 | 2798.83 | 2608.55 | 4311.10 |
| Test Accuracy | 0.77 | 0.78 | 0.86 | 0.77 | 
| RMSE | 6209.88 | 6067.50 | 4841.88 | 6238.13 |
 
## CONCLUSION
Among the models tested, the Linear Regression algorithm yielded the best results, with an MAE of 4305.20, RMSE of 6209.88, and R2 of 0.77. <br>
Thus, the Linear Regression model proves to be the most suitable based on both training and testing accuracies.
