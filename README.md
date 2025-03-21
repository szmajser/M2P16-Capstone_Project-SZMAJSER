# M2P16-Capstone_Project-SZMAJSER

## Introduction

In this project, I use a dataset from kaggle related to EV Battery Charging

Source: https://www.kaggle.com/datasets/ziya07/ev-battery-charging-data?select=ev_battery_charging_data.csv

Features:
- SOC (%): State-of-Charge of the EV battery, expressed as a percentage. This indicates the current charge level of the battery.
- Voltage (V): Voltage of the battery during charging, measured in volts (V).
- Current (A): The current (in amperes) flowing into the battery during the charging process.
- Battery Temp (°C): The temperature of the battery during charging, measured in degrees Celsius (°C).
- Ambient Temp (°C): The surrounding temperature of the environment in which the EV is being charged.
- Charging Duration (min): The duration (in minutes) of the battery charging process.
- Degradation Rate (%): A computed value representing the degradation rate of the battery, which affects its overall efficiency and charging capacity. This is - calculated based on the charging duration, SOC, and battery temperature.
- Charging Mode: A categorical feature representing the charging mode used during the process. This can be one of three values: 'Fast', 'Normal', or 'Slow'.
- Efficiency (%): Battery efficiency calculated based on the degradation rate. The higher the degradation, the lower the efficiency.
- Battery Type: The type of battery used in the EV. This feature has two possible values: 'Li-ion' (Lithium-ion) and 'LiFePO4' (Lithium Iron Phosphate).
- Charging Cycles: The number of charging cycles the battery has undergone. A charging cycle is counted when the battery goes from full charge to empty and back to full charge.
- EV Model: The model of the electric vehicle, which can be one of the following: 'Model A', 'Model B', or 'Model C'.
- Optimal Charging Duration Class: The target variable representing the classification of the optimal charging duration:
- Short (0): Charging duration is short (≤ 40 minutes).
- Medium (1): Charging duration is moderate (≤ 80 minutes).
- Long (2): Charging duration is long (> 80 minutes).

## Analysis
### Optimal Charging Duration Class Correlations
Strongest Correlation: 
- Degradation Rate (%) and Efficiency (%) - 1.00

High Correlation:
- Charging Duration (min) and Optimal Charging Duration Class - 0.92
- Degradation Rate (%), Efficiency (%), and Charging Duration (min) - 0.86

Behind 80% correlation:
- Degradation Rate (%) and Optimal Charging Duration Class - 0.81

Higher efficiency (%) is associated with a higher optimal charging duration class. This suggests that more efficient battery charging processes align with longer optimal charging durations.

Longer charging duration (min) negatively impacts the optimal charging duration class. Meaning excessive charging time is less optimal and reduces the likelihood of reaching an ideal charging duration.

Factors such as ambient temperature (°C), battery temperature (°C), and voltage (V) have a slight positive influence. This indicates that under certain conditions, these factors contribute marginally to improving the optimal charging duration.

### Model 1 - Logistic Regression Model
Logistic regression was used to identify the key features contributing to Optimal Charging Duration Class.

Classification Report for Logistic Regression:
Value 0 (Short (0): Charging duration is short (≤ 40 minutes))

Precision = 100% it was correct.
Recall = 95% of the short charging duration were correctly identified.
Value 1 (Medium (1): Charging duration is moderate (≤ 80 minutes))

Precision = 97% it was correct.
Recall = 100% of the medium charging duration were correctly identified.
Value 2 (Long (2): Charging duration is long (> 80 minutes))

Precision = 100% it was correct.
Recall = 100% of the long charging duration were correctly identified.
Accuracy 99%

### Model 2 - SVM (Support Vector Machines) + GridSearchCV
Precision - How many of the predicted positive cases were actually positive.

Recall - How many of the actual positive cases were correctly identified.

Value 0 (Short (0): Charging duration is short (≤ 40 minutes))

Precision = 100% it was correct.
Recall = 100% of the short charging duration were correctly identified.
Value 1 (Medium (1): Charging duration is moderate (≤ 80 minutes))

Precision = 99% it was correct.
Recall = 100% of the medium charging duration we correctly identified.
Value 2 (Long (2): Charging duration is long (> 80 minutes))

Precision = 100% it was correct.
Recall = 99% of the long charging duration were correctly identified.
Accuracy 99%

### Conclusion
Final test done with a model of 99% accuracy, it predicted fine the tested value.
