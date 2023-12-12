# Sales Forecast Project Brief
## 💫 Overview
📈 ***The Sales Forecast Project is crucial for business planning and strategy. It accurately predicts future sales volumes, allowing businesses to optimize inventory, reorder, and funding allocation***.<br><br>
***📦 Optimize Inventory Management***: Accurate sales predictions help businesses plan their inventory levels more effectively.<br>
***💰 Improve Reorder Planning***: With insights into future sales volumes, businesses can streamline their production processes.<br>
***⚖️ Out-of-stock and Overstock Reduction***: Accurate sales forecasts enable businesses to avoid overproduction, resulting in reduced out-of-stock or overstock costs.<br>
***🔍 Data-Driven Decision Making***: The Sales Forecasting System empowers organizations to make informed decisions based on reliable predictions.<br>

## The system architect is as follows (as of August 2023):

***🏢 Data Warehouse:*** All data comes from UDS (Clickhouse).<br>
***📚 Feature Store:*** Contains a collection of relevant features related to sales, market trends, inventory, and products info. These features are extracted from the data warehouse and serve as input variables for the forecasting models.<br>
***🧹 Preprocessing:*** The Preprocessing module involves data cleaning, transformation, and normalization.<br>
***🛠️ Feature Engineering:*** In the Feature Engineering module, additional features are created or derived from the existing ones to enhance the predictive power of the models.<br>
***🧠 Modeling:*** The Modeling module includes the implementation of forecasting models, specifically Neural Prophet and Cat Boost models.<br>
***📈 Model Inference:*** The Model Inference module generates the final output, which is the monthly forecast for each product in each channel group for the next 12 months.<br><br>
These modules work together to provide a comprehensive sales forecasting solution, enabling businesses to make informed decisions based on accurate predictions of future sales performance.<br>

### Monthly FCST Cycle. The collaborative process between sales forecast-driven replenishment, logistics, marketing and financial decision making.

### System FCST Release Cycle.  The process for upgrading, validating, and releasing System FCST.

### Sales FCST Business-Data Science Collaboration Architecture(as of September 2023):

***Distill business directives:***
Summarized the process of extracting actionable business guidelines and instructions based on analysis and insights on the business side, mainly through meetings to complete information transmission <br>
***Data Science Analysis and Feedback:***
In this stage, the data science team reviews the business directives, analyzes feasibility, evaluates implications, and provides authoritative feedback. This includes presenting data-driven insights, metrics, risks, optimizations and recommendations to enhance or validate the business directives. <br>
***Data Handoff and Transition :***
After reviewing business directives, the data science team hands off optimized directives and key metrics back to the business side for execution. Meanwhile, important features, data preprocessing and other technical outputs are transitioned to the model building phase to enable the next stage of the data science workflow. 

# 🗓️  Milestone
#### 2019 - DSS + Sales Pattern
Starting from 2019, the sales forecasting system has been driven by DSS (Daily Selling Speed) and Sales Pattern.
DSS is a weighted average of historical sales over a certain period of time, with adjustments made for oversize orders and stockouts.
The sales pattern is a monthly-level historical observation of market trends at the product type level.
The monthly-level Sales Forecast is obtained by multiplying the product-level/channel-level DSS with the corresponding monthly-level Sales Pattern.

#### 2022 - Multilayer Perceptron (MLP) Neural Network
Starting from 2022 Q4, the sales forecasting system has been driven by MLP model.
The Multilayer Perceptron (MLP) neural network is a feedforward neural network composed of multiple layers of neurons, with each layer connected to the next layer through fully connected connections.
It is a widely used artificial neural network model commonly employed for classification and regression problems, including image recognition, speech recognition, natural language processing, recommendation systems, and more.

#### 2023 Q1 - Neural Prophet
Starting from 2023 Q1, the sales forecasting system has been driven by NP (Neural Prophet) model. Our main upgrade is as follows:
Drive sales forecasting with NP algorithm.
Standardize the model and process for multi-channel sales forecasting.
Use dynamic Safety Stock instead of static Safety Stock parameters.
We achieved a 3% improvement in comparison to the MLP model by using historical averages.

#### 2023 Q2 - Neural Prophet + Cat Boost + MKT features
Starting from 2023 Q2, the sales forecasting system has been driven by NP (Neural Prophet) model and CB (Cat Boost) model.
Another main upgrade is as follows:
Outliers optimization: Better identification of sales impacts caused by out of stock, temporary promotions, and other factors.
Integration of Marketing (MKT) features, such as SEM cost, SEM CTR, product rank, coupon and return quantity.
We achieved a 2% improvement in comparison to the NP only model by using historical averages.

#### 2023 Q3 - Neural Prophet + Cat Boost + Feature 2.0
Starting from 2023 Oct 2nd, the sales forecasting system has been driven by Feature 2.0.
Another main upgrade is as follows:
More marketing information such as price, competitors and promotions has been added.
More comprehensive and accurate anomaly detection for historical sales


# 🎯️ Measurement
Our main objective will be to improve forecast accuracy. The formula to calculate forecast accuracy is as below
Sales Forecast Accuracy = 1 - MAPE (mean absolute percentage error).

# 🔜  What's Next

# 💬 FAQ
#### What is the commercial value of 70% FA?
We will know in advance about 70% of the sales situation in the next three months, Which products will be sold in what channels and times, and how many quantities
#### Conditions for the release and launch of System FCST
Calculate the FA and FB corresponding to the Ongoing and All pools of M0~M2 and M1~M3 for at least 4 historical versions of System FCST
The average FA of the development version in the M0-M2 caliber is better than that of the production version
The average FA of the development version in the M1~M3 caliber is better than that of the production version
The FB of the development version in the M0-M2 caliber is within -10%~10%
The FB of the development version in the M1~M3 caliber is within -10%~10%, but one version is allowed to exceed the 10% threshold for FB
#### Why choose NP (Neural Prophet) model ?
Neural Prophet is a neural network-based time series forecasting model developed by Meta (Facebook) as an open-source model.
NP can model and accurately forecast time series data by decomposing it into trend and seasonal components.
Considering data availability and quality, NP's time series modeling approach is more suitable when only stable sales and inventory time series data are available.
#### How to use NP ?
Conduct stationarity test on time series and process non-stationary sequences.
Input processed time series into NP model to learn multi-dimensional growth trends, seasonal trends, etc.
Adjust model structure and customize technical parameters like Fourier terms and time series decomposition.
Conduct multi-step prediction based on time series characteristics learned by the model.
#### Why choose CB (CatBoost) model ?
CB (CatBoost or Categorical Boosting) is a gradient boosting framework developed by Yandex.
CB supports constructing complex feature space to discover feature correlations and contributions to the target.
GBDT can provide feature importance measurement and interpretability to identify key influencing factors.
CB has rapid training and can quickly respond to recent business changes.
#### How to use CB ?
Construct multidimensional features representing recent business factors.
Apply GBDT to learn feature relationships and contributions.
Parameter optimization via grid search and cross validation.
Apply optimized model to forecast recent sequence changes.
#### Why do we need feature engineering in FCST ?
Improve accuracy: Feature engineering can help models better understand data and improve prediction accuracy.
Enhance interpretability: Proper feature engineering can make some models more interpretable, helping teams understand model decision processes.
Leverage expert knowledge: Manual FCST considers more factors, integrating experts' knowledge and experience. Through feature engineering, we can incorporate such knowledge into system FCST.
Increase model robustness: Feature engineering can help models become more robust towards new, unseen data and enhance stability.
Learn from manual FCST logic: We hope system FCST can learn and apply logics from manual FCST. Feature engineering ensures models can learn and apply such logic.
#### What features have we considered in FCST ?
In feature engineering v2.0 we have cumulatively added data of inventory, SEM, price, seasonality, competitors.
Overall, our feature engineering is continuously enriching and upgrading from simple to complex, low-dimensional to high-dimensional, which will greatly enhance model predictive power. Please refer to the feature engineering section for details.
More details: 
#### Why do we need our own data science team for in-house FCST development ?
**Customized prediction**:<br>
In-house research and development can design personalized predictive models based on enterprise proprietary data and business models, which ready-made generic tools cannot achieve.<br>
**Data security and risk control:** <br>
In-house R&D helps protect core data privacy, reduce reliance on external suppliers, and mitigate data control risks.<br>
**Continuous optimization and cost control:** <br>
The internal team can continuously optimize models based on business needs and effectively control predictive costs. Outsourced black-box systems lack flexibility and incur higher costs.<br>
**Team development:** <br>
Developing the internal modeling team accumulates enterprise predictive capabilities and knowledge assets, enabling machine learning driven solutions for different scenarios.<br>
