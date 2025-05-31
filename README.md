# Global Healthcare Dataset Analysis
## Data Information
This project uses a mock healthcare CSV dataset from Kaggle that provides comprehensive statistics on healthcare from around the world. The dataset includes health statistics from countries that vary in geography and economic factors. There are 1,000,000 records in the dataset.

## Source
**Title:** Global Health Statistics

**Date of Study:** 2024

**Author:** Malaiarasu G Raj

**Affiliation:** Kaggle

**Relevant Information:** This is a mock dataset that simulates various diseases, treatments, and outcomes.

**Source:** https://doi.org/10.34740/kaggle/dsv/10028650

## Table Columns
Country - The name of the country where the health data was recorded.

Year - The year in which the data was collected.

Disease Name - The name of the disease or health condition tracked.

Disease Category - The category of the disease (e.g., Infectious, Non-Communicable).

Prevalence Rate (%) - The percentage of the population affected by the disease.

Incidence Rate (%) - The percentage of new or newly diagnosed cases.

Mortality Rate (%) - The percentage of the affected population that dies from the disease.

Age Group - The age range most affected by the disease.

Gender - The gender(s) affected by the disease (Male, Female, Both).

Population Affected - The total number of individuals affected by the disease.

Healthcare Access (%) - The percentage of the population with access to healthcare.

Doctors per 1000 - The number of doctors per 1000 people.

Hospital Beds per 1000 - The number of hospital beds available per 1000 people.

Treatment Type - The primary treatment method for the disease (e.g., Medication, Surgery).

Average Treatment Cost (USD) - The average cost of treating the disease in USD.

Availability of Vaccines/Treatment - Whether vaccines or treatments are available.

Recovery Rate (%) - The percentage of people who recover from the disease.

DALYs - Disability-Adjusted Life Years, a measure of disease burden.

Improvement in 5 Years (%) - The improvement in disease outcomes over the last five years.

Per Capita Income (USD) - The average income per person in the country.

Education Index - The average level of education in the country.

Urbanization Rate (%) - The percentage of the population living in urban areas.

## Retrieved table from
- https://www.kaggle.com/datasets/malaiarasugraj/global-health-statistics/data

# Charts and Calculations Generated For This Project
I used the Python language along with Jupyter Notebooks to perform some data preparation for machine learning and apply machine learning techniques on the dataset to find significant trends and patterns for the analysis. Before analyzing the data, I cleaned out NULL values, checked the data for inaccuracies, and transformed it into multiple tables separated by their countries. The CSV file used to generate graphs is a healthcare dataset from Kaggle that provides comprehensive statistics on healthcare from around the world.

## Jupyter Notebooks Libraries
I imported the common libraries used for Jupyter Notebook. The pandas library is an open-source tool for data analysis and manipulation in Python. It reads files and creates Dataframes and Series. The Matplotlib library is used to generate graphical representations of data in Python. The NumPy library works with arrays and performs mathematical calculations.

![Image](https://github.com/SMarbella/global-healthcare-dataset-analysis/blob/main/Imported%20Libraries/Basic%20Libraries.png)

I imported the set of libraries I need to perform some machine learning techniques. The comments label where I will use each machine learning technique.

![Image](https://github.com/SMarbella/global-healthcare-dataset-analysis/blob/main/Imported%20Libraries/Libraries%20for%20Graphs.png)

## First 10 Rows of Raw Data Table
I downloaded my CSV file from Kaggle to my local drive. Then, I imported the libraries I need for my Python code to access machine learning functions. I extracted the path of my CSV file from my local drive into Jupyter Notebook. The headers are Country, Year, Disease Name, Disease Category, Prevalence Rate (%), Incidence Rate (%), Mortality Rate (%), Age Group, Gender, Population Affected, Healthcare Access (%), Doctors per 1000, Hospital Beds per 1000, Treatment Type, Average Treatment Cost (USD), Availability of Vaccines/Treatment, Recovery Rate (%), DALYs, Improvement in 5 Years (%), Per Capita Income (USD), Education Index, and Urbanization Rate (%).

I noticed some inconsistent or incorrect data points in the dataset. I needed to perform some data cleansing operations. I wanted to know the names of diseases, disease types, and treatment types recorded on the table. Ebola, Parkinson’s Disease, and Malaria cannot be treated with surgery.

![Image](https://github.com/SMarbella/global-healthcare-dataset-analysis/blob/main/Graphs/10%20Rows%20Raw%20Data.png)

## Data Exploration
I collected the names of all diseases, disease categories, and treatment types from the table.
![Image](https://github.com/SMarbella/global-healthcare-dataset-analysis/blob/main/Data%20Exploration/List%20of%20Diseases%2C%20Treatments%2C%20and%20Disease%20Categories.png)

## Data Cleaning
Before fixing incorrect information, I counted the number of NULL values per column. Since there are no NULL values, I did not have to drop or fill any rows.

![Image](https://github.com/SMarbella/global-healthcare-dataset-analysis/blob/main/Data%20Cleaning/Find%20Nulls.png)

I corrected the information for the categories and treatment types for all diseases. Cancer is a special case where it can be treated with either Chemotherapy or Surgery or both.
![Image](https://github.com/SMarbella/global-healthcare-dataset-analysis/blob/main/Data%20Cleaning/Correct%20Inconsistencies.png)

I displayed the data to show the updated information for each disease. Ebola, Parkinson’s Disease, and Malaria are no longer treated with surgery. Their treatments have been corrected with their appropriate remedies in real life.
![Image](https://github.com/SMarbella/global-healthcare-dataset-analysis/blob/main/Data%20Cleaning/Fixed%20Information.png)

Next, I wanted to split the table by country to organize the data and work with a smaller dataset. I printed the list of countries. It allows me to choose which countries I want to analyze the data from. I can decide to analyze data from Italy, France, Turkey, and other countries included in the printed list. I named each table after the countries they represent. Since there are plenty of countries, I did not make tables for all of them. I chose to analyze data from the USA, Italy, Japan, and Indonesia.
![Image](https://github.com/SMarbella/global-healthcare-dataset-analysis/blob/main/Data%20Cleaning/Split%20Into%20Countries.png)

I dropped the Country column for each country because all the data in each table comes from one country. I made a table for USA data. I used the same procedure to create tables for Italy, Japan, and Indonesia.
![Image](https://github.com/SMarbella/global-healthcare-dataset-analysis/blob/main/Data%20Cleaning/One%20Country%20Table.png)

## Finding Feature Importances
I prioritized data from the USA table. I started building the train and test data to gather feature importances. I wanted to find the feature importances when the target columns are Prevalence Rate (%), Recovery Rate (%), and Mortality Rate (%). It will give me insight into which feature greatly affects machine learning predictions. I split the data into train and test data. I fit a Random Forest Regressor model.
![Image](https://github.com/SMarbella/global-healthcare-dataset-analysis/blob/main/Feature%20Importances/Choosing%20Feature%20Importances.png)

I got the feature importance percentages from my Random Forest Regressor model. It displays the importances for each column with the highest on top and lowest on bottom. Recovery rate has the biggest impact on my machine learning model. I visualized these feature importance percentages in a bar graph. I measured the feature importances from my Random Forest Regressor model based on mean decrease in impurity. I measured the elapsed time.
![Image](https://github.com/SMarbella/global-healthcare-dataset-analysis/blob/main/Feature%20Importances/Feature%20Importance%20Measurements.png)

I measured the feature importances from my Random Forest Regressor model based on permutation. I measured the elapsed time. The mean decrease in impurity method performed the calculation faster than the permutation method. The feature importances help me understand which target column largely impacts my machine learning model’s prediction performance. Since the Recovery Rate (%) column has the highest feature importance, I chose it to see how my machine learning algorithms will perform. I will test it on Random Forest, Lasso, Gradient Boosting, and Stacking Regressor machine learning models.
![Image](https://github.com/SMarbella/global-healthcare-dataset-analysis/blob/main/Feature%20Importances/Feature%20Importances%20Using%20Permutation%20on%20Full%20Model.png)

## Using Different Feature Importances
I used a column selector function make_column_selector() from sklearn.compose to show the columns that are categorical and other columns that are numerical. The pipeline requires a preprocessor for tree-based models. I made tree preprocessors for categorical columns and numerical columns. I defined the preprocessor for a linear model ending regressor for both categorical columns and numerical columns. After I completed making the tree preprocessors, I started to make the models. I made a Lasso model, a Random Forest Regressor model, Gradient Boosting Regressor model, and a Stacking Regressor model. I made a plot to generate my graphs. The graphs generated to show that Random Forest fits the truth line the best.
![Image](https://github.com/SMarbella/global-healthcare-dataset-analysis/blob/main/Graphs/Regressor%20Lines%20from%20Models.png)

I tested the same models on a feature with weaker importance called Mortality Rate (%). Since I already have a pipeline with my four machine learning algorithms, I skipped directly to the code that creates the graphs.
![Image](https://github.com/SMarbella/global-healthcare-dataset-analysis/blob/main/Graphs/Weaker%20Regressor%20Lines%20from%20Models.png)

## USA Calculations
Using a different selection of columns, I encoded the categorical columns into Python dictionaries with defined numeric codes. I made new test and train sets for a Random Forest Classifier machine learning model. I made a Random Forest Classifier model, fit it to the training data, and used the test data to make predictions. I made a sample prediction of the next USA patient and average treatment cost. The printed output comes from the sample prediction. It says that the most likely person will be 0-18 years old and will pay $37,330 to have the Zika virus treated.
![Image](https://github.com/SMarbella/global-healthcare-dataset-analysis/blob/main/Calculations/sample%20prediction%20of%20the%20next%20USA%20patient%20and%20average%20treatment%20cost.png)

I added the Mortality Rate (%) and Recovery Rate (%) columns to see if the predicted treatment cost changes. The treatment cost increased by about $1,000 after learning about the mortality and recovery rates in the USA. This time, the person will be the same age and will pay the same amount to have the Zika virus treated. The predicted average treatment cost for patients in the USA is $37,076.
![Image](https://github.com/SMarbella/global-healthcare-dataset-analysis/blob/main/Calculations/Mortality%20Rate%20(%25)%20and%20Recovery%20Rate%20(%25)%20columns.png)

I wanted to focus on healthcare access and quality and how their factors affect Prevalence Rate (%), Recovery Rate (%), and Mortality Rate (%). The predictions are slightly off from the actual values. The Random Forest Regressor model overpredicted the Prevalence Rate (%) but underpredicted the Recovery Rate (%) and Mortality Rate (%). A 1.08 mean squared error means that the machine learning model’s predictions are quite close to the actual values. The R-squared value is close to 1, meaning the variables are highly dependent.
![Image](https://github.com/SMarbella/global-healthcare-dataset-analysis/blob/main/Calculations/USA%20Patient%20Survival%20Predictions.png)

I added different target columns. I removed the Prevalence Rate (%) column and added Healthcare Access (%), Doctors per 1000, and Hospital Beds per 1000. I adjusted both the predicted and actual values to their corresponding columns. The Random Forest Regressor model underpredicted Healthcare Access (%), Doctors per 1000, Recovery Rate (%), and Mortality Rate (%). The mean squared error is higher, meaning that it performed worse than the previous dataset that used fewer target columns. The R-squared score shows that the variables are slightly more independent.
![Image](https://github.com/SMarbella/global-healthcare-dataset-analysis/blob/main/Calculations/USA%20Healthcare%20Access%20Outcome%20Predictions.png)

## Japan Calculations
I used the same method on a different table for Japan. This time, the predicted patient will be 19-35 years old, have COVID-19, and pay $4,378 to have it treated. The predicted average treatment cost for Japanese patients is $17,868.
![Image](https://github.com/SMarbella/global-healthcare-dataset-analysis/blob/main/Calculations/Predicted%20Japanese%20Patient.png)

I used the same method for a different country. This time, the predicted and actual values for patient survival are different. The prevalence and recovery rates are lower than those in the USA. Japan has a higher mortality rate. Similarly, the Random Forest Regressor overpredicted the Prevalence Rate (%) and Recovery Rate (%) but underpredicted the Mortality Rate (%). The mean-squared error shows that the model is quite good at predicting values. The R-squared score is very close to 1, showing that the variables are dependent.

![Image](https://github.com/SMarbella/global-healthcare-dataset-analysis/blob/main/Calculations/Japan%20Patient%20Survival%20Predictions.png)

The healthcare access and hospital beds per 1000 are higher in Japan than in the USA, but there are fewer doctors, a lower recovery rate, and higher mortality rates. The Random Forest Regressor model overpredicted healthcare access and Recovery Rate (%). It underpredicted Doctors per 1000, Beds per 1000, and Mortality Rate (%). There is a higher mean squared error, meaning the model’s predictions are worse than the Patient Survival predictions. The R-squared score shows that the variables are somewhat dependent.

![Image](https://github.com/SMarbella/global-healthcare-dataset-analysis/blob/main/Calculations/Japan%20Healthcare%20Access%20Outcome%20Predictions.png)

## Indonesia Calculations
I used the same method for Indonesia. The predicted patient will be about 0-18 years old and will pay $34,387 to have the Zika virus treated. The predicted average treatment cost for Indonesian patients is $40,673.
![image](https://github.com/SMarbella/global-healthcare-dataset-analysis/blob/main/Calculations/Predicted%20Indonesian%20Patient.png)

The Indonesian Patient Survival Predictions have similar Random Forest Regressor prediction errors, mean squared errors, and R-squared score to those found in the Patient Survival Predictions in the USA, Japan, and Italy. According to the R-squared score, the variables are very dependent.

![Image](https://github.com/SMarbella/global-healthcare-dataset-analysis/blob/main/Calculations/Indonesia%20Patient%20Survival%20Predictions.png)

The Indonesian Healthcare Access Outcome Predictions have similar Random Forest Regressor prediction errors, mean squared errors, and R-squared score to those found in the Healthcare Access Outcome Predictions in the USA, Japan, and Italy. According to the R-squared score, the variables are somewhat more independent.

![Image](https://github.com/SMarbella/global-healthcare-dataset-analysis/blob/main/Calculations/Indonesia%20Healthcare%20Access%20Outcome%20Predictions.png)

## Italy Calculations
I used the same method for Italy. The predicted patient is 36-60 years old and will pay $7,740 to have Influenza treated. The average treatment cost for Italian patients is $34,912.
![Image](https://github.com/SMarbella/global-healthcare-dataset-analysis/blob/main/Calculations/Predicted%20Italian%20Patient.png)

The Random Forest Regressor model underpredicted Prevalence Rate (%) and Mortality Rate (%). It overpredicted Recovery Rate (%). The Random Forest Regressor model performed similarly on Italian patient survival prediction data, having similar mean squared error and R-squared scores to the patient survival predictions of both USA and Japan.

![Image](https://github.com/SMarbella/global-healthcare-dataset-analysis/blob/main/Calculations/Italy%20Patient%20Survival%20Predictions.png)

The prediction errors are like the ones found in the healthcare access predictions from Japan and USA. The Random Forest Regressor performed worse with a higher mean squared error on healthcare access outcome predictions than on patient survival predictions. It has a similar R-squared score to the healthcare access outcome predictions from Japan and the USA.

![Image](https://github.com/SMarbella/global-healthcare-dataset-analysis/blob/main/Calculations/Italy%20Healthcare%20Access%20Outcome%20Predictions.png)

# Summary
First, I imported the global healthcare dataset CSV file from Kaggle, which includes inconsistent data for each disease. I imported the libraries I needed to perform the machine learning operations on the dataset. I checked for NULL values and found that there are no NULL values. I collected lists of disease names, disease categories, and treatment types to fix the information and make it consistent and more accurate. Since the dataset consists of data from many countries mixed into one table, I gathered the list of countries and split the data into separate tables by country.

I started building the train and test data to gather feature importances. I wanted to find the feature importances when the target columns are Prevalence Rate (%), Recovery Rate (%), and Mortality Rate (%). After I printed the percentages of feature importances and found out the column that makes the most impact on the machine learning model’s prediction performance, I visualized the result into bar graphs. The feature importances help me understand which target column largely impacts my machine learning model’s prediction performance. Since the Recovery Rate (%) column has the highest feature importance, I chose it to see how my machine learning algorithms will perform. I tested it on Random Forest, Lasso, Gradient Boosting, and Stacking Regressor machine learning models. I visualized the four models and found that different feature importance strengths impact the prediction accuracy of all models, with higher feature importance giving more accurate predictions.

To further data exploration, I made new test and train data to train new Random Forest Regressor and Random Forest Classifier models on USA, Japan, Italy, and Indonesia. The Random Forest Classifier predicted the next likely patient and the country’s average treatment cost to treat a patient. The Random Forest Regressor predicted patient survival and healthcare access outcomes. Overall, the Random Forest Regressor has a higher mean squared error on healthcare access outcome predictions than on patient survival in all countries. The R-squared score on patient survival shows more dependent variables than those from the healthcare access outcome.
