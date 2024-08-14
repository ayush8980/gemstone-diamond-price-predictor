## Introduction About the Data :
***

The dataset The goal is to predict **_price_** of given diamond (Regression Analysis).

There are 10 independent variables (including id):

* **_id_** : unique identifier of each diamond
* **_carat_** : Carat (ct.) refers to the unique unit of weight measurement used exclusively to weigh gemstones and diamonds.
* **cut** : Quality of Diamond Cut
* **_color_** : Color of Diamond
* **_clarity_** : Diamond clarity is a measure of the purity and rarity of the stone, graded by the visibility of these characteristics under 10-power magnification.
* **_depth_** : The depth of diamond is its height (in millimeters) measured from the culet (bottom tip) to the table (flat, top surface)
* **_table_** : A diamond's table is the facet which can be seen when the stone is viewed face up.
* **_x_** : Diamond X dimension
* **_y_** : Diamond Y dimension
* **_z_** : Diamond Z dimension

Target variable:
* **_price_** : Price of the given Diamond.

 Dataset Source Link : https://www.kaggle.com/competitions/playground-series-s3e8/data?select=train.csv

#### It is observed that the categorical variables 'cut', 'color' and 'clarity' are ordinal in nature

#### Check this link for details : [American Gem Society](https://www.americangemsociety.org/ags-diamond-grading-system/)



## Screenshot of UI
***

SS Link: https://drive.google.com/file/d/13dvthrqhI6lFD1vUrvzY2e0AOJdT_Q59/view?usp=sharing




## Approach for the project
***

1. ### Data Ingestion :
* In Data Ingestion phase the data is first read as csv.
* Then the data is split into training and testing and saved as csv file.

2. ### Data Transformation :
* In this phase a ColumnTransformer Pipeline is created.
* for Numeric Variables first SimpleImputer is applied with strategy median , then Standard Scaling is performed on numeric data.
* for Categorical Variables SimpleImputer is applied with most frequent strategy, then ordinal encoding performed , after this data is scaled with Standard Scaler.
* This preprocessor is saved as pickle file.

3. ### Model Training :
* In this phase base model is tested . The best model found was Decision Tree regressor.
* R2 score of the model was found to be close to 95.5%.
* This model is saved as pickle file.

4. ### Prediction Pipeline :
* This pipeline converts given data into dataframe and has various functions to load pickle files and predict the final results in python.

5. ### Flask App creation :
* Flask app is created with User Interface to predict the gemstone prices inside a Web Application.

6. ### Exploratory Data Analysis Notebook
* [EDA Notebook](https://github.com/Ayan-OP/Diamond_Price_Predictor_Project/blob/main/notebooks/EDA.ipynb)

7. ### Model Training Approach Notebook
* [Model Training Notebook](https://github.com/Ayan-OP/Diamond_Price_Predictor_Project/blob/main/notebooks/Model%20Training.ipynb)
