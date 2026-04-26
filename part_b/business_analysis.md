Part B: Business Case Analysis
B1. Problem Formulation
(a)

In this problem, we want to predict how many items will be sold in a store for a given month. So the target variable is the number of items sold. To make this prediction, we can use different inputs like store size, location type (urban, semi-urban, rural), type of promotion, number of customers coming to the store (footfall), competition in that area, and also time-related things like month, weekends, and festivals. Since we are predicting a number and we already have past data, this is a supervised learning problem and comes under regression.

(b)

Using total revenue is not always a good idea because revenue depends on price. For example, if there is a big discount, more items may be sold but revenue may look lower. So it can give the wrong idea about performance. Items sold is better because it directly shows how customers are responding to the promotion. It tells us which promotion is actually working. This shows an important point that the target variable should match the real goal of the business.

(c)

Using one model for all stores is not a very good idea because stores are different. A store in a city and a store in a rural area may behave very differently. A better way is to either build separate models for different types of locations or make sure the model properly understands store differences. This will give better and more accurate results.

B2. Data and EDA Strategy
(a)

The data is coming from four tables: transactions, store details, promotion details, and calendar data. These can be joined using common columns like store_id, promotion_id, and date. After joining everything, we should make the data in such a way that one row represents one store for one month. Then we can calculate total items sold in that month, total footfall, and which promotion was used. We can also include things like number of weekends and whether there was any festival in that month.

(b)

Before building the model, we should explore the data properly. First, we can check which promotion gives more sales by comparing them. Then we can look at monthly sales trends to see if there is any pattern like higher sales during festivals. We can also check how different variables are related to each other. Another useful thing is to compare sales in urban and rural areas to see differences. Lastly, we should check how the sales values are distributed to see if the data is normal or not. All this helps us understand the data better and build a better model.

(c)

If most of the data does not have promotions, the model may ignore promotions completely and focus only on normal sales. This is a problem because we want to understand promotion impact. To fix this, we can balance the data or give more importance to promotion data. We can also add a feature that shows whether a promotion was used or not.

B3. Model Evaluation and Deployment
(a)

Since this is time-based data, we should split it based on time. For example, we can use the first two to three years for training and the last few months for testing. We should not use random split because it mixes past and future data, which is not correct. To check performance, we can use MAE, RMSE, and R-squared. MAE tells us the average error, RMSE shows larger mistakes more clearly, and R-squared tells us how well the model is working overall.

(b)

If the model suggests different promotions for the same store in different months, it means the situation is changing. For example, in December there may be festivals and more shopping, so loyalty points may work better. In March, sales may be lower, so discounts may help more. We can use feature importance to see which factors are affecting the decision. Then we can explain this to the marketing team in simple language.

(c)

After training the model, we can save it using tools like joblib or pickle. Every month, new data will come in and we need to prepare it in the same way as before. Then the model will predict sales for different promotions, and we can choose the best one. This process can be automated so it runs every month. We should also keep checking how well the model is performing by comparing predictions with actual sales. If the performance becomes worse, then we should retrain the model.