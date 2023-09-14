<div align="center">
<centre><h1>Medical Insurance Prediction</h1><br />
 <img ![cee74642dc5bff63684290a0eb80e1f9](https://github.com/SruthiSreeSG/Medical_Insurance_Prediction/assets/140688742/0eb417be-8027-406a-b899-d8d02b0b2c75)></centre>
 </div>

 

## Introduction
  The project titled "Medical Insurance EDA and Forecast" likely involves using machine learning techniques to perform exploratory data analysis (EDA) on a dataset related to medical insurance and then using this analysis to forecast or make predictions about future trends or outcomes in the context of medical insurance. Let me break down the project steps:

## Step-1:Importing libraries
* **For ML Models:** sklearn</br>
* **For Data Processing:** numpy, pandas, sklearn</br>
* **For Data Visualization**: matplotlib, seaborn, plotly</br>

### Setting up sklearnex to speed up training
  If you don't know about sklearnex, this is a tool you can use to speed up training sklearn models, without having to change any code.</br>
  A simple 2 line of code can speed up training by 2x.

## Step-2: About the DataSet
The dataset named "Insurance" is being used for this project which is in .csv format.This dataset contains some basic features of the patient and the expenses for the treatment.

### Column Descriptions
* **age:** age of primary beneficiary</br>
* **sex:** insurance contractor gender, female, male</br>
* **bmi:** Body mass index, providing an understanding of body, weights that are relatively high or low relative to height, objective index of body weight              (kg / m ^ 2) --using the ratio of height to weight, ideally 18.5 to 24.9</br>
* **children:** Number of children covered by health insurance / Number of dependents</br>
* **smoker**: Smoking</br>
* **region:** the beneficiary's residential area in the US, northeast, southeast, southwest, northwest.</br>
* **expenses**: Individual medical costs billed by health insurance</br>

**Categorical Features**
sex, smoker, region
**Continuous Features**
age, children, bmi, charges

## Step-3: Exploratory Data Analysis
 EDA is the process of summarizing and visualizing data to understand its main characteristics, uncover patterns, and identify potential relationships or trends. In the context of this project, EDA may involve tasks such as:

* **Data Cleaning:** Removing or handling missing values and outliers.</br>
* **Descriptive Statistics:** Calculating basic statistics like mean, median, and standard deviation to get a sense of the data's distribution.</br>
* **Descriptive Statistics:** Calculating basic statistics like mean, median, and standard deviation to get a sense of the data's distribution.</br>
* **Data Visualization:** Creating charts and graphs to visualize trends and relationships in the data.</br>
* **Feature Engineering:** Creating new features or modifying existing ones to improve model performance.</br>

### Insights from EDA


* Individuals who smoke have a higher medical bill than individuals who do not smoke.</br>
* We can see 3 categories of medical bill paid, 0-15k, 15k-32k, 32k-50k.</br>
* It can be seen that those 3 categories of expenses has a strong correlation with age.</br>
* The correlation of expenses and age is linear in each of the categories.</br>
* From this, we can determine that these 3 categories mean how bad the health condition of the patient is!</br>
* Southeast-ern people have the highest bmi, a median bmi of 33.33</br>
* Northeast-ern people have the lowest bmi, a median bmi of 28.88</br>
* The bmi of a person is independent of their gender</br>
* Looks like people smoke regardless of their gender</br>
* More Males seem to be smokers than females, but the difference is minimal, also the number of females tested is slightly less than the number of males.</br>
* It cannot be concluded that more males smoke because we do not have sufficient data.</br>
* Smokers usually have less children than non-smokers.</br>

## Step-4: Data Cleaning and PreProcessing
Data preprocessing is a crucial step in the data analysis and machine learning pipeline. It involves cleaning, transforming, and organizing raw data into a format that is suitable for analysis and modeling. Proper data preprocessing can significantly impact the accuracy and effectiveness of your analytical or machine learning models.</br>
* In our dataset, sex and smoker have 2 unique values, and region have more than 2 unique values.</br>
* Here, I am converting the columns with 2 unique values to binary (either 1 or 0)</br>
* And one-hot encode the other categorical columns which has more than 2 unique values</br>

## Step-5: Data Modelling
Once the dataset has been thoroughly explored, machine learning models can be applied to make predictions or forecasts.
Metrices we will be using are,</br>
           * Root Mean Square Error (RMSE)</br>
           * Mean Absolute Percentage Error (MAPE)</br>
           * Coefficient of Determination (R^2)</br>

The algorithms used for this model are:</br>
           * Random Forest</br>
           * Linear Regression</br>
           * Decision Tree</br>
           * Bayesian Ridge</br>

### Random Forest
A random forest is a meta estimator that fits a number of classifying decision trees on various sub-samples of the dataset and uses averaging to improve the predictive accuracy and control over-fitting. The sub-sample size is controlled with the max_samples parameter if bootstrap=True (default), otherwise the whole dataset is used to build each tree.

### Linear Regression
LinearRegression fits a linear model with coefficients w = (w1, …, wp) to minimize the residual sum of squares between the observed targets in the dataset, and the targets predicted by the linear approximation.

### Decision Tree
Decision tree builds regression or classification models in the form of a tree structure. It breaks down a dataset into smaller and smaller subsets while at the same time an associated decision tree is incrementally developed. The final result is a tree with decision nodes and leaf nodes.

### Bayesian Ridge
Bayesian regression allows a natural mechanism to survive insufficient data or poorly distributed data by formulating linear regression using probability distributors rather than point estimates. The output or response 'y' is assumed to drawn from a probability distribution rather than estimated as a single value.

## Step-6: Model Evaluation
By comparing the results and metrices value generated by all four algorithm, We come to a decision that The Random Forest algorithm is best suited one which give low error value and good accuracy rate.

## Conclusion

The Machine Learning model analyse the dataset and found insights from the data. The steps involved in this project, the dataset, the insights found is being briefed in this section.
