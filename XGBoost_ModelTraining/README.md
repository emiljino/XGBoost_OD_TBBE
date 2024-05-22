# XGBoost_ModelTraining

For XGBoost Model training to integrate with BBE (Bristol Betting Exchange)

## The code in this folder is used to train and test the iterative XGBoost models using data collected from the Bristol Betting Exchange (BBE) platform. The data is collected using the setup in the dissertation.

The main purpose of this code is for Pre-processing data, training iterative xgboost models and evaluating the performance using hypothesis testing of the XGBoost agents against each other and base agents from the data collected from BBE

Main code:

1. XGB1Training.ipynb
   XGB2Training.ipynb
   XGB3Training.ipynb
   XGB4Training.ipynb

   The preprocessing and iterative training of XGBoost agents, each one is trained on data generated from its predecessor and base agents.

   Details are in the 'Markdown' and commented section of the code.

2. XGBRepTraining.ipynb

   The preprocessing and iterative training of the replicated agent, trained on data generated from BBE and in the same process as [Terawongs] original model.

3. StatTestXGB1.ipynb
   StatTestXGB2.ipynb
   StatTestXGB3.ipynb
   StatTestXGB4.ipynb
   StatTestXGBRepVsOGvs1.ipynb

   These files test each XGB agent to validate the performance of the agents against each other and the base agents from BBE.
   The "StatTestXGBRepVsOGvs1.ipynb" is to test the replicated agent against the original agent and improved XGB1 agent.

4. Others

   The data folder is intended to contain the merged form of the results generated from BBE that will be used for training and testing the XGBoost agents.

## This repositry doesn't contain training and testing data due to the large file size. The data can be collected from running sessions in TBBE using the setup in the dissertation.
