# Benchmarking Auto ML Frameworks

Many techniques are present to handle the problem of combining designing ML systems and accelerate the data science process, automatic learning platforms are one of them. They are created to extract value from data as quickly and with as little effort as possible. 

These frameworks automate most of the tasks associated with constructing and implementing a machine learning pipeline that would normally be engineered by specialized teams, so that users can spend more time on more complex processes, like feature engineering and hyper-param optimization.

However, there is no objective method to compare these techniques. So, authors present a benchmark of current open source automatic machine learning solutions using open source datasets. In experiments, authors test auto-sklearn, TPOT, auto_ml, and H2Os against a compiled set of regression and classification datasets.

Here is the table with these frameworks' merits and demerits(excerpted from the original)

|      |merits|demerits|
|------|------|--------|
|**auto_ml**<br>V2.7.0|1. it autom ates the feature engineering process through tf-idf processing (natural language), date processing, categorical encoding and numeric feature scaling;<br>2. it performs feature reduction when more than 100,000 columns exist using reduction methods such as PCA;<br>3. it automates the model construction, tuning, selection, and ensembling process;<br>4. it utilizes highly optimized libraries such as Scikit-Learn, XGBoost, TensorFlow, Keras, and LightGBM for its algorithm implementations.|1. it has poor extensibility;<br>2. it tends to performs poorly with multi-class classification problems;<br>3. it does not support a time limiting feature;
|**auto_sklearn**<br>V0.4.0|1. try all the relevant data manipulators and estimators on a dataset but can be manually restricted;<br>2. have multi-threading support;<br>3. One of the greatest advantages is its easy integration into the existing sklearn ecosystem of tools which provides an avenue for extension;<br>4. use the optimization framework SMAC3 which implements bayesian search along with a racing mechanism to quickly assess model performance. |1. lack the ability to process natural language inputs;<br>2. lack the ability to automatically discern between cat-egorical and numerical inputs;<br>3. do not handle string inputs and requires manual integer encoding to accept categorical strings;|
|**TPOT**<br>V0.9|1. source its data manipulators and estimators from sklearn and its search space can be limited through a configuration file;<br>2. Time restrictions are applied by changing the maximum execution time or the population size;<br>3. The optimization process also supports pausing and resuming;<br>4. The most important feature of this framework is the ability to export a model to code to be further modified by hand;|1. cannot automatically process natural language inputs;<br>2. cannot processes categorical strings which must be integer encoded before passing in data;|
|**H2O**<br>V3.20.0.2|1. support imputation, one-hot encoding, and stan-dardization for feature engineering;<br>2. support generalized linear models, basic deep learning models, gradient boosting machines, and dense random forests for its machine learn-ing models;<br>3. support two methods of hyperparameter optimization; cartesian grid search and random grid search;<br>4. the end result is an ensemble model that can be saved and reloaded into the h2o framework to be used in production systems. |1. The primary drawback of h2o is its massive resource usage. During testing, this framework suffered multiple failures during long-running processes due to inadequate garbage collection.|

The result is that auto-sklearn performs the best on the classifi-cation datasets and TPOT performs the best on regression datasets.


## References
1. Adithya Balaji, Alexander Allen: Benchmarking Automatic Machine Learning Frameworks. In 2018.