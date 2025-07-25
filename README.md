
# 🧠 Fraud Detection App

🔗 [Live Demo](https://fraud-detection-d532ad7fohyswbhntwwfj6.streamlit.app/)

A web-based Streamlit application that helps detect potentially fraudulent transactions using a trained machine learning pipeline. The app allows users to input key transaction parameters and instantly receive a fraud prediction result.

---

## 📌 Project Overview

This project includes:
- A **Streamlit frontend app** (`fraud_detection.py`) that allows real-time transaction fraud predictions.
- A **Jupyter Notebook** (`analysis_model.ipynb`) that handles training, evaluation, and saving of the machine learning pipeline (`fraud_detection_pipeline.pkl`).

The model is trained on financial transaction data with the goal of identifying fraudulent activities based on transaction type, amount, and sender/receiver balances.

---

## 🚀 App Features

- Accepts inputs like:
  - Transaction Type (`PAYMENT`, `TRANSFER`, `CASH_OUT`, `DEBIT`)
  - Amount
  - Sender's Old and New Balances
  - Receiver's Old and New Balances
- Uses a machine learning pipeline loaded from `fraud_detection_pipeline.pkl`
- Outputs:
  - **Prediction Result** (0 → Not Fraud, 1 → Fraud)
  - Friendly message with success or warning flag

---

## 🧪 Model Training

The notebook `analysis_model.ipynb` handles:
- Data loading and preprocessing
- Feature encoding and transformation
- Model training (possibly using tree-based or ensemble classifiers)
- Evaluation using classification metrics
- Export of the trained pipeline using `joblib`

---

## 📁 File Structure

├── fraud_detection.py              # Streamlit application   
├── analysis_model.ipynb            # Jupyter notebook for training and evaluation  
├── fraud_detection_pipeline.pkl    # Pre-trained ML pipeline

## ⚙️ Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/akhilamurarka/Fraud-Detection.git
   
   cd Fraud-Detection
  
2. Install dependencies:
  ```
   pip install -r requirements.txt
   ```

   If `requirements.txt` is not available, install manually:
   ```
   pip install streamlit joblib scikit-learn numpy pandas
   ```

3. Run the app:
  ```
   streamlit run fraud_detection.py
   ```

## 💡 Example Input

| Transaction Type        |     TRANSFER     |
|-------------------------|------------------|
| Amount                  | 5000             |
| Old Balance (Sender)    | 10000            |
| New Balance (Sender)    | 5000             |
| Old Balance (Receiver)  | 1000             |
| New Balance (Receiver)  | 6000             |

Prediction: 1 (i.e., This transaction can be fraud )


## 📝 Notes

- The model expects valid transaction details as inputs.

- Ensure `fraud_detection_pipeline.pkl` is present in the same directory as `fraud_detection.py` before running the app.
