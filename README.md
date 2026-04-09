# 🏠 California Housing Price Prediction using ANN

This project demonstrates the implementation of an **Artificial Neural Network (ANN)** for solving a **regression problem** using the California Housing dataset.

The goal is to predict **housing prices** based on various input features such as income, population, and location-related factors.

---

## 📊 Dataset

- Dataset: California Housing Dataset  
- Source: Scikit-learn  
- Type: Regression  

### Features:
- Median Income  
- House Age  
- Average Rooms  
- Population  
- Latitude & Longitude  

---

## ⚙️ Technologies Used

- Python 🐍  
- TensorFlow / Keras  
- NumPy & Pandas  
- Matplotlib  
- Scikit-learn  

---

## 🧠 Model Architecture

- **Input Layer:** 8 features  
- **Hidden Layer 1:** 30 neurons (ReLU)  
- **Hidden Layer 2:** 10 neurons (ReLU)  
- **Hidden Layer 3:** 5 neurons (ReLU)  
- **Output Layer:** 1 neuron (Linear)  

---

## 🔄 Data Preprocessing

- Train, validation, and test split  
- Feature scaling using **StandardScaler**  
- Avoided data leakage (fit on training data only)  

---

## 💻 Sample Code

```python
# Import libraries
from tensorflow.keras.models import Sequential
from tensorflow.keras.layers import Dense
from tensorflow.keras.callbacks import EarlyStopping

# Build ANN model
model = Sequential([
    Dense(30, activation='relu', input_shape=(8,)),
    Dense(10, activation='relu'),
    Dense(5, activation='relu'),
    Dense(1)
])
```
---

# Compile model
model.compile(optimizer='adam', loss='mse', metrics=['mae'])

# Train model
early_stop = EarlyStopping(patience=5, restore_best_weights=True)

model.fit(X_train, y_train, epochs=20,
          validation_data=(X_valid, y_valid),
          callbacks=[early_stop])

---

## 📈 Results & Visualization

- Plotted training vs validation loss  
- Evaluated model on test dataset  
- Observed model performance and generalization  

---

## 🔍 Prediction

```python
new_scaled = scaler.transform(new.reshape(1, 8))
prediction = model.predict(new_scaled)

---

## 🔔 Callbacks Used

- EarlyStopping → Prevent overfitting  
- ModelCheckpoint → Save best model  
- TensorBoard → Monitor training  

---

## 📌 Key Learnings

- Importance of feature scaling in ANN  
- Avoiding data leakage  
- Using callbacks for efficient training  
- Understanding overfitting using graphs  

---

## 🚀 Future Improvements

- Use Adam optimizer  
- Hyperparameter tuning  
- Add Dropout layers  
- Deploy using Flask / Streamlit  

---

## 🧠 Conclusion

This project shows how ANN can be effectively applied to regression problems and highlights best practices like preprocessing, callbacks, and evaluation.

---

## 📬 Connect with Me

- LinkedIn: https://www.linkedin.com/in/priyanka-mittha 
- GitHub: https://github.com/PriyankaMittha  
