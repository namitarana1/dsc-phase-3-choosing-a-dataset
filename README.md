![image](https://github.com/namitarana1/dsc-phase-3-choosing-a-dataset/blob/main/images/gettyimages-93065842-612x612.jpg)



# DRIVEN DATA: The Tanzanian Water Crisis
#### Author: Namita Rana
# Overview
Tanzania, as a developing country, struggles with providing clean water to its population of over 57,000,000. There are many water points already established in the country, but some are in need of repair while others have failed altogether. As a result, many people are suffering. In this project, the objective is to dive into this crisis, focusing on the analysis of water well functionality across the country in order to assess the level of the crisis and explore some possible solutions towards improving the situation for millions of people.

# Business Problem:
Almost half the population of Tanzania is without basic access to safe water. Although there are many water-points already established in the country, a lot of them are in need of repair while others have failed altogether. It can assist the Tanzanian Ministry of Water on identifying pumps that are in need of repair and/or no longer functional.Understanding which pumps will fail and which will not may help improve maintenance operations and ensure that clean water is available to people residing in Tanzania. Note that this is a ternary classification problem by default, but can be engineered to be binary. Stakeholder: Ministry of Water and Irrigation, Goverment of Tanzania.
## Dataset
The dataset provided on https://www.drivendata.org/ by Taarifa and the Tanzanian Ministry of Water.
For this dataset, there are two subsections to the problem description:
### Features
* List of features
### Labels
* List of labels
The features in this dataset are:
### The features in this dataset are:
* amount_tsh - Total static head (amount water available to waterpoint)
* date_recorded - The date the row was entered
* funder - Who funded the well
* gps_height - Altitude of the well
* installer - Organization that installed the well
* longitude - GPS coordinate
* latitude - GPS coordinate
* wpt_name - Name of the waterpoint if there is one
* num_private -
* basin - Geographic water basin
* subvillage - Geographic location
* region - Geographic location
* region_code - Geographic location (coded)
* district_code - Geographic location (coded)
* lga - Geographic location
* ward - Geographic location
* population - Population around the well
* public_meeting - True/False
* recorded_by - Group entering this row of data
* scheme_management - Who operates the waterpoint
* scheme_name - Who operates the waterpoint
* permit - If the waterpoint is permitted
* construction_year - Year the waterpoint was constructed
* extraction_type - The kind of extraction the waterpoint uses
* extraction_type_group - The kind of extraction the waterpoint uses
* extraction_type_class - The kind of extraction the waterpoint uses
* management - How the waterpoint is managed
* management_group - How the waterpoint is managed
* payment - What the water costs
* payment_type - What the water costs
* water_quality - The quality of the water
* quality_group - The quality of the water
* quantity - The quantity of water
* quantity_group - The quantity of water
* source - The source of the water
* source_type - The source of the water
* source_class - The source of the water
* waterpoint_type - The kind of waterpoint
* waterpoint_type_group - The kind of waterpoint

### Methods

 #### Cleaning and Feature Engineering

This project uses data cleaning and feature engineering to also addressed the class imbalance between classes we have used SMOTE. We also cleaned up our data, as there were missing values in multiple columns. For example, if "construction year" of the waterpoint had a missing value, we filled that value with the mean construction year of all waterpoints within that given region. We also engineered one column "age" to equal the age of the waterpoint when the data was collected. Cleaning our data and building these features helped make our model more interpretable and significant.

#### Models Development

Classification  was used in order to predict the status level of a pump. We trained four separate classifier models: K-Nearest Neighbor, Decision Trees,Random Forest, and XGBoost. Knn was our simplest model, and we tuned our models to get the best results.

# Model Evaluation 1

## Evaluation Metrics

Our target is multi-class with imbalance issue where we have a very few observations of water points that needs repair compared to the ones that are functioning. It was important to us to not miss the non functioning or need for repair cases, as it is directly related to the lives of people using that water points.

![image](https://github.com/namitarana1/dsc-phase-3-choosing-a-dataset/blob/main/images/status_spread.png)

So for our model evaluation, we prioritized the Accuracy and precision.We also specifically focussed on minimizing the false positives which is model predicts non functional but is actually functional, which can in-turn lead to wastage of resources.
Additionally weighted F1 score was considered for overall performance.

# Class Imbalance

Our dataset has high class imbalance issue we tried to fix it using SMOTE.

We tested a number of models including ...

kNearestNeighbors
Decision Tree
Random Forest
XGBoost
Hyperparameter tuning was GridSearchCV.



#### Results

Our simplest model,XGBoost came back with a confusion matrix that produced a 82% accuracy score and a 86% precision score. For our purposes, we were looking to maximize precision as we want to reduce the amount of False positives (predicting the pump as non- functional when it is functional).

#### Future Work
* In the near future important features identified through the models can be explored in order to narrow down recommendations towards specific action points.

* Looking at features like quality of water, its quantity,  and other such features to assess their impact on well functionality to provide more specific location recommendations for water pump development.

* Based on the model results and feature weights we recommend that the minister of water and irrigation deploy resources to conduct additional due diligence on water sources where wells are being installed. In addition, there is strong evidence of lack of functionality for wells installed at higher levels. We suggest adding using government oversight to make sure wells are installed at lower levels where possible. Our final recommendation is to setup a new fund / organization to review and repair older wells in cooperation with non-governmental organizations assisting with wells construction

## For More Information

Please review my full analysis in [my Jupyter Notebook](https://github.com/namitarana1/Tanzanian_WaterWells_Project/blob/main/Notebook/Tanzanian_Well_Project.ipynb).

For any additional questions,
please contact:
- Namita Rana at <namitarana21@gmail.com>

## Repository Structure

```
├── Images<- 
├── Docs
├── Tanzanian_Well_Project.pptx                               
└── Tanzanian_Well_Project.ipynb                           
```
