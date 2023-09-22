<div align="center">
<centre><h1>Medical Insurance Prediction</h1><br />
</div>

 <div align="center">
<img  width = "600" src = "https://github.com/SruthiSreeSG/Medical_Insurance_Prediction/assets/140688742/0b88f222-3a3f-4647-9198-3cb9d5aedc81">
 </div>

<div>
<centre><h2>Introduction</h2><br />
</div>
 
  The project titled "Medical Insurance EDA and Forecast" likely involves using machine learning techniques to perform exploratory data analysis (EDA) on a dataset related to medical insurance and then using this analysis to forecast or make predictions about future trends or outcomes in the context of medical insurance. 

<div align="center">
<centre><h1>Intel DevCloud</h1><br />
</div>

 <div align="center">
<img width ="300" src ="https://github.com/SruthiSreeSG/Medical_Insurance_Prediction/assets/140688742/5a7af305-af22-4ace-846e-668e0803e096">
 </div>


DevCloud for oneAPI provides a library of highly optimized algorithms for data preprocessing and analysis, specifically designed to accelerate machine learning
workloads on a diverse set of Intel architectures. DevCloud is an all-in-one online destination to test the performance of your AI models on Intel processors. It's a dedicated space that allows developers and engineers to innovate in a production-ready space. What's great about this platform is that it gives you access to dedicated Intel technology – without having to invest in hardware upfront. 

<centre><h3>Key Features</h3><br />
* The latest Intel hardware, including Intel Core processors, Intel Xeon Scalable processors, Intel IoT developer kits and Intel FPGAs
* Intel-optimized frameworks – the latest version of OpenVINO

This project is executed in Jupyter Notebook provided by Intel DevCloud, in One API platform



Let me break down the project steps:
<div>
<centre><h2>Step-1:Importing libraries</h2><br />
</div>
 
* **For ML Models:** sklearn</br>
* **For Data Processing:** numpy, pandas, sklearn</br>
* **For Data Visualization**: matplotlib, seaborn, plotly</br>

<div>
<centre><h3>Setting up sklearnex to speed up training</h3><br />
</div>
 
  If you don't know about sklearnex, this is a tool you can use to speed up training sklearn models, without having to change any code.</br>
  A simple 2 line of code can speed up training by 2x.

<div>
<centre><h2>Step-2: About the DataSet</h2><br />
</div>
 
The dataset named "Insurance" is being used for this project which is in .csv format.This dataset contains some basic features of the patient and the expenses for the treatment.
The dataset is downloaded from kaggle website.</br>
The Dataset link: https://github.com/stedy/Machine-Learning-with-R-datasets/blob/master/insurance.csv

<div>
<centre><h3>Column Descriptions</h3><br />
</div>
 
* **age:** age of primary beneficiary</br>
* **sex:** insurance contractor gender, female, male</br>
* **bmi:** Body mass index, providing an understanding of body, weights that are relatively high or low relative to height, objective index of body weight
 (kg / m ^ 2) using the ratio of height to weight, ideally 18.5 to 24.9</br>
* **children:** Number of children covered by health insurance / Number of dependents</br>
* **smoker**: Smoking</br>
* **region:** the beneficiary's residential area in the US, northeast, southeast, southwest, northwest.</br>
* **expenses**: Individual medical costs billed by health insurance</br>

**Categorical Features**
sex, smoker, region
**Continuous Features**
age, children, bmi, charges

<div>
<centre><h2>Step-3: Exploratory Data Analysis</h2><br />
</div>
 
 EDA is the process of summarizing and visualizing data to understand its main characteristics, uncover patterns, and identify potential relationships or trends. In the context of this project, EDA may involve tasks such as:

* **Data Cleaning:** Removing or handling missing values and outliers.</br>
* **Descriptive Statistics:** Calculating basic statistics like mean, median, and standard deviation to get a sense of the data's distribution.</br>
* **Descriptive Statistics:** Calculating basic statistics like mean, median, and standard deviation to get a sense of the data's distribution.</br>
* **Data Visualization:** Creating charts and graphs to visualize trends and relationships in the data.</br>
* **Feature Engineering:** Creating new features or modifying existing ones to improve model performance.</br>

<div>
<centre><h3>Insights from EDA</h3><br />
</div>

<img src = "https://github.com/SruthiSreeSG/Medical_Insurance_Prediction/assets/140688742/aaf876a3-4c31-4f75-bbe1-62fc38265350"></br>
The above image depict that,
* Individuals who smoke have a higher medical bill than individuals who do not smoke.</br>
* We can see 3 categories of medical bill paid, 0-15k, 15k-32k, 32k-50k.</br>

<img src = "https://github.com/SruthiSreeSG/Medical_Insurance_Prediction/assets/140688742/36f04084-e818-440e-9d28-aacd95d104fc"></br>

* It can be seen that those 3 categories of expenses has a strong correlation with age.</br>
* The correlation of expenses and age is linear in each of the categories.</br>
* From this, we can determine that these 3 categories mean how bad the health condition of the patient is!</br>

<img src = "https://github.com/SruthiSreeSG/Medical_Insurance_Prediction/assets/140688742/5f90031f-29bb-4974-b2af-f11951b32204"></br>
* Southeast-ern people have the highest bmi, a median bmi of 33.33</br>
* Northeast-ern people have the lowest bmi, a median bmi of 28.88</br>

<img src = "https://github.com/SruthiSreeSG/Medical_Insurance_Prediction/assets/140688742/d9ae160f-94ca-4ef2-bb1a-7bb4d49bdacd"></br>
* The bmi of a person is independent of their gender</br>

<img src = "https://github.com/SruthiSreeSG/Medical_Insurance_Prediction/assets/140688742/105be7e6-3f5b-4789-855e-3c9ba4573a4d"></br>
* Looks like people smoke regardless of their gender</br>
* More Males seem to be smokers than females, but the difference is minimal, also the number of females tested is slightly less than the number of males.</br>
* It cannot be concluded that more males smoke because we do not have sufficient data.</br>

<img src = "https://github.com/SruthiSreeSG/Medical_Insurance_Prediction/assets/140688742/8dc94fb0-c17b-487c-85b0-c478bf9b5a49"></br>
* We can analyse that Smokers usually have less children than non-smokers.</br>

<div>
<centre><h2>Step-4: Data Cleaning and PreProcessing</h2><br />
</div>
 
Data preprocessing is a crucial step in the data analysis and machine learning pipeline. It involves cleaning, transforming, and organizing raw data into a format that is suitable for analysis and modeling. Proper data preprocessing can significantly impact the accuracy and effectiveness of your analytical or machine learning models.</br>
* In our dataset, sex and smoker have 2 unique values, and region have more than 2 unique values.</br>
* Here, I am converting the columns with 2 unique values to binary (either 1 or 0)</br>
* And one-hot encode the other categorical columns which has more than 2 unique values</br>

<div>
<centre><h2>Step-5: Data Modelling</h2><br />
</div>
 
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

<div>
<centre><h3>Random Forest</h3><br />
</div>
 
A random forest is a meta estimator that fits a number of classifying decision trees on various sub-samples of the dataset and uses averaging to improve the predictive accuracy and control over-fitting. The sub-sample size is controlled with the max_samples parameter if bootstrap=True (default), otherwise the whole dataset is used to build each tree.

<div>
<centre><h3>Linear Regression</h3><br />
</div>
 
LinearRegression fits a linear model with coefficients w = (w1, …, wp) to minimize the residual sum of squares between the observed targets in the dataset, and the targets predicted by the linear approximation.

<div>
<centre><h3>Decision Tree</h3><br />
</div>
 
Decision tree builds regression or classification models in the form of a tree structure. It breaks down a dataset into smaller and smaller subsets while at the same time an associated decision tree is incrementally developed. The final result is a tree with decision nodes and leaf nodes.

<div>
<centre><h3>Bayesian Ridge</h3><br />
</div>
 
Bayesian regression allows a natural mechanism to survive insufficient data or poorly distributed data by formulating linear regression using probability distributors rather than point estimates. The output or response 'y' is assumed to drawn from a probability distribution rather than estimated as a single value.

<div>
<centre><h2>Step-6: Model Evaluation</h2><br />
</div>
 Model evalution involves comparission of all the models used and concluding the best one.For this evaluation, we should consider the evaluation metrics: 
 Mean Squared Error (MSE), 
 Mean Absolute Percentage Error (MAPE), and
 R-squared (R2) score. 

Here's a brief interpretation of the metrics:

1. **MSE (Mean Squared Error)**: It measures the average squared difference between actual and predicted values. Lower MSE indicates better performance.

2. **MAPE (Mean Absolute Percentage Error)**: It measures the average percentage difference between actual and predicted values. Lower MAPE is better, as it indicates a smaller percentage error.

3. **R2 Score (R-squared)**: It measures the proportion of the variance in the dependent variable (target) that is predictable from the independent variables (features). Higher R2 score is better, as it indicates a better fit of the model to the data.

Based on these metrics:

- **RandomForestRegressor** has the lowest MSE (4355.29), which suggests it has the smallest average squared difference between actual and predicted values.

- **RandomForestRegressor** also has a relatively low MAPE (0.332), indicating a lower percentage error on average.

- **RandomForestRegressor** has the highest R2 score (0.8808), indicating the best fit of the model to the data among the models listed.
 <div align="center">
<img src = "https://github.com/SruthiSreeSG/Medical_Insurance_Prediction/assets/140688742/4ea6d33b-4c4e-4e63-bca2-9f966c741cc5">
</div>
So, based on these metrics, the RandomForestRegressor appears to be the best model among the ones you've listed. However, it's essential to consider the specific context and requirements of your problem when choosing a model, as different applications may prioritize different metrics.

<div>
<centre><h2>Conclusion</h2><br />
</div>

The Machine Learning model analyse the dataset and found insights from the data. The steps involved in this project, the dataset, the insights found is being briefed in this section.Out of all the models Random Forest model is giving the highest accuracy this means predictions made by this model are close to the real values as compared to the other model.

The dataset we have used here was small still the conclusion we drew from them were quite similar to what is observed in the real-life scenario. If we would have a bigger dataset then we will be able to learn even deeper patterns in the relation between the independent features and the premium charged from the buyers.
