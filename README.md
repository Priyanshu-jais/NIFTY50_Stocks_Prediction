
## 🧾 README for "NIFTY 50 Price Prediction using Bidirectional LSTM"

### 📌 Objective

The objective of this project is to **predict future stock prices of the NIFTY 50 index** using a **Bidirectional Long Short-Term Memory (Bi-LSTM)** neural network. By leveraging historical stock price data, the model aims to learn sequential patterns and forecast the closing prices accurately.

---

### ⚙️ Methodology

1. **Data Collection**  
   - Historical stock prices of NIFTY 50 from `01-01-2000` to `03-03-2025`.
   - Columns used: `Open`, `High`, `Low`, and `Close`.

2. **Data Preprocessing**
   - Dates are converted to datetime and sorted.
   - MinMaxScaler is applied to normalize values between 0 and 1.
   - Time-series data is prepared by creating sequences of 60 timesteps to predict the next closing price.

3. **Model Architecture**
   - A Sequential model using:
     - 2 Bidirectional LSTM layers (100 units each),
     - Dropout for regularization,
     - Dense layers with ReLU and final linear activation.
   - Loss function: Mean Squared Error (MSE)
   - Optimizer: Adam
   - EarlyStopping is used to prevent overfitting.

4. **Training**
   - Training-Validation Split: 80% training data.
   - Model is trained for 500 epochs with a batch size of 64.
   - Validation is performed on the remaining 20% with early stopping (patience=20).

5. **Evaluation**
   - Evaluation metrics:
     - **Mean Squared Error (MSE)**
     - **Mean Absolute Error (MAE)**
     - **R² Score**
   - Visualization of:
     - Full Prediction vs Actual
     - Zoomed-in Plot for Last 100 days
     - Loss curves for training and validation

---

### 🧠 Logic of the Code

The core of the model lies in the following steps:

- `create_dataset()`: Converts a continuous time series into supervised learning data with features and labels.
- `Bidirectional(LSTM)`: Processes sequence data in both forward and backward directions, improving the context learned from past and future steps.
- `Dropout`: Prevents overfitting by randomly disabling neurons during training.
- `EarlyStopping`: Monitors validation loss and restores the best model if no improvement is seen for 20 epochs.

---

### 📊 Results

**Evaluation Metrics on Test Data:**
- **Mean Squared Error**: _(calculated and printed in the notebook)_
- **Mean Absolute Error**: _(calculated and printed in the notebook)_
- **R² Score**: _(printed after predictions)_

> These values confirm the model’s efficiency in forecasting stock prices.

**Visualization:**
- 📈 Plot comparing **actual vs predicted prices** shows strong alignment.
- 🔍 A zoomed-in view for the **last 100 days** highlights the model’s accuracy in short-term prediction.
- 📉 Loss curves show a smooth convergence of both training and validation loss.

---

### 🖼️ Output Plots

The notebook generates several key plots:
- **Full Range Prediction** (`Actual vs Predicted`)
- **Zoomed View (Last 100 values)**
- **Loss Curves** (`Training vs Validation`)

All visualizations indicate a well-trained model with good generalization capabilities.

---

### 🗂️ Repository Structure

```
📁 NIFTY-BiLSTM-Prediction/
│
├── Bi-LSTM.ipynb              # Main Notebook
├── NIFTY50_Historical.csv     # Historical data used (not included here)
└── README.md                  # You're reading it!
```

---

