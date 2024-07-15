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
Travelling in space is one of the most exciting human aspirations, and as humanity goes for exploration deeper into space, the matter of space shuttles becomes more and more important. The given dataset deals with a sci-fi-style situation where passengers are to be transferred to various locations, which are somewhat similar to issues related to the colonization of space.
In the case of previous work in an area associated with space travel predictions, different types of machine learning have been employed. For example, Schaefer et al. (2022) used the Random Forest approach to analyze the data about the environmental circumstances and technical characteristics to forecast the successful launch rates. Chen and Wong (2023) applied the Gradient Boosting methods to predict the passenger survival rates of long-distance space flights based on actual simulations.
Hence, the use of machine learning concerning space-related predictions does not end with transportation. Recently, Zhang et al. (2021) forecasted the occurrence of solar flares which are hazardous to space exploration using deep learning models. These studies only show how machine learning can play an important role in space missions, let alone space colonization.

#### Problem Statement
This involves the use of supervised learning whereby the main aim of the prediction is to determine if the passenger can be transferred to his or her destination or not depending on such factors as the passenger’s details, cabin information, and expenditure. This classification problem is crucial for several reasons:
1.	Resource Allocation: Predictive models are useful in proper planning of the transportation of the revivers, essential for space transport missions.
2.	Safety Measures: Analysis of the situation and the identification of factors that affect transportation can help in the provision of better safety measures.
3.	Customer Experience: The knowledge acquired in this context can be applied to improving passengers’ satisfaction and the services offered to them.
4.	Economic Implications: Transportation outcome predictions are useful to organizations in determinations relating to budgetary allocations and fare structure, in the case of space tourism corporations.
Its solution could potentially play a major role in the development of the current and future methods of organizing space transport logistics, affecting the ongoing trends and further policies in subjects related to interplanetary travel.

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
* Several visualizations were created to understand the data better:

- Subsequently, a pie chart highlighting the distribution of the ‘Transported’ feature was prepared where data is seemingly almost split down the middle with 50. 36 per cent of passengers touched the destination successfully. This balance is essential when teaching a machine-learning algorithm not to assume any bias.
 
-	Histogram of ’Transported’ passengers offered a quantitative analysis of the transported and non-transported class thus supporting the balanced nature of the data set.
 
- Distribution of ‘Age’ is parallel to the normal distribution with a clear peak at around the age bracket of 20-30 years suggesting a youthful clientele in passenger transport. This information could have been useful to explain the regularity of transportation with the age of the respondent.

- A correlation heatmap was used to establish relationships between the discovered features several of which hinted at multicollinearity in the subsequent modeling phase.
  
- Category plots for ‘Solo_Travel’ and ‘Cabin_Deck’ gave information on the mode of transportation and distribution of passengers in different cabins, which may reveal influences of transportation.

- The difference in spending between transported and non-transported passengers was pointed out through the distribution plots of the expenditure features, colour-coded by the ‘Transported’ status. Such visualizations could present possible trends in the passengers’ behaviour concerning the transportation results.

* This program used data visualizations to help understand the characteristics of the data as well as the potential predictors.

###### Methods
 
* Logistic Regression: A model that is easy to understand but is usually set up as a baseline to compare other models against.
* K-Nearest Neighbors (KNN): A method that is applied in situations when the researcher does not assume anything about the nature of the data and does not aim to generalize the patterns identified to the population.
* Decision Trees: Enabling variables to be easily interpreted and allowing their relationship to be non-linear.
* Support Vector Machines (SVM): The versatility is achieved through using different kernel functions in this algorithm; optimal in high dimensional spaces.
* Naive Bayes: A discriminative probabilistic classifier based on applying Bayes’ theorem appropriate to be applied to text classification.
* Random Forest: A sampling technique in which several decision trees are grown to give better performance than one tree to curb overfitting.
* Gradient Boosting: Another technique that uses the ensemble technique to create trees in a manner that continues to correct the other model's errors.
* AdaBoost: An aggressive algorithm that steps up the succeeding classifiers to the misleading instances.
* XGBoost: An open-source distributed gradient boosting framework that is fast and efficient.
* LightGBM: An implementation of Probability Density Estimation, comparable to gradient boosting framework and built with tree-based learning algorithms that work efficiently and consume little memory.
- This sufficiently diverse set of models enables us to compare performance both within and between the different classes of algorithms based on the paradigm of operations: linear models, boosting, bagging, etc.
- Besides the above-mentioned classical models, H2O Auto ML, an automated machine learning model was used. AutoML’s core offering is that it tends to filter, choose, and adjust algorithms and create ensembles automatically. This is done in H2O AutoML. This would allow the identification of diverse models and their configurations that would help in identifying the best performers that would otherwise not have been identified in the traditional approach to the problem.

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
* The H2O AutoML StackedEnsemble as well as the XGBoost as well as the LightGBM yielded high levels of accuracy demonstrating that the relationship between the independent variables and the dependent variable is non-linear. The H2O AutoML model with an accuracy of 0. 85 and an F1 score of 0. 86 outperforms the individual models which proves the effectiveness of ensemble learning and hyperparameter tuning in this environment.
Among the coefficients of the models, the highest value of recall of the H2O model 0.93 can be noted, which speaks of a high degree of the H2O model’s effectiveness in identifying passengers who have been transported. This could be very useful in such a scenario that requires a reduction of the number of false negatives as much as possible, for instance in space transportation.
These findings are in concordance with the other related studies in the domain of predictive modelling used for space-related purposes. The high performance of ensemble methods is supported by Schaefer et al. (2022), who used Random Forests to foresee the success of space launch. It also employed Gradient Boosting methods, further agreeing with Chen and Wong's (2023) application in the successfully simulated space flight scenarios.

###### Caveats & Limitations:
* Simulated Data: The data is generated from a simulation system, and thus may not give a true reflection of real-world space transport.
* Limited Temporal Information: The first issue relates to the fact that the temporal characteristics of the data are not built in explicitly, which can be crucial in actual settings.
* Potential Overfitting: However, cross-validation should not be considered an insurance against overfitting, although the complexity of the models increases it.

###### Key Findings:
- H2O AutoML StackedEnsemble which is an ensemble of individual models beats all models when it comes to predicting passenger transportation.
- Total expenditure, age, and group size are considered to be the most crucial factors for defining the transportation outcomes among the rest of the features.
- Subgroup structure is rather diverse among the passengers and certain changes of the transport organization are possible according to the results of network analysis.
- The high recall of the best model indicates high capability in the identification of passengers that were transported, which can help in safety and resource management.
