**Problem Overview**
SmartManufacture Inc., a leader in industrial automation, has deployed an extensive sensor network across a client's manufacturing facility to monitor environmental conditions and energy usage. The client is concerned about rising energy costs and seeks a predictive system to forecast equipment energy consumption based on various environmental factors and sensor readings from different factory zones.

**Objective** 
Develop a robust machine learning model to accurately predict equipment energy consumption (equipment_energy_consumption) using sensor data. This predictive capability aims to assist facility managers in optimizing operations for enhanced energy efficiency and cost reduction.

**Dataset Description**
The dataset comprises time-stamped sensor measurements from a manufacturing facility, including:

Energy consumption readings for equipment and lighting

Temperature and humidity readings from 9 distinct zones within the facility

Outdoor weather conditions (temperature, humidity, pressure, etc.)

**Methodology**
**Data Preprocessing**
Converted non-timestamp columns to numeric, coercing errors to NaN

Dropped rows with missing equipment_energy_consumption values

Imputed missing values in features using the median strategy

Extracted temporal features: hour of the day, day of the week, and weekend indicator

Removed random_variable1 and random_variable2 due to negligible correlation with the target variable

**Exploratory Data Analysis (EDA)**
Visualized the distribution of equipment energy consumption

Analyzed correlations between features and the target variable

Examined average energy consumption by hour of the day

**Modeling**
Implemented and tuned the following regression models using pipelines and GridSearchCV:

Random Forest Regressor

Gradient Boosting Regressor

XGBoost Regressor

Each model pipeline included standard scaling and hyperparameter tuning.

**Evaluation Metrics**
Root Mean Squared Error (RMSE)

Mean Absolute Error (MAE)

R-squared (R²)

Cross-validated R² scores

**Results**
After evaluating all models, the XGBoost Regressor demonstrated superior performance:

RMSE: 157.49
MAE: 65.86
R²: 0.076
Cross-validated R²: 0.057 (±0.010)

Feature Importance
The top 10 features influencing equipment energy consumption, as identified by the XGBoost model, include:
'hour','lighting_energy','visibility_index','zone3_temperature', 'zone7_temperature', 'zone2_humidity', 'zone1_humidity', 'outdoor_humidity', 'zone4_humidity','zone8_temperature'
 

**Key Insights and Recommendations**
Top Influencing Features: The most significant predictors of energy consumption include 'hour','lighting_energy'and 'visibility_index'

Temporal Patterns: Energy consumption varies by hour, indicating potential for optimization during off-peak times.

Environmental Factors: Features such as 'zone3_temperature' and 'zone7_temperature',suggest that environmental conditions significantly impact energy usage.

Predictive Maintenance: Implementing predictive maintenance strategies could reduce unexpected energy consumption spikes.
