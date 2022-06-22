# Feautre Engineering :feature-selection
Feature selection is the process of reducing the number of input variables when developing a predictive model.
It is desirable to reduce the number of input variables to both reduce the computational cost of modeling and, in some cases, to improve the performance of the model.

 ![image](https://user-images.githubusercontent.com/83010684/174958150-f783bcf4-f824-4545-8307-4a2adc68a05a.png)
 
 
 
## Feature Selection Techniques:

There are mainly two types of Feature Selection techniques, which are:

### Supervised Feature Selection technique:

Supervised Feature selection techniques consider the target variable and can be used for the labelled dataset.

### Unsupervised Feature Selection technique:

Unsupervised Feature selection techniques ignore the target variable and can be used for the unlabelled dataset.

 
 ![image](https://user-images.githubusercontent.com/83010684/174959477-89424288-cc39-4a3f-8448-25aeafdca326.png)


1. Wrapper Methods

In wrapper methodology, selection of features is done by considering it as a search problem, in which different combinations are made, evaluated, and compared with other combinations. It trains the algorithm by using the subset of features iteratively.

 ![image](https://user-images.githubusercontent.com/83010684/174968255-ac0bd0b3-4c76-47b8-8eec-1e25f50747d7.png) 

Some techniques of wrapper methods are:

*Forward selection - Forward selection is an iterative process, which begins with an empty set of features. After each iteration, it keeps adding on a feature and evaluates the performance to check whether it is improving the performance or not. The process continues until the addition of a new variable/feature does not improve the performance of the model.

  *Backward elimination - Backward elimination is also an iterative approach, but it is the opposite of forward selection. This technique begins the process by considering all the features and removes the least significant feature. This elimination process continues until removing the features does not improve the performance of the model.
  
  *Exhaustive Feature Selection- Exhaustive feature selection is one of the best feature selection methods, which evaluates each feature set as brute-force. It means this method tries & make each possible combination of features and return the best performing feature set.
  
  *Recursive Feature Elimination-
  Recursive feature elimination is a recursive greedy optimization approach, where features are selected by recursively taking a smaller and smaller subset of features. Now, an estimator is trained with each set of features, and the importance of each feature is determined using coef_attribute or through a feature_importances_attribute.


2. Filter Methods

In Filter Method, features are selected on the basis of statistics measures. This method does not depend on the learning algorithm and chooses the features as a pre-processing step.
The filter method filters out the irrelevant feature and redundant columns from the model by using different metrics through ranking.
The advantage of using filter methods is that it needs low computational time and does not overfit the data.

 ![image](https://user-images.githubusercontent.com/83010684/174968176-9e25df68-cf66-41a4-9999-14492a8a1cac.png)


Some common techniques of Filter methods are as follows:
              Information Gain
              Chi-square Test
              Fisher's Score
              Missing Value Ratio
              
              
Information Gain: Information gain determines the reduction in entropy while transforming the dataset. It can be used as a feature selection technique by calculating the information gain of each variable with respect to the target variable.

Chi-square Test: Chi-square test is a technique to determine the relationship between the categorical variables. The chi-square value is calculated between each feature and the target variable, and the desired number of features with the best chi-square value is selected.

Fisher's Score:
Fisher's score is one of the popular supervised technique of features selection. It returns the rank of the variable on the fisher's criteria in descending order. Then we can select the variables with a large fisher's score.

Missing Value Ratio:

The value of the missing value ratio can be used for evaluating the feature set against the threshold value. The formula for obtaining the missing value ratio is the number of missing values in each column divided by the total number of observations. The variable is having more than the threshold value can be dropped.


3. Embedded Methods

Embedded methods combined the advantages of both filter and wrapper methods by considering the interaction of features along with low computational cost. These are fast processing methods similar to the filter method but more accurate than the filter method.

 ![image](https://user-images.githubusercontent.com/83010684/174968360-1799f955-2256-441e-adea-1f7a60d7ecda.png)


These methods are also iterative, which evaluates each iteration, and optimally finds the most important features that contribute the most to training in a particular iteration. Some techniques of embedded methods are:

Regularization- Regularization adds a penalty term to different parameters of the machine learning model for avoiding overfitting in the model. This penalty term is added to the coefficients; hence it shrinks some coefficients to zero. Those features with zero coefficients can be removed from the dataset. The types of regularization techniques are L1 Regularization (Lasso Regularization) or Elastic Nets (L1 and L2 regularization).
Random Forest Importance - Different tree-based methods of feature selection help us with feature importance to provide a way of selecting features. Here, feature importance specifies which feature has more importance in model building or has a great impact on the target variable. Random Forest is such a tree-based method, which is a type of bagging algorithm that aggregates a different number of decision trees. It automatically ranks the nodes by their performance or decrease in the impurity (Gini impurity) over all the trees. Nodes are arranged as per the impurity values, and thus it allows to pruning of trees below a specific node. The remaining nodes create a subset of the most important features.


### How to choose a Feature Selection Method?
For machine learning engineers, it is very important to understand that which feature selection method will work properly for their model. The more we know the datatypes of variables, the easier it is to choose the appropriate statistical measure for feature selection.

 ![image](https://user-images.githubusercontent.com/83010684/174961657-d9b62dde-d77a-4ea0-9a71-cd3407055573.png)


To know this, we need to first identify the type of input and output variables. In machine learning, variables are of mainly two types:

Numerical Variables: Variable with continuous values such as integer, float
Categorical Variables: Variables with categorical values such as Boolean, ordinal, nominals.
Below are some univariate statistical measures, which can be used for filter-based feature selection:

1. Numerical Input, Numerical Output:
Numerical Input variables are used for predictive regression modelling. The common method to be used for such a case is the Correlation coefficient.

Pearson's correlation coefficient (For linear Correlation).
Spearman's rank coefficient (for non-linear correlation).
2. Numerical Input, Categorical Output:

Numerical Input with categorical output is the case for classification predictive modelling problems. In this case, also, correlation-based techniques should be used, but with categorical output.

ANOVA correlation coefficient (linear).
Kendall's rank coefficient (nonlinear).
3. Categorical Input, Numerical Output:

This is the case of regression predictive modelling with categorical input. It is a different example of a regression problem. We can use the same measures as discussed in the above case but in reverse order.

4. Categorical Input, Categorical Output:

This is a case of classification predictive modelling with categorical Input variables.
The commonly used technique for such a case is Chi-Squared Test. We can also use Information gain in this case.

We can summarise the above cases with appropriate measures in the below table:

  ![2022-06-22 (2)](https://user-images.githubusercontent.com/83010684/174962527-476188ed-cb26-4b3a-b98e-a23a62f5003f.png)
  
  


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
https://www.javatpoint.com/feature-selection-techniques-in-machine-learning
https://towardsdatascience.com/feature-selection-techniques-in-machine-learning-with-python-f24e7da3f36e

## information Gain
#### sklearn.feature_selection.mutual_info_classif¶

Estimate mutual information for a discrete target variable.

Mutual information (MI)  between two random variables is a non-negative value, which measures the dependency between the variables. It is equal to zero if and only if two random variables are independent, and higher values mean higher dependency.

The function relies on nonparametric methods based on entropy estimation from k-nearest neighbors distances as described in [2] and [3]. Both methods are based on the idea originally proposed in [4].
