# 🌍 Hyperspectral Pixel Classification with Machine Learning
<img width="2570" height="1928" alt="classified_map" src="https://github.com/user-attachments/assets/24a29181-8cf6-466c-aadd-0f68523c7e10" />

## 🛰️ Project Overview

Hyperspectral imagery captures hundreds of spectral bands for each pixel, allowing detailed identification of materials and land cover types based on their **spectral signatures**.

This project implements a **pixel-based hyperspectral image classification workflow** using multiple supervised machine learning algorithms. The goal is to evaluate how well different models classify land cover types using spectral information.

The workflow includes:

* Data preprocessing
* Stratified train–test sampling
* Training multiple machine learning models
* Model evaluation using classification metrics
* Visualization of classification performance

This project demonstrates how machine learning can be applied to **remote sensing and hyperspectral data analysis**.

---

## 🎯 Objectives

The main objectives of this project are:

* Apply machine learning algorithms to hyperspectral data
* Compare classification performance of multiple models
* Evaluate models using confusion matrices and accuracy metrics
* Demonstrate a reproducible workflow for hyperspectral classification

---

## 🧠 Machine Learning Algorithms

Four supervised learning algorithms were implemented:

| Algorithm                        | Description                                                           |
| -------------------------------- | --------------------------------------------------------------------- |
| **Logistic Regression**          | Linear classification model commonly used as a baseline               |
| **Decision Tree**                | Tree-based classifier that partitions data into decision rules        |
| **Random Forest**                | Ensemble method combining multiple decision trees                     |
| **Support Vector Machine (SVM)** | Classifier that finds optimal separating hyperplanes in feature space |

These algorithms are widely used in **remote sensing classification problems**.

---

## 📊 Dataset

The dataset consists of **labeled hyperspectral samples** extracted from imagery.

Each sample includes:

* A **class label** (land cover category)
* Multiple **spectral reflectance bands**

Example structure:

| Class      | Band1 | Band2 | Band3 | ... | BandN |
| ---------- | ----- | ----- | ----- | --- | ----- |
| Soil       | 0.23  | 0.25  | 0.19  | ... | 0.14  |
| Vegetation | 0.05  | 0.08  | 0.11  | ... | 0.42  |

The spectral bands act as **predictor variables**, while the class label is the **target variable**.

---

## ⚙️ Methodology

### 1️⃣ Data Preparation

The dataset is loaded using **Pandas**, and features are separated from labels.

```python
y = df.iloc[:,0]
X = df.iloc[:,1:]
```

A **stratified train–test split** ensures that class distributions remain balanced.

```python
from sklearn.model_selection import train_test_split

X_train, X_test, y_train, y_test = train_test_split(
    X,
    y,
    test_size=0.30,
    stratify=y,
    random_state=42
)
```

---

### 2️⃣ Model Training

Each machine learning model is trained using the training dataset.

Example:

```python
from sklearn.ensemble import RandomForestClassifier

model = RandomForestClassifier()
model.fit(X_train, y_train)
```

---

### 3️⃣ Model Evaluation

Models are evaluated using:

* Accuracy
* Precision
* Recall
* F1 Score
* Confusion Matrix

```python
from sklearn.metrics import classification_report

predictions = model.predict(X_test)

print(classification_report(y_test, predictions))
```

---

## 📈 Results

The models produced different classification performances depending on their ability to capture spectral differences among land cover classes.

### Confusion Matrix

---

### Example Classification Output

---

## 🛠️ Technologies Used

This project uses the following Python tools:

* **Python**
* **NumPy**
* **Pandas**
* **Scikit-Learn**
* **Matplotlib**
* **Seaborn**

These libraries enable efficient **data processing, model training, and visualization**.

---

## 🌱 Applications

Hyperspectral classification has many important applications:

* Land cover mapping
* Precision agriculture
* Mineral exploration
* Environmental monitoring
* Forest health assessment

---

## 🚀 Future Work

Future improvements may include:

* Applying **dimensionality reduction (PCA)** for hyperspectral bands
* Implementing **deep learning models (CNN or U-Net)**
* Comparing **pixel-based vs object-based classification**
* Applying the workflow to **full hyperspectral imagery**

---

## 📂 Repository Structure

```
Hyperspectral-Classification
│
├── data
│   └── hyperspectral_training_samples.xlsx
│
├── notebooks
│   └── Pixel_based_HSI_classification_using_machine_learning.ipynb
│
├── results
│   ├── confusion_matrix.png
│   └── classified_map.png
│
└── README.md
```

---

## ▶️ How to Run the Project

### 1 Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/hyperspectral-pixel-classification-ml.git
```

### 2 Install dependencies

```bash
pip install pandas numpy scikit-learn matplotlib seaborn
```

### 3 Run the notebook

```bash
jupyter notebook
```

Open:

```
Pixel_based_HSI_classification_using_machine_learning.ipynb
```

---

## 👨‍🎓 Author

**Stephen Adebisi**

Graduate Student — Geography (GIS & Remote Sensing)

Research Interests:

* Remote sensing
* Geospatial machine learning
* Land cover mapping
* Environmental monitoring

---

## 📜 License

This project is released under the **MIT License**.
