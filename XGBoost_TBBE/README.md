# XGBoost_TBBE

### This is code for A XGBoost-Agent Based model in In-Play Betting on a Sports Betting Exchange dissertation

This project is an extension of the Multi-threaded BBE (Bristol Betting Exchange) integrated with Opinion Dynamics Platform, originally developed by [Guzelyte](https://github.com/Guzelyte/TBBE_OD) and further extended by [Terawong](https://github.com/Terawong).

In this version, I have modified the agent called `XGBoostBettingAgent`, existing in the `betting_agents.py` file located in the Application folder. This agent now has the capability to load multiple different models trained in [XGBoost_ModelTraining].

The main objective of this project is to train iterative XGBoost agents. This is achieved by leveraging the existing codebase and adding functionality to load multiple XGBoost agents.
Basic steps for running the BBE (Bristol Betting Exchange):

1. In config.py -> Initialise the agents list. Below is the example of the latest agent list:
   agents = [('Agent_Opinionated_Random', 10), ('Agent_Opinionated_Leader_Wins', 10),
   ('Agent_Opinionated_Underdog', 10),('Agent_Opinionated_Back_Favourite',10),
   ('Agent_Opinionated_Linex', 10), ('Agent_Opinionated_Priviledged', 5),
   ("XGBoostBettingAgent_xgb1", 5), ("XGBoostBettingAgent_xgb2", 5),("XGBoostBettingAgent_xgb3", 5),
   ("XGBoostBettingAgent_xgb4", 5)]

   This is the configuration of the agents in the simulation. The first element in the tuple is the agent name, and the second element is the number of agents in the simulation. The XGBoost agents are named as XGBoostBettingAgent_xgb(n), where n is the iteration of the XGBoost agent. For training the next iteration of the XGBoost agent, the previous iterations must be used in the configuration.

2. In systems_constant.py defines parameters/settings of the simulations. Example of parameters systems_constant.py:

   -> General
   NUM_OF_SIMS = 1
   NUM_OF_COMPETITORS = 5
   NUM_OF_EXCHANGES = 1
   PRE_RACE_BETTING_PERIOD_LENGTH = 0
   IN_PLAY_CUT_OFF_PERIOD = 0
   SESSION_SPEED_MULTIPLIER = 1

   -> Exchange Attributes
   MIN_ODDS = 1.1
   MAX_ODDS = 20.00

   -> Event Attributes
   RACE_LENGTH = 2000
   MIN_RACE_LENGTH = 400
   MAX_RACE_LENGTH = 4000

3. "RUN" the session -> In the terminal type "python TBBE.py" to run the session. The session will start and finish after the number of simulations specified in systems_constant.py is completed. The results will be saved in the data folder.

4. Many result files will be generated. Please look at session_stats.py file for how each file is generated, the path to the data folder can be specified to save to a different location if needed due to large file size.

5. For each simulation specified in `NUM_OF_SIMS`, several result files will be generated. These include `getXGBoostTrainingData.csv`, `final_balances.csv`, `prices_histories.csv`, `prices_spreads.csv`, `transactions.csv`, and a `race_event_core.csv` file. Please refer to the `session_stats.py` file for details on each file. Due to the large size of these files, the path of the data folder can be specifed to a different location.

### This repositry doesn't contain data files due to the large file size. The training and testing data can be collected from running sessions in BBE using the setup in the dissertation.
