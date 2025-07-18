
# 🧾 `app.py` Code Breakdown – Nigerian SME Sales Predictor

This document provides a clear, line-by-line explanation of the `app.py` file used in the Streamlit web application. The app allows Nigerian SME owners to make daily sales predictions using a trained machine learning model.

---

## 📂 File Purpose

`app.py` is the core script of the Streamlit application. It loads a trained model, displays a user-friendly form, accepts input, and shows predicted sales results based on business logic.

---

## 🔍 Code Walkthrough

```python
import streamlit as st
import joblib
import numpy as np
```

- **Libraries**:
  - `streamlit`: for the user interface.
  - `joblib`: to load the serialized machine learning model.
  - `numpy`: to prepare feature vectors for prediction.

---

```python
@st.cache_resource
def load_model():
    return joblib.load("model.pkl")

model = load_model()
```

- **Model Loading**:
  - Loads the pre-trained Random Forest model from `model.pkl`.
  - `st.cache_resource` ensures the model is only loaded once for better performance.

---

```python
st.set_page_config(page_title="🇳🇬 Nigerian SME Sales Predictor", layout="centered")
st.title(" Predict Daily Sales for Nigerian SMEs")
st.markdown("""
This tool helps Nigerian small businesses forecast daily sales using a machine learning model trained on real e-commerce data.
""")
```

- **App Configuration**:
  - Sets the browser tab title and layout.
  - Displays a page title and introductory markdown.

---

```python
with st.form("sales_form"):
    col1, col2 = st.columns(2)

    with col1:
        day = st.number_input("Day of Month", min_value=1, max_value=31, value=15)
        month = st.number_input("Month", min_value=1, max_value=12, value=7)

    with col2:
        is_weekend = st.selectbox("Is it a Weekend?", ["No", "Yes"])
        promo_day = st.selectbox("Is it a Promo Day?", ["No", "Yes"])

    weather = st.selectbox("Weather Condition", ["Sunny", "Cloudy", "Rainy"])
    submitted = st.form_submit_button("Predict")
```

- **User Input Form**:
  - Provides five inputs: day, month, weekend status, promo status, and weather condition.
  - `st.columns()` creates a side-by-side layout for improved UX.
  - `st.form()` ensures all inputs are collected before prediction is triggered.

---

```python
if submitted:
    weekend = 1 if is_weekend == "Yes" else 0
    promo = 1 if promo_day == "Yes" else 0
    weather_val = {"Sunny": 0, "Cloudy": 1, "Rainy": 2}[weather]

    features = np.array([[day, month, weekend, promo, weather_val]])
    prediction = model.predict(features)[0]

    st.success(f"📈 Predicted Sales: ₦{prediction:,.2f}")
```

- **Prediction and Output**:
  - Converts categorical selections into numerical values.
  - Creates a feature array for the ML model.
  - Predicts sales and displays it in a success box with Naira formatting.

---

## 💡 Conclusion

This app.py file is a complete minimal setup that enables Nigerian SMEs to interact with a real machine learning model through a friendly web interface — no data science background required.

The full prediction pipeline is hosted on Streamlit Cloud, making it easy to access from any device.
