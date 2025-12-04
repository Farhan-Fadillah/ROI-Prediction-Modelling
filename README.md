# Retail Intelligence: Maximizing ROI through Predictive Analytics

In the fast-paced and highly competitive retail industry, profit margins are often razor-thin. The single biggest challenge facing every retailer from local grocery stores to e-commerce giants is Inventory Management. Holding too much stock (overstock) ties up capital and inflates storage costs, while running out of stock (understock) during high demand leads to lost revenue and customer dissatisfaction.

<img width="855" height="441" alt="image" src="https://github.com/user-attachments/assets/816ca270-68a8-4d1e-9ced-430e5644d952" />

Many retailers still rely on intuition or simple manual calculations to decide which products to keep or restock. This approach often fails to capture complex dynamics such as sales velocity, supply chain risks (lead time), and the impact of returns (refunds). Consequently, business decisions are frequently suboptimal, resulting in accumulating Dead Stock or costly Lost Sales.

<img width="859" height="588" alt="image" src="https://github.com/user-attachments/assets/0e35d803-b636-4315-a0b1-38db385380b0" />

To bridge this gap, this project introduces the Retail ROI Optimization System, a Machine Learning-based solution designed to accurately predict product profitability (ROI). The system goes beyond simply identifying "what sells" to analyzing overall inventory health, providing strategic recommendations on whether a product should be immediately restocked or discontinued.

## Project Significance and Benefits
- Financial Health Improvement: Directly improves Cash Flow by prioritizing capital investment in "Star" products (High ROI) and preventing capital waste on "Dead" products (Low ROI).
- Inventory Efficiency: Reduces operational warehousing costs (holding costs) by detecting overstock risks early through stock ratio analysis.
- Supply Chain Risk Mitigation: Integrates external risk factors such as lead time (delivery wait times) into predictions, ensuring the company avoids ordering goods that will arrive too late after a trend has passed.
- Data-Driven Decision Making: Shifts the decision-making culture from "gut feeling" to objective data-driven insights, enabling procurement teams to operate with greater precision.
- Scalability: The model is designed to handle thousands of SKUs simultaneously, making it a scalable solution that grows with the business.

## Why This Project Matters
Retail success is no longer determined solely by who has the best product, but by who has the most efficient operations. This project addresses that challenge by leveraging Artificial Intelligence to transform raw transaction data into actionable insights. With the ability to predict ROI with high accuracy (97%), the system acts as a "Financial Guardian," protecting company margins from inefficiency and market risks.
Dataset Description
The dataset consists of retail operational data that has undergone deep Feature Engineering to capture crucial business dimensions. Key features include:
- restock_lead_days: The time required for suppliers to deliver goods (The most influential feature).
- unit_margin_ratio: The net profit percentage per unit.
- stock_cover_ratio: The ratio of available stock compared to daily sales velocity.
- sell_through_rate: How quickly a percentage of stock is sold out within a specific period.
- lead_time_risk: An interaction feature detecting high-risk scenarios (long lead times combined with demand spikes).
- refund_rate: The percentage of items returned by customers (an indicator of quality/satisfaction).
- Target Variable (roi_class): A binary classification where 1 represents High ROI Products (Invest) and 0 represents Low ROI Products (Inefficient).

## Machine Learning Model: Random Forest Classifier

<img width="879" height="437" alt="image" src="https://github.com/user-attachments/assets/403e33e8-19a5-4638-89d7-6358dba5c806" />

### Why Random Forest?
- Handling Non-Linearity: Relationships in retail data are rarely linear. For instance, a low price does not always guarantee high sales, and high sales do not always guarantee profit. Random Forest excels at capturing these non-linear patterns and complex feature interactions.
- Robust to Imbalance: Retail datasets are often imbalanced (more average products than best-sellers). By utilizing class_weight='balanced', the model handles this disparity without biasing towards the majority class.
- Feature Importance: The model provides transparency by highlighting which variables most influence decisions (in this case: Lead Time and Margin), which is critical for strategic planning.
- Ensemble Power: By aggregating hundreds of decision trees, the model is highly resistant to overfitting and provides stable predictions on new data.

## Project Flow Overview
### Step-by-step Flow:
1. Data Ingestion & Preprocessing:
   - Loading raw transaction data (sales, stock, costs, prices).
   - Cleaning data and handling missing values.
2. Advanced Feature Engineering:
   - Creating meaningful business metrics such as sell_through_rate (sales speed), stock_cover_ratio (stock durability), and real_net_profit (accounting for refund and holding costs).
   - Defining the target label: ROI Class 1 (High) vs. Class 0 (Low).
3. Model Training & Tuning:
   - Splitting data into Training and Testing sets.
   - Training the Random Forest Classifier using GridSearchCV to find the best parameters (hyperparameter tuning) to maximize performance.
4. Evaluation:
   - Measuring model performance using Confusion Matrix and ROC-AUC Score.
   - Current results show 97% Accuracy and 0.95 ROC-AUC, indicating a highly reliable model.
5. Inference & Business Recommendation:
   - The system ingests new product data or weekly ongoing data.
   - The model predicts the ROI class and a probability score.
   - Automated Output: The system generates actionable labels:
     - 🔥 STAR PRODUCT: Priority Restock.
     - ⚠️ DEAD STOCK: Recommendation for Discount/Clearance.
     - ✅ POTENTIAL: Monitor Margin.
    

## Streamlit App Features
Features:
- Data Input = Sidebar file uploader for CSV files (test_tbl_data) with schema validation and a historical data template display.
- ROI Prediction = Random Forest Classifier model that predicts product profitability (High ROI vs. Low ROI) based on inventory metrics.
- Smart Recommendations = Logic-based actionable insights (e.g., "Restock Segera", "Stop Order") generated from prediction confidence scores.
- Automated Feature Engineering = Automatically calculates advanced retail metrics like Sell-Through Rate, Stock Cover Ratio, and Margin from raw input data.
- Visualization = Interactive dashboard displaying KPI metrics, recommendation distribution charts, and feature importance analysis.
- Model Training = Automated background training process using cached resources to ensure the model is ready immediately upon launch.
- Export Capability = Download button allowing users to save the final analysis, including predictions and action plans, as a CSV file.

<img width="1920" height="915" alt="image" src="https://github.com/user-attachments/assets/9f17e2e6-9041-4f1c-996d-de04255f7381" />

<img width="1914" height="939" alt="image" src="https://github.com/user-attachments/assets/57fb34ae-bd31-4a22-ac1b-a2d87edc0c23" />

<img width="1918" height="955" alt="image" src="https://github.com/user-attachments/assets/5a41cc32-4065-42b0-a2e7-a81b45b71a88" />

## Link Application
[Link](https://roi-prediction-modelling.streamlit.app/)





