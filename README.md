
# IndabaX Nigeria 2025 Deploying Machine Learning Models with Streamlit Workshop

Welcome to the hands-on project for the workshop **"Deploying Machine Learning Models with Streamlit for Nigerian SMEs"**.

This project demonstrates how to:
- Use real Nigerian e-commerce data to train a sales prediction model
- Build a web-based prediction form using **Streamlit**
- Deploy the model live on **Streamlit Cloud** so SMEs can use it without coding

---

## 📌 Use Case: Why This Matters
Small and Medium Enterprises (SMEs) in Nigeria often lack tools for forecasting sales or planning inventory. This project provides a lightweight, low-cost solution they can use directly on mobile or desktop — powered by open-source tools.

---

## 🧠 What’s Inside

| File                              | Description                                                    |
|-----------------------------------|----------------------------------------------------------------|
| `app.py`                          | The Streamlit app with a form-based input UI                   |
| `model.pkl`                       | Trained Random Forest model for predicting sales               |
| `requirements.txt`                | List of Python packages needed for deployment                  |
| `nigeria_sme_sales_prediction.ipynb` | Google Colab notebook used to clean, train, and export model   |
| `Streamlit_App_Code_Explanation_Workshop.docx` | Presenter-friendly code breakdown                   |

---

## 📊 Dataset

- Source: [Nigerian E-Commerce Dataset (Kaggle)](https://www.kaggle.com/datasets/ademolababs/nigerian-ecommerce-sales-dataset)
- Columns used: `Order Date`, `Item Price`, `Quantity`, `Order Region`, etc.
- Features engineered: day, month, is_weekend, promo_day, weather (simulated)

---

## 🛠️ Tech Stack

- **Model**: RandomForestRegressor (from `scikit-learn`)
- **UI**: Streamlit
- **Deployment**: Streamlit Cloud
- **Notebook**: Google Colab

---

## 🚀 How to Run Locally

```bash
# Step 1: Clone this repo
git clone https://github.com/HarbdhulQuadri/IndabaX2025-Deploying-with-streamlit-demo.git
cd sme-sales-streamlit-app

# Step 2: Install dependencies
pip install -r requirements.txt

# Step 3: Run the app
streamlit run app.py
```

---

## 🌐 Deploy to Streamlit Cloud

1. Push this repo to GitHub.
2. Go to [streamlit.io/cloud](https://streamlit.io/cloud)
3. Connect your GitHub account.
4. Choose this repo.
5. Set `app.py` as the entry file.
6. Click **Deploy** 🚀

---

## 📸 App Demo Screenshot


---

## 🧑‍🏫 Workshop Objective

By the end of the workshop, you will:
- Understand how to use real Nigerian SME data for training an ML model
- Learn to export ML models using `joblib`
- Build a web interface with Streamlit forms
- Deploy your model live on Streamlit Cloud
- Predict sales in real-time using only your browser

---
## 🤝 Connect With Me

Let’s stay in touch and collaborate on meaningful tech for Africa:  
🔗 [Connect on LinkedIn](https://www.linkedin.com/in/adegbiji)

---

## 💬 License & Contribution

This project is open for educational purposes.  
Feel free to fork, remix, and contribute improvements!

---

## 🔗 Useful Links

- [Streamlit Docs](https://docs.streamlit.io)
- [Google Colab](https://colab.research.google.com/)
- [Scikit-learn Docs](https://scikit-learn.org/)
- [Kaggle Dataset](https://www.kaggle.com/datasets/ademolababs/nigerian-ecommerce-sales-dataset)
