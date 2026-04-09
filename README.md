# Artificial Neural Network (ANN) for Regression

## 1. What is ANN using Regression?

Artificial Neural Network (ANN) is a computational model inspired by the human brain. It can learn patterns from data to make predictions.  

When using ANN for **regression**, the goal is to **predict a continuous numerical value** rather than a category.  

**Example Use Cases:**
- Predicting house prices
- Predicting stock prices
- Forecasting temperature

**How it works:**
- **Input Layer:** Features of the dataset (e.g., size of house, number of rooms)  
- **Hidden Layers:** Neurons that extract patterns from input data  
- **Output Layer:** Single neuron that predicts a continuous value  
- **Activation Function:** `ReLU` for hidden layers; `linear` (or no activation) for output in regression  
- **Loss Function:** `Mean Squared Error (MSE)` or `Mean Absolute Error (MAE)`  

---

## Callbacks in Keras/TensorFlow

**Callbacks** are special functions that are executed during training of a neural network. They help you **monitor, control, and optimize** the training process.  

### **Why Use Callbacks?**
- Track the model's performance on validation data in real-time  
- Stop training early to prevent overfitting  
- Save the best version of your model automatically  
- Adjust learning rate dynamically if training plateaus  
- Visualize metrics using TensorBoard  

### **Common Callbacks**

| Callback                | Purpose                                                                 |
|-------------------------|-------------------------------------------------------------------------|
| **EarlyStopping**       | Stop training if validation loss does not improve for a set number of epochs |
| **ModelCheckpoint**     | Save the best model automatically during training                       |
| **ReduceLROnPlateau**   | Reduce the learning rate if the model stops improving                   |
| **TensorBoard**         | Visualize training metrics like loss and accuracy in real-time         |

---

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

## ⚡ Model Training with Callbacks

```python
# Create a Sequential ANN model using predefined layers
model_2 = tf.keras.models.Sequential(LAYERS)

# Define loss function and optimizer
LOSS = 'mse'          # Mean Squared Error (used for regression)
OPTIMIZER = 'sgd'     # Stochastic Gradient Descent optimizer

# Compile the model (configure training process)
model_2.compile(
    optimizer=OPTIMIZER,  # Controls how weights are updated
    loss=LOSS             # Measures prediction error
)

# Define number of training epochs
EPOCHS = 20

# Callback to save the best model during training
checkpoint_cb = tf.keras.callbacks.ModelCheckpoint(
    'my_model.keras',     # File to save model
    save_best_only=True   # Save only best version
)

# Callback to stop training early if no improvement
early_stopping_cb = tf.keras.callbacks.EarlyStopping(
    patience=5,                 # Wait 5 epochs before stopping
    restore_best_weights=True   # Restore best weights after stopping
)

# Callback to visualize training using TensorBoard
tensorboard_cb = tf.keras.callbacks.TensorBoard(
    log_dir='logs'  # Directory for logs
)

# Combine all callbacks into a list
CALLBACKS = [checkpoint_cb, early_stopping_cb, tensorboard_cb]

# Train the model with training data and validate on validation data
history = model_2.fit(
    X_train, y_train,                    # Training data
    epochs=EPOCHS,                      # Number of iterations
    validation_data=(X_valid, y_valid), # Validation data
    callbacks=CALLBACKS                 # Apply callbacks
)
```
---

## 📈 Results & Visualization

- Plotted training vs validation loss  
- Evaluated model on test dataset  
- Observed model performance and generalization  

---

## 🔍 Prediction

```python
# Predict output for a new single data point (reshape to match input shape)
model.predict(new.reshape((1,8)))
```
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
