<div align="center">

  <a href="https://tarkptel.github.io/">
    <img src="https://img.shields.io/badge/🌐-Portfolio-blue" height="28">
  </a>
  <a href="https://www.kaggle.com/tark01/">
    <img src="https://img.shields.io/badge/-Kaggle-20BEFF?logo=kaggle&logoColor=white" height="28">
  </a>
  <a href="https://www.linkedin.com/in/tark-patel/">
    <img src="https://img.shields.io/badge/-LinkedIn-0077B5?logo=linkedin&logoColor=white" height="28">
  </a>

</div>

# 🍽️ Food Demand Forecasting App

A Machine Learning powered web application built with Streamlit that predicts the number of orders for a meal in a given week based on historical data and input features. This app is especially useful for supply chain optimization and inventory planning in food delivery or distribution services. <br><br>


## 🚀 Live Demo
 
You can try the web app live here: **[🔗 Hugging Face Space](https://huggingface.co/spaces/tarkpatel/food-demand-forecast)** <br><br>

## 🧠 Features

- Predicts food demand (number of orders) for a given center and meal.
- Feature engineering using historical demand.
- Custom encoding for center and meal IDs using LabelEncoders.
- Interactive UI using Streamlit.
- Custom background and styled interface.
- Historical lag features, rolling statistics, and promotion-related features.
- Clean and minimal design for easy usability. <br><br>



## 📁 Dataset

- Training data used: `train.csv`
- Data includes: `center_id`, `meal_id`, `week`, `num_orders`, `base_price`, `checkout_price`, `emailer_for_promotion`, `homepage_featured`.<br><br>



## 🎯 Feature Engineering

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
- `center_id_encd`, `meal_id_ecd` - Encoded categorical features for center and meal IDs. <br><br>

<h2> 🏆 Model Training Approach</h2>
    <p>I cleaned and preprocessed the dataset to remove irrelevant or noisy data. Several machine learning algorithms were used to train the model, including:</p>
    <ul>
        <li>XGBoost Regressor</li>
        <li>Random Forest</li>
    </ul>
    <p> XGBoost Regressor & Random Forest Both provided the best results with an R<sup>2</sup> score of <strong>87%</strong>. After evaluation, XGBoost showed better performance (lower RMSE), so it was selected as the final model for deployment.. </p> <br><br>

<h2> 🚀 Deploying Through Render</h2>
    <p>I Deploy my model through Hugging Face. The trained XGBoost model was deployed using Streamlit, a fast and lightweight framework for building interactive ML web apps. The app allows users to select a week, meal, and center details, and instantly predicts the expected food demand.</p> <br><br>

<h2> 👑 Author</h2>
    <p>Developed by <strong>Tark Patel</strong>.</p>
    <p><a href="https://www.linkedin.com/in/tark-patel/" target="_blank">LinkedIn</a> | <a href="https://www.kaggle.com/tark01" target="_blank">Kaggle</a></p>
