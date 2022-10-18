# Experimenting-Stock-Trading-using-Reinforcement-Learning
Stock market is the venue where stocks of various companies are exchanged between buyers and sellers.Advancements in the field of reinforcement learning inspire to model trading of stocks as a Markov Decision Process.

## Overview

In our project, we build a trading environment and train reinforcement agents using Actor-Critic model. Here, we train the model using two sets of inputs, “stock price data” and “stock price data along with its sentiment data”. By experimenting with these two sets of input on the same architecture, we aim to verify if adding sentiment data really improve the performance of the agent

## Problem Statement

The aim of this project is to verify if adding sentiment data really improves the performance of the agent and help to obtain the maximum portfolio value. This can be considered as a maximization problem
we model trading of stocks as a Markov Decision Process (MDP) and our MDP contains the following:
1. State[s] - Each state is represented as a vector that holds the information regarding the availability of cash, shares of holding stocks, portfolio value, stock value for current time step, sentiment data and so on.
2. Action[a] - The action space includes buying, selling or holding shares that are owned, with respect to a particular stock.
3. Reward[r] - Some value that is obtained when certain action is performed.
4. Policy[pi] - Policy can be defined as a trading strategy at every state in our MDP. It is nothing but the probability distribution of an action at a given state.
5. Action-value function [QPi(s,a)]- This is an expected reward that is obtained for taking certain action from a state using the policy.

## Methodology

We use Advantage Actor Critic (A2C) algorithm to imple- ment our trading agent because Actor (policy) network states which action (buy, hold, sell) should be taken for state parameters while critic (value function) network gives a feedback on how good the action is and adjust the reward. Thus, it reduces the high variance of the policy network and makes the model more robust.

## Experimental Setting

The dataset contains the daily stock details for Apple (AAPL) and Microsoft (MSFT) from 2014 to 2017
Each stock data contains following parameters:
```
Date
Open Price (stock price at start of the day)
Close Price (stock price at end of the day)
High price (highest price of stock on that day)
Low Price (lowest price of stock on that day)
sentiment data such as (positive score, negative score, neutral score and compound score)
```
## Evaluation Criteria

For evaluation, we will compare the model with two sets of input - stock prices data, stock price with sentiment data
With different inputs, we train the model under the same architecture and hyper-parameters. Then, we perform number of runs to calculate average profit, average reward obtained and number of successful runs.
In addition, we evaluate the model by three different sentiment score calculations which are defined as below: 
```
1. Minimum Sentiment Score = (SentimentScore)^2
2. Normal Sentiment Score = SentimentScore
3. High Sentiment Score = math.sqrt(SentimentScore)
```

## References

1. T. Grek, “Stock trading using reinforcement learning. [online] available: https://towardsdatascience.com/a- blundering-guide-to-making-a-deep-actor-critic-bot-for- stock-trading-c3591f7e29c2,” Accessed: 01-May-2022
2. X.-Y. Liu, H. Yang, Q. Chen, R. Zhang, L. Yang, B. Xiao, and C. D. Wang, “Finrl: A deep reinforcement learning library for automated stock trading in quantitative finance,” 2020
3. Ankthon, “Stock trading using reinforcement learning. [online] available: https://www.geeksforgeeks.org/python- sentiment-analysis-using-vader/,” Accessed: 01-May-2022
4. O. Gold, “Deep actor-critic experiment for stock trading amid sentiment and buzz. [online] available: https://www.omergold.com/stocktrading.pdf,” Accessed: 01-May-2022
5. K. Suhail, S. Sankar, A. Kumar, T. Nestor, N. Soliman, A. Algarni, W. El-Shafai, and F. Abd El-Samie, “Stock mar- ket trading based on market sentiments and reinforcement learning,” Computers, Materials and Continua, vol. 70, p. 935–950, 09 2021

