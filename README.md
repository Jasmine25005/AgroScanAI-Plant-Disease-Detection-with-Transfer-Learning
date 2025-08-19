# 🌿 LeafVision: End-to-End Plant Disease Classification 🔬

A deep learning-based computer vision project to classify plant diseases using images of leaves — built with **CNN**, **VGG16**, and **ResNet50**.

---

# ✅ Zoomcamp Final Project Review Checklist

- [x] Problem framed clearly
- [x] Preprocessing + EDA
- [x] Trained multiple models
- [x] Used MLflow
- [x] Used FastAPI (web service)
- [x] Used Prefect (workflow)
- [x] Used ImageDataGenerator with proper preprocessing
- [x] Full repo + requirements.txt + Makefile
- [x] README with Kaggle + Sample outputs
- [x] Deployed model works
---

## 📸 Dataset

- Source: [Kaggle - Plant Disease Recognition](https://www.kaggle.com/datasets/rashikrahmanpritom/plant-disease-recognition-dataset)
- Classes:
  - 🌱 Healthy
  - 🍃 Powdery Mildew
  - 🍂 Rust

**![Class Balances](DataWeights.png)**
---

## 🧠 Models Used

| Model             | Preprocessing           | Accuracy |
|------------------|-------------------------|----------|
| Custom CNN        | `rescale=1./255`        | ✅       |
| VGG16             | `preprocess_input()`    | ✅       |
| ResNet50          | `preprocess_input()`    | ✅       |

---

## 📊 Evaluation Metrics

- ✅ Accuracy & Val Accuracy over Epochs
- 📉 Training & Validation Loss
- 🔍 Confusion Matrix
- 📋 Classification Report
- 🖼️ Visualized Predictions on Test Set

---

## 🚀 Key Takeaways

- Learned how **learning rate** directly impacts training efficiency
- Built a powerful, modular **`DataGenerator()`** for flexible preprocessing
- Compared model performance under fair evaluation conditions
- Saved and exported models for reuse + visualized results with Matplotlib

---

## 🔍 Sample Prediction Output

![Sample Predictions](sample_predictions.png)

---

## 💡 Lessons Learned

🧠 **"Accuracy stuck at 33%?"** It wasn't the model, the data, or the augmentation...

✳ It was the **learning rate**!

- Lowering the LR from `0.001` to `0.0001` fixed the issue!
- Proper preprocessing based on the model is a **must** (CNN ≠ ResNet ≠ VGG)

---


---

## 📦 Tech Stack

- Python (TensorFlow, Keras, OpenCV, Matplotlib, Sklearn)
- Jupyter Notebooks
- Deep Learning (CNN, Transfer Learning)
- ImageDataGenerator for augmentation

---

## 📌 Future Improvements

- Add model monitoring & logging via Weights & Biases or MLflow
- Use class balancing / focal loss for better minority class performance
- Convert model to TensorFlow Lite for low-resource IoT deployment

---

## 🧑‍💻 Author

Made with ❤️ by Jasmine
---
---

## 🛠️ MLOps Pipeline ✅

To ensure this project is scalable, reproducible, and production-ready, I implemented multiple MLOps components:

### 📋 **1. Experiment Tracking**
- Tracked model runs, parameters, metrics, and artifacts using `MLflow`.
- Different experiments were logged for:
  - Custom CNN
  - Transfer Learning (VGG16, ResNet50)
- Models saved and versioned under the MLflow Model Registry.

### 🌀 **2. Workflow Orchestration**
- Built a simple training pipeline using `Prefect`.
- Each step (data loading → training → evaluation) is modular and traceable.
- Easily replaceable steps for future automation through CI/CD.

### 🌐 **3. Model Deployment**
- Created a `FastAPI` web service to serve trained models.
- Takes image input and returns predicted class.
- Supports both custom and transfer learning models.

### 📊 **4. Monitoring**
- Used `Evidently` to generate drift reports between training and test sets.
- Supports future integration with monitoring dashboards (e.g., Grafana, Streamlit).

### 🔁 **5. Reproducibility**
- `requirements.txt` with all dependencies
- `Makefile` for running key steps (train, test, deploy)
- Saved models & configs


---

