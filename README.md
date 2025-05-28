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

# Charts Generated For This Project
I used the Python language along with Jupyter Notebooks to perform some data preparation for machine learning and apply machine learning techniques on the dataset to find significant trends and patterns for the analysis. Before analyzing the data, I cleaned out NULL values, checked the data for inaccuracies, and transformed it into multiple tables separated by their countries. The CSV file used to generate graphs is a healthcare dataset from Kaggle that provides comprehensive statistics on healthcare from around the world.

I imported the common libraries used for Jupyter Notebook. The pandas library is an open-source tool for data analysis and manipulation in Python. It reads files and creates Dataframes and Series. The Matplotlib library is used to generate graphical representations of data in Python. The NumPy library works with arrays and performs mathematical calculations.
![Image](https://github.com/SMarbella/global-healthcare-dataset-analysis/blob/main/Imported%20Libraries/Basic%20Libraries.png)

I imported the set of libraries I need to perform some machine learning techniques. The comments label where I will use each machine learning technique.
![Image](https://github.com/SMarbella/global-healthcare-dataset-analysis/blob/main/Imported%20Libraries/Libraries%20for%20Graphs.png)
