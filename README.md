# Feautre Engineering :feature-selection
Feature selection is the process of reducing the number of input variables when developing a predictive model.
It is desirable to reduce the number of input variables to both reduce the computational cost of modeling and, in some cases, to improve the performance of the model.


I will share 3 Feature selection techniques that are easy to use and also gives good results.
  1. Univariate Selection
  2. Feature Importance
  3. Correlation Matrix with Heatmap
  


###### Description of variables in the above file
- battery_power: Total energy a battery can store in one time measured in mAh
- blue: Has Bluetooth or not
- clock_speed: the speed at which microprocessor executes instructions
- dual_sim: Has dual sim support or not
- fc: Front Camera megapixels
- four_g: Has 4G or not
- int_memory: Internal Memory in Gigabytes
- m_dep: Mobile Depth in cm
- mobile_wt: Weight of mobile phone
- n_cores: Number of cores of the processor
- pc: Primary Camera megapixels
- px_height
- Pixel Resolution Height
- px_width: Pixel Resolution Width
- ram: Random Access Memory in MegaBytes
- sc_h: Screen Height of mobile in cm
- sc_w: Screen Width of mobile in cm
- talk_time: the longest time that a single battery charge will last when you are
- three_g: Has 3G or not
- touch_screen: Has touch screen or not
- wifi: Has wifi or not
- price_range: This is the target variable with a value of 0(low cost), 1(medium cost), 2(high cost) and 3(very high cost).



###### 1. Univariate Selection
Statistical tests can be used to select those features that have the strongest relationship with the output variable.
The scikit-learn library provides the SelectKBest class that can be used with a suite of different statistical tests to select a specific number of features.



###### 2. Feature Importance
You can get the feature importance of each feature of your dataset by using the feature importance property of the model.
Feature importance gives you a score for each feature of your data, the higher the score more important or relevant is the feature towards your output variable.


###### 3.Correlation Matrix with Heatmap
Correlation states how the features are related to each other or the target variable.
Correlation can be positive (increase in one value of feature increases the value of the target variable) or negative (increase in one value of feature decreases the value of the target variable)

reference:
https://towardsdatascience.com/feature-selection-techniques-in-machine-learning-with-python-f24e7da3f36e

## information Gain
#### sklearn.feature_selection.mutual_info_classif¶

Estimate mutual information for a discrete target variable.

Mutual information (MI)  between two random variables is a non-negative value, which measures the dependency between the variables. It is equal to zero if and only if two random variables are independent, and higher values mean higher dependency.

The function relies on nonparametric methods based on entropy estimation from k-nearest neighbors distances as described in [2] and [3]. Both methods are based on the idea originally proposed in [4].
