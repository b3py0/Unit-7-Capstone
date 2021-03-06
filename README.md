# Capstone projects
This repo contains 3 workbooks. 

1) A small NLP project from midway through the DS course at Thinkful on AirBnB data to predict neighbourhood. This is an example of asking the _wrong question_ from a great dataset: A great, if unintended, learning experience.  
2) Data cleaning and analysis of microfossil (biostratigraphic) data from the Equinor-operated Volve oil field hosted at https://www.equinor.com/en/news/14jun2018-disclosing-volve-data.html that is now open-access. Under a release programme, Equinor allowed access to the retired Volve oilfield that was in operation off south Norway from 2008-2016. 
3) The third workbook - <b>Oversampling effects on data</b> - visualizes the effects of oversampling on sparse data using PCoA. While SMOTE clearly interpolates artificial new samples, RandomOversampling duplicates samples in the smallest time bin. Both approaches are effective for training the models presented here. 

The .pdf file, <b>Thinkful_volve_presenation</b> is a presentation of the final Capstone presented to Thinkful on 14th January 2019.

The focus of the main study is the fossil data (fossil pollen, spores, dinoflagellate cysts, and other organic-walled fossil) from 13 wells with the intention of assessing whether the fossil data could be trained for machine learning to classify age of samples. The main workbook - <b> volve_final_capstone</b> - contains text and code to show data cleaning, feature engineering (some of which are not used in this report but will be in further analyses), and modelling. Since no open-access studies of these types of count data are available to study, the approach taken is one of exploring different models and their ability to classify age firstly for large time domains (ages) e.g. Middle Jurassic, Late Cretaceous etc., and then to train models that can classify smaller time bins at the stage level (e.g. Bajocian, Kimmeridgian etc.). The dataset contains classes exhibiting significant class imbalance. 

Data were presented for modelling by 
* Multinomial Naive Bayes, 
* Logistic Regression, 
* Random Forest, 
* K-Nearest Neighbour,
* Gradient Boosting Classifier, and 
* Support Vector Machine that performed excellently for large time bins.
Oversampling by SMOTE and RandomOversampling improved model performance. 

For classifying stages, an ensemble approach using the VotingClassifier (hard voting) was deployed of:
* SVM (poly kernel), 
* Logistic Regression, 
* Random Forest and 
* Gradient Boosting 
The combination of these lifted performance by 4% from the best model (again the SVC). The data are too sparse and the classes too small and imbalanced for effective deployment of even a simple MLP. 


