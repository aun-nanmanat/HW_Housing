# Prediction of Flat and House Rents in Delhi
## Data Overview and Preparation
The dataset used in this analysis contains various attributes related to housing prices in Delhi, such as area, location, number of bedrooms and bathrooms, balcony, lift, parking, property status, furnished condition, and more. 

## Pre-Processing
### Handling Missing Values
#### Replacing missing values with 0:
  - Pros: Maintains dataset structure and enables calculations without NA issues.

  - Cons: May introduce bias if missing values are not truly zero and assume missing values indicate absence rather than unknown or undefined.

### Log-Transformation
Applied log transformation to handle skewed data and make it easier to visualize and model.

### Splitting the Data
Split the data into 70% training and 30% testing sets to balance between model training and validation.

## Exploratory Analysis
### Mapping Space and Price per Square Meter
- **Original and Log-Transformed Price per Square Meter:**

  - Original map uses actual prices per square meter.

  - Log-transformed map uses log of prices per square meter to handle skewed data.

  - The original map is easier to interpret, but the log-transformed map better highlights price differences.

- **Original and Log-Transformed Area per Square Meter:**

  - Original map shows absolute sizes of flats and houses.

  - Log-transformed map normalizes values, highlighting relative size differences.

### Categories and Price
- **Price Comparisons Using Boxplots:**

  - Flats vs. Individual Houses

  - New vs. Resale Properties

  - Furnished vs. Unfurnished

  - Ready vs. Under-Construction Properties

  - **Insights:** Resale, unfurnished, and ready-to-move properties tend to be more cost-effective.

### Size and Price
- **Size and Price with Parking Availability:**

  - Visualized using original and log-transformed data.

  - Original data is more informative for real-world interpretation.

- **Size and Price with Balcony Availability:**

  - Similar approach to parking availability analysis.

## Hypothesis Testing
### Hypotheses Formulation
- **Hypothesis 1:** Size of Property (area_sqm)

  - *Null Hypothesis (H0):* No significant relationship between size and housing prices.

  - *Alternative Hypothesis (H1):* Significant relationship between size and housing prices.

- **Hypothesis 2: Parking Availability**

  - Null Hypothesis (H0): No significant relationship between parking and housing prices.

  - Alternative Hypothesis (H1): Significant relationship between parking and housing prices.

### Pre-processing Steps
Identified and addressed missing values and applied log-transformation to skewed data.

## Model Development
Developed multiple predictive models using selected predictors.

### Model 1: TM1 Model
- Predictor: area_sqm

- High R-squared value (0.725), indicating substantial explanation of price variability.

### Model 2: TM2 Model
- Predictor: parking

- Very low R-squared value (0.00025), indicating minimal explanation of price variability.

### Model 3: TM3 Model

- Predictors: area_sqm, Bathrooms, Bedrooms, Balcony

- High R-squared value (0.730), suggesting good model fit.

### Model 4: TM4 Model

- Predictors: parking, Bathrooms, Bedrooms, Balcony

- Moderate R-squared value (0.523), suggesting moderate model fit.

## Model Evaluation
Evaluated models using RMSE:

- TM3 Model: RMSE = 41462 (best performance)

- TM3ln Model (Log-transformed): RMSE = 44242

- PCA Model: RMSE = 48026

## Conclusion
Based on the analysis, the TM3 model with predictors area_sqm, Bathrooms, Bedrooms, and Balcony performed the best with an RMSE of 41462. This model effectively captures the significant predictors influencing housing prices in Delhi.

## Recommendations
For accurate rent predictions in Delhi:

- Focus on the area per square meter and the number of bathrooms.

- Consider log-transforming skewed data for better model performance.

- Further explore interactions and non-linear relationships for enhanced predictions.
