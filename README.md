# 🧠 EMNIST Digit & Alphabet Classifier (Streamlit App)

A web app built with **Streamlit** and **TensorFlow** that can recognize **handwritten digits (0–9)**, **uppercase letters (A–Z)**, and **lowercase letters (a–z)** using a CNN trained on the **EMNIST ByClass dataset**.

You can draw directly on a digital canvas or upload an image of a handwritten character, and the app will predict which character it is — along with the top 5 most likely predictions.

---
👉 **Live Demo:** [https://letter-predict-omkar-kashid23.streamlit.app/](https://letter-predict-omkar-kashid23.streamlit.app/)

---

## 🧩 Overview

This project uses a **Convolutional Neural Network (CNN)** trained on the EMNIST dataset to identify handwritten digits and alphabets.
It provides two easy-to-use input methods:

-   ✍️ **Draw your character** on a digital canvas.
-   📤 **Upload an image** (PNG/JPG) of a handwritten symbol.

---

## 🧠 Model Details

-   **Dataset:** EMNIST ByClass (62 total classes)
    -   Digits (0–9)
    -   Uppercase letters (A–Z)
    -   Lowercase letters (a–z)
-   **Input shape:** 28x28 grayscale images
-   **Framework:** TensorFlow/Keras
-   **Model type:** CNN (2 Conv2D + MaxPooling + Dense layers)
-   **File:** `cnn_emnist_digits_alphabets.pkl` (pickled model)

---

## 🛠️ Project Setup

### 🗂️ Folder Structure

```plaintext
📁 emnist_classifier
┣ 📄 app.py                      ← Streamlit app
┣ 📄 cnn_emnist_digits_alphabets.pkl   ← Pre-trained CNN model
┣ 📄 requirements.txt             ← Dependencies
┣ 📄 README.md                    ← Documentation (this file)
```

---

## 🧮 How the App Works

### Model Loading

-   The model is loaded from `cnn_emnist_digits_alphabets.pkl` using `pickle`.
-   Cached with `@st.cache_resource` for faster reloads.

### Preprocessing

-   Input image resized to 28x28 pixels, converted to grayscale.
-   Colors inverted (white character on black background).
-   Normalized pixel values between 0 and 1.
-   Reshaped to `(1, 28, 28, 1)` for model prediction.

### Prediction

-   CNN outputs probabilities for all 62 classes.
-   The app displays the most likely prediction.
-   Top 5 predictions shown as a bar chart for comparison.

### Context-Aware Prediction

-   You can select input context:
    -   Auto Detect
    -   Digit (0–9)
    -   Letter (A–Z, a–z)
-   The app prioritizes predictions based on your context hint.

---

## 📊 Example Output

### Example 1 — Drawn Digit

-   **Input:** ✍️ Draw “7”
-   **Output:** Predicted Class → 7
-   **Confidence:** 99.4%

### Example 2 — Uploaded Image

-   **Input:** 🖼️ Uploaded lowercase “a”
-   **Output:** Predicted Class → a
-   **Top 5 Predictions:** a, o, s, e, c

---

## 👨‍💻 Author

**Omkar Kashid**

AI & Data Science Enthusiast

📍 India

> 💬 "Turning code into creativity — one model at a time."

