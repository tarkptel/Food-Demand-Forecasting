# 🍽️ Food Demand Forecasting App

A Machine Learning powered web application built with Streamlit that predicts the number of orders for a meal in a given week based on historical data and input features. This app is especially useful for supply chain optimization and inventory planning in food delivery or distribution services.


## 🚀 Live Demo

👉 [Click here to view the deployed app](https://huggingface.co/spaces/tarkpatel/food-demand-forecast)  



## 📸 Demo Preview

<img src="![image](https://github.com/user-attachments/assets/e69574eb-45fa-4ef5-8a6d-88cc8de90a3b)
" width="800"/>



## 🧠 Features

- Predicts food demand (number of orders) for a given center and meal.
- Feature engineering using historical demand.
- Custom encoding for center and meal IDs using LabelEncoders.
- Interactive UI using Streamlit.
- Custom background and styled interface.
- Historical lag features, rolling statistics, and promotion-related features.
- Clean and minimal design for easy usability.



## 📁 Dataset

- Training data used: `train.csv`
- Data includes: `center_id`, `meal_id`, `week`, `num_orders`, `base_price`, `checkout_price`, `emailer_for_promotion`, `homepage_featured`



## 🧪 Feature Engineering

The following features are created dynamically before prediction:

- `week_sin`, `week_cos` – Encode week cyclically to capture seasonality.
- `demand_lag_1`, `demand_lag_2` – Demand in previous 1 and 2 weeks.
- `rolling_mean_3` - 3-week rolling mean of demand.
- `rolling_std_3` – 3-week rolling standard deviation of demand.
- `price_diff` - Difference between base price and checkout price.
-  `price_ratio` - Ratio of checkout price to base price.
- `meal_avg_demand` - Average demand for each meal across all centers.
- `center_meal_avg` - Average demand for each meal in a specific center.
- `quarter` - Week converted into quarter (0 to 3).
- `weeks_since_event` - Weeks passed since a reference point (e.g. week 100).
- `normalized_week` - Week normalized based on first week of each meal.
- `is_promo` - Whether emailer or homepage promotion is active.
- `promo_effect` - Combined effect of promotion and price difference.
- `price_per_center` - Average checkout price per center.
- `meal_popularity_in_center` - 	Meal popularity within a specific center.
- `center_id_encd`, `meal_id_ecd` - Encoded categorical features for center and meal IDs.
