### Customer Payment (Revenue) Prediction
#### Author: Qingchuan Lyu
__Goal__: we want to learn more about the users who started the new new service during November 2020.  

__Problems__:

Using only the first 7 days of payments and events, what is our best prediction for day 60 revenue.  We can model per user and/or aggregates grouped by platform, channel and geo.

__Strategy Highlights__:
* To predict day 60 revenue with the first 7 days of payments and events, I computed the total revenue on day 60 for each combination of platform, channel and geo. According to total revenue on day 60 and the sample size of each combination, I divided users into 4 groups ('combo_category' = 0, 1, 2, 3) and found the optimal model for each group. See Section Grouping Users.
* Building a PCA pipeline most often significantly reduced RMSE. The only exception was the last group (combo_category = 3), where a simple OLS model outperformed all the other regularized linear models and tree models on the out-of-sample data. See Section Modeling.
