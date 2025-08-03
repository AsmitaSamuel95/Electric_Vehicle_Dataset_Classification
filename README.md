# Electric Vehicle Eligibility Classification

## This project analyzes electric vehicle data to classify vehicle eligibility for clean alternative fuel programs using machine learning models, coupled with thorough data preprocessing and visualization.

## Dataset used – Electric_Vehicle_Population_Data.csv 
Website used - US Government's Data: https://www.data.gov/ 
This dataset contains information about vehicles that are eligible to be powered by non
traditional fuels or energy sources that produce lower emissions compared to 
conventional gasoline or diesel-powered vehicles. 
Type of Data- 
- Categorical Data: 
  - Vehicle Make(brand or manufacturer of vehicle), Model(specific version or 
  name of a vehicle), Electric Vehicle Type(Electric Vehicle Classification), 
  Electric Utility(Electric Service Provider), VIN (Vehicle Identification 
  Number), and Clean Alternative Fuel Vehicle (CAFV) Eligibility are 
  categorical variables.  
- Numerical Data: 
  - Model Year, Electric Range, DOL Vehicle ID, and Base MSRP are numerical 
  features, representing continuous values. 
- Geographical Data: 
  - County, City, State, Postal Code, Legislative District, Vehicle Location 
  (coordinates), and 2020 Census Tract provide geographical context for the 
  vehicle's location.

## Preprocessing techniques applied – 
- Missing Value Handling 
  - Printing total number of missing values per column 
  - Dropping Columns with missing values- 
    - Dropped Legislative District as it has a large number of missing values 
    and is not relevant 
    - Dropped Vehicle Location as it has some missing values and is not 
    relevant 
    - Dropped 2020 Census Tract as it has some missing values and is not 
    relevant 
- Dropping rows with missing values as we have enough number of rows/data 
- Outlier Handling 
  - Removing Vehicles with Zero Electric Range 
    - Filters out any rows where the Electric Range column has a value of 0. It 
    assumes that vehicles with a zero electric range are outliers or invalid 
    records, as electric vehicles should have a non-zero range. 
  - Removing Vehicles with Unknown CAFV Eligibility 
    - Removes rows where the Clean Alternative Fuel Vehicle (CAFV) Eligibility 
    column contains the value 'Eligibility unknown as battery range has not 
    been researched'. Such rows have an unknown eligibility status, which 
    will not be relevant for analysis. 
- Converting features with string datatype to categorical using label encoding 
  - Converted Make, Electric Vehicle Type into categorical datatype as we will use 
  these columns as features 
  - Converted Clean Alternative Fuel Vehicle (CAFV) Eligibility into categorical 
  datatype as we will use this column as the target 
- Calculating correlation with target and dropping columns with low correlation and 
are not needed 
  - Dropped DOL Vehicle ID and Postal Code as they have low correlation and are 
  not needed 
- Normalization 
  - Performed on all numerical features so they can have the same scale 
  - The MinMaxScaler is used to scale values of numerical columns between 0 and 
  1, ensuring uniformity across features

## 5 visualization techniques 
- Electric Range Distribution
  Observation- 
  Maximum number of vehicles have electric range between 0 and 50 
- Count of vehicles by Make
  Observation- 
  Tesla has the greatest number of vehicles in this dataset 
- Electric Vehicle Type vs. Clean Alternative Fuel Vehicle Eligibility
  Observation- 
  All Battery Electric Vehicles are eligible for Clean Alternative Fuel Vehicles 
- Count of models which are not CAFV eligible
  Observation- 
  Wrangler has the greatest number of vehicles that are not eligible for CAFV 
- Count of models which are CAFV eligible
  Observation- 
  Model 3 has the greatest number of vehicles that are eligible for CAFV

## How to Run
You can run the Jupyter Notebook file directly using Google Colab without installing anything locally:

1. Open Google Colab in your web browser.

2. Click File > Upload notebook.

3. Choose the .ipynb file from your computer and upload it.

4. Run the code cells by clicking the Run button, next to each cell or press Shift + Enter.

5. To run all cells sequentially, go to Runtime > Run all.

6. The notebook will be automatically saved in your Google Drive under the Colab Notebooks folder.
