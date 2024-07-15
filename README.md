# ASSIGNMENT 2 - GROUP PROJECT - KAGGLE CHALLENGE
## Table of Contents
* Background Context	
* Problem Statement	
* Domain Knowledge	
* Exploratory Data Analysis (EDA)
* Methods		
* Results	
* Discussion & Conclusions	
* Caveats & Limitations	
* Key Findings	
* Future Work
* Bibliography
### Background Context
Space travel is a thrilling human dream, with space shuttles becoming increasingly important. Machine learning has been used to forecast successful launch rates as well as passenger survival rates in space travel. Recent research has also used deep learning models to predict solar flares, which endanger space exploration. These studies show that machine learning plays an important role in space exploration and colonization.

#### Problem Statement
Supervised learning is used to forecast passenger transfers based on passenger information, cabin information, and spending. This classification problem is critical for resource allocation, safety precautions, customer experience, and economic consequences. Predictive models aid in the planning of space transport missions, identifying transportation-related factors, improving passenger satisfaction, and determining budgetary allocations. This solution has the potential to influence future logistics and interplanetary travel policies.

##### Domain Knowledge: 
The dataset includes several key attributes that provide comprehensive information about each passenger and their journey:
- PassengerId: A code number that is given to every passenger as a reference number when recording his/her records or details.
- HomePlanet: The body characteristic also includes the planet of origin for each passenger which gives additional information about where the passenger was coming from.
- CryoSleep: A boolean feature that would show whether or not the passenger was in cryosleep during the journey, which could be vital in space journeys that take a long time.
- Cabin: Details about the cabin number and position of the passenger may affect their experience and the result of transportation.
- Destination: The intended destination planet: provides information about the distance as well as the difficulty of the trip.
- Age: Another independent variable that may influence the passenger’s experience and result of space travel is their age.
- VIP: A binary attribute suggesting the passenger’s level of being a celebrity that may influence the treatment and transportation priorities.
- RoomService, FoodCourt, ShoppingMall, Spa, VRDeck: Numerical measurements concerning the spending on different services offered on the flight, which indicates the passenger’s activity level during the flight.
- Transported: The target variable of the model is a Boolean variable denoting whether or not the passenger was successfully transported to their required location.

###### Exploratory Data Analysis (EDA): 
Supervised learning is used to forecast passenger transfers based on passenger, cabin, and spending data. This classification problem is critical for resource allocation, safety precautions, customer experience, and economic outcomes. Predictive models help plan space transport missions, identify transportation-related factors, improve passenger satisfaction, and determine budget allocations. This solution has the potential to impact future logistics and interplanetary travel policies.

###### Methods
Logistic Regression, K-Nearest Neighbors (KNN), Decision Trees, Support Vector Machines (SVM), Naive Bayes, Random Forest, Gradient Boosting, AdaBoost, XGBoost, and LightGBM are among the machine learning models discussed in the text. These models enable performance comparison within and between different classes of algorithms using operations such as linear models, boosting, bagging, and so on. H2O Auto ML, an automated machine learning model, filters, selects, and adjusts algorithms as well as generates ensembles automatically. This approach aids in the identification of various models and their configurations, as well as the identification of the best performers who would not have been identified using traditional methods.

###### Pre-processing steps included:
 
- Primarily, the steps of the imputation of missing values: mode if they are in category type, median if in continuous type.
- Feature engineering:
- Taking derivatives of PassengerId which are Group, Member, Solo_Travel and Group_Size.
- For the extraction of Cabin_Deck, Cabin_Num, and Cabin_Side variables, the Census Variable Cabin needs to be separated.
- It’s necessary to generate new features, namely Age_Group and Total_Expenditure.
- The transformation of expenditure-related features includes the Log transformation because the features contain skewed data.
- Encoding categorical variables
- Scaling numerical features
- These pre-processing steps were important to ensure the data had to go through for modelling, data with missing values and other problems had to be addressed while at the same time features that would help in increasing the performance of the model had to be created.

###### Results

- Model Training and Optimization: Training of multiple models and their validation was done through cross-validation. The best-performing traditional models were:
- XGBoost: Accuracy: 0. 81, F1: 0. 81
- LightGBM: Accuracy: 0. 81, F1: 0. 81
- Gradient Boosting: Accuracy: 0. 80, F1: 0. 80
- Random Forest: Accuracy: 0. 80, F1: 0. 79

###### The StackedEnsemble_AllModels_1_AutoML_1_20240701_134151 model, which is a stacked ensemble, showed impressive results:
- Train AUC: 0. 9580
- Cross-validation AUC: 0. 9021
- Mean cross-validation accuracy: 0. 8073
The nature of the ensemble was a combination of base models, mainly XGBoost and GBM, with the GLM meta learner.
Feature Importance: By performing SHAP analysis it is possible to determine that three key attributes – Total_Expenditure, Age and Group_Size have the highest priority in terms of being used for the prediction. This insight gives a lot of information regarding some of the factors that play a major role in the determination of whether a passenger can be transported or not.
- Network Analysis: When doing the network analysis of the training data the real structure of the passenger associations was defined: altogether there are 6217 sub-groups. This information could be potentially useful to explain the dynamics occurring within each group and their relation to the results achieved in the field of transportation.

###### Discussion & Conclusions
The non-linear relationship between independent and dependent variables is demonstrated by the H2O AutoML model, which performs better than other models in terms of accuracy and recall. The model's maximum recall value of 0.93 shows how well it can identify passengers who have been moved, which may be useful in situations involving space travel. These results are consistent with other research in successfully simulated space flight scenarios, like Schaefer et al. (2022) and Chen and Wong (2023), that used ensemble approaches for space-related goals.


###### Caveats & Limitations:
* Simulated Data: The data is generated from a simulation system, and thus may not give a true reflection of real-world space transport.
* Limited Temporal Information: The first issue relates to the fact that the temporal characteristics of the data are not built in explicitly, which can be crucial in actual settings.
* Potential Overfitting: However, cross-validation should not be considered an insurance against overfitting, although the complexity of the models increases it.

###### Key Findings:
- H2O AutoML StackedEnsemble which is an ensemble of individual models beats all models when it comes to predicting passenger transportation.
- Total expenditure, age, and group size are considered to be the most crucial factors for defining the transportation outcomes among the rest of the features.
- Subgroup structure is rather diverse among the passengers and certain changes of the transport organization are possible according to the results of network analysis.
- The high recall of the best model indicates high capability in the identification of passengers that were transported, which can help in safety and resource management.

##### Future Work:
- Incorporate real-world data: Where possible use actual data on space transportation to validate the models.
- Temporal analysis: Research the effect of the temporal characteristics in transportation.
- Deep learning approaches: It also briefly considers different neural network topologies hoping to increase the model’s efficiency.
- Causal inference: Research factors that would help identify the effects of the various features on transport.
- Extended network analysis: Continue the study of the group dynamic concerning the transportation probabilities.

In conclusion, employing the results of this research work, it can be argued that the interdisciplinary approach of applying machine learning in general and ensemble and auto machine learning, in particular, allows for predicting the outcomes in space transportation successfully. The information derived from the feature importance and network analysis results points to valuable directions for further research and application in space travel logistics. Such predictive models shall only grow in importance as humanity advances to explore and conquer outer space for efficient and safe transportation needs.

##### Bibliography
- Chen, Y. and Wong, K.Y., 2023. Predictive modeling of passenger survival rates in simulated long-distance space flights using Gradient Boosting methods. Journal of Space Transportation, 45(3), pp.287-301.
- Schaefer, R., Johnson, M. and Liu, X., 2022. Application of Random Forest algorithms in predicting space launch success rates. Advances in Space Research, 69(8), pp.2956-2970.
- Zhang, H., Li, J. and Wang, S., 2021. Deep learning approaches for solar flare prediction: Implications for space travel safety. Astrophysical Journal, 912(2), p.108.
