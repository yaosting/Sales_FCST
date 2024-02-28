# Sales Forecast Project Brief
## 💫 Overview
📈 ***The Sales Forecast Project is crucial for business planning and strategy. It accurately predicts future sales volumes, allowing businesses to optimize inventory, reorder, and funding allocation***.<br><br>
***1.- Optimize our Safety stocks/reorder points -> liberate cash (more cash available for inventory) -> Increase in-stock rates and have consistency in our stock levels -> Increase revenue.***<br>
***2.- Have higher accuracy in our revenue FCST -> not constant changes in funding for inventory -> Increase in-stock rates and have consistency in our stock levels -> Increase revenue.***<br>
***3.- 数据赋能业务的突破性尝试，盘活企业数据、部门孤岛，接入三方外部市场数据，构建高质量的统一数据基座。以FCST项目为核心，用部门关键月度会议牵头，打通以Dynamic Princing、Dynamic SEM、GRS为核心的PM、MKT、SCP(采销存)部门。实现核心业务数字化、自动化，业务影响快速传递给上下游，以统一的revenue FCST为全局目标导向，提高部门间的高效协同与调整。***<br>

## The system architect is as follows (as of August 2023):
![System%20FCST%20WorkFlow.png](https://github.com/yaosting/Sales_FCST/blob/main/Docs/_static/System%20FCST%20WorkFlow.png "Magic Gardens")

***🏢 Data Warehouse:*** All data comes from UDS (Clickhouse).<br>
***📚 Feature Store:*** Contains a collection of relevant features related to sales, market trends, inventory, and products info. These features are extracted from the data warehouse and serve as input variables for the forecasting models.<br>
***🧹 Preprocessing:*** The Preprocessing module involves data cleaning, transformation, and normalization.<br>
***🛠️ Feature Engineering:*** In the Feature Engineering module, additional features are created or derived from the existing ones to enhance the predictive power of the models.<br>
***🧠 Modeling:*** The Modeling module includes the implementation of forecasting models, specifically Neural Prophet and Cat Boost models.<br>
***📈 Model Inference:*** The Model Inference module generates the final output, which is the monthly forecast for each product in each channel group for the next 12 months.<br><br>
These modules work together to provide a comprehensive sales forecasting solution, enabling businesses to make informed decisions based on accurate predictions of future sales performance.<br>

## Comparison of industry solutions
![Comparison of industry solutions.png](https://github.com/yaosting/Sales_FCST/blob/main/Docs/_static/Comparison%20of%20industry%20solutions.png "Magic Gardens")

### Monthly FCST Cycle. The collaborative process between sales forecast-driven replenishment, logistics, marketing and financial decision making.
![Monthly%20FCST%20Cycle.png](https://github.com/yaosting/Sales_FCST/blob/main/Docs/_static/Monthly%20FCST%20Cycle.png "Magic Gardens")

### System FCST Release Cycle.  The process for upgrading, validating, and releasing System FCST.
![Monthly%20FCST%20Cycle.png](https://github.com/yaosting/Sales_FCST/blob/main/Docs/_static/Monthly%20System%20FCST%20Update%20Cycle.png "Magic Gardens")

### Sales FCST Business-Data Science Collaboration Architecture(as of September 2023):
![Monthly%20FCST%20Cycle.png](https://github.com/yaosting/Sales_FCST/blob/main/Docs/_static/FCST%20Business-Data%20Science%20Collaboration%20Architecture.png "Magic Gardens")

***Distill business directives:***
Summarized the process of extracting actionable business guidelines and instructions based on analysis and insights on the business side, mainly through meetings to complete information transmission <br>
***Data Science Analysis and Feedback:***
In this stage, the data science team reviews the business directives, analyzes feasibility, evaluates implications, and provides authoritative feedback. This includes presenting data-driven insights, metrics, risks, optimizations and recommendations to enhance or validate the business directives. <br>
***Data Handoff and Transition :***
After reviewing business directives, the data science team hands off optimized directives and key metrics back to the business side for execution. Meanwhile, important features, data preprocessing and other technical outputs are transitioned to the model building phase to enable the next stage of the data science workflow. 

## 模型类项目推进方案：
#### 阶段一（3~6个月）：场景建模&算法测试
***目标***：实现核心数据整合和模型构建，以便进行快速迭代和优化。<br>
***关键任务***：<br>
数据接入和预处理：与数据提供方合作确保核心数据的准确性和完整性。针对特定业务场景和规律进行数据预处理，确保数据的独立同分布（IID）。<br>
算法选型和测试：选择适合初期探索的多样算法，例如轻量级模型，以便于调试和理解底层原理。进行初步的模型训练，调整参数，优化后处理机制。<br>
业务沟通与反馈：与业务团队紧密合作，确保模型输出与业务需求一致，及时调整模型以反映业务变化。<br>
***成果***：构建初步模型框架，获得对数据特征、模型性能的基础理解，确保模型能满足基本应用需求。<br>
#### 阶段二（6~12个月）：数据完善与算法优化
***目标***：在业务反馈的基础上，提升模型的准确性和适应性。<br>
***关键任务***：<br>
数据源扩展：基于对BigGap问题的分析，增加新的数据源，提炼出关键的、可复用的数据特征。<br>
算法迭代：选取更适合当前数据分布和业务逻辑的算法进行深入研究，如升级到集成模型等。<br>
团队协作加强：模型建设人员需与业务团队保持密切合作，共享对预测场景的理解，确保模型服务的高度符合企业需求。<br>
成果：构建出更为精准和可靠的预测模型，达到或超越商业软件的性能水平。<br>
#### 阶段三：业务整合与跨部门协作
***目标***：实现从数据驱动到业务驱动的转变，提升模型在复杂业务环境中的应用价值。<br>
***关键任务***：<br>
控制因素落实：识别并实现在预测场景中的“不可控”因素的控制，例如通过新的合作项目或跨部门协作。<br>
数据资产活化：从单一数据场景的驱动扩展到跨部门协作，利用企业内部的数据资源，从而实现更广泛的业务影响。<br>
持续优化和扩展：不断优化模型，应对新的业务挑战和需求，推动数据和模型的持续演进。<br>
***成果***：实现模型在企业级的广泛应用，为企业带来显著的商业价值和竞争优势。<br>

## [2024 OKR](https://github.com/yaosting/Sales_FCST/blob/main/Internal%20Business%20report/2024%20OKR)
***1.调整System FCST预测目标，适配2024年Infinite Business的Demand Plan OKR***<br>
***2.拓展System FCST适用范围，满足2024年Infinite Business的新渠道、新产品、新场景、新数据***<br>
***3.与需求计划团队为主的业务方进行紧密合作，在业务的协助下完成新场景、新问题、新升级的发现、分析、解决***<br>

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
