
# 🎓 Campus Placement Prediction Analysis

A data analytics and machine learning project that predicts whether a student will be placed or not placed based on academic and personal attributes using KNIME Analytics Platform.

The project performs data preprocessing, visualization, and predictive modeling using algorithms such as **Random Forest**, **Decision Tree**, and **Tree Ensemble**. This workflow helps institutions analyze placement trends and student performance factors.
<img width="1919" height="1079" alt="Screenshot 2026-03-14 001540" src="https://github.com/user-attachments/assets/584b1873-c6fb-4776-842f-73bf7f1cfb3f" />

---

## 📌 Project Overview

Campus placement prediction helps institutions:
* Identify students likely to get placed
* Understand factors affecting placements
* Improve training programs
* Provide targeted guidance to students

This project builds a machine learning pipeline in KNIME to analyze placement data and generate predictions.

---

## 🛠 Tools & Technologies

| Tool | Purpose |
| :--- | :--- |
| **KNIME Analytics Platform** | Data processing & ML workflow |
| **Machine Learning** | Prediction models |
| **Data Visualization** | Bar Chart, Pie Chart, ROC Curve |
| **CSV Dataset** | Student placement dataset |

---

## 📂 Workflow Architecture

The workflow consists of the following stages:

`CSV Reader` ➔ `Missing Value Handling` ➔ `Column Filtering` ➔ `Table Partitioning` ➔ `One-to-Many Encoding` ➔ `Machine Learning Models` ➔ `Prediction` ➔ `Model Evaluation` ➔ `Data Visualization`

---

## ⚙️ KNIME Workflow Nodes Explanation

### 1️⃣ CSV Reader
Loads the placement dataset.
* **Example dataset columns:** `gender`, `ssc_p`, `hsc_p`, `degree_p`, `workex`, `etest_p`, `mba_p`, `specialisation`, `status`
* **Target variable:** `status` ➔ Placed / NotPlaced

### 2️⃣ Missing Value Node
Handles missing values in the dataset. Common techniques used:
* Mean replacement
* Median replacement
* Most frequent value

### 3️⃣ Column Filter
Removes unnecessary columns to improve model performance.
* **Remove:** `student_id` 
* **Keep:** academic performance columns

### 4️⃣ Table Partitioner
Splits the dataset to evaluate model performance:
* **Training Data:** 80%
* **Testing Data:** 20%

### 5️⃣ One-to-Many Encoding
Converts categorical variables into numeric format.
* **Gender:** Male ➔ `1`, Female ➔ `0` 
* **Specialisation:** Marketing ➔ `[1,0]`, Finance ➔ `[0,1]`

---

## 🤖 Machine Learning Models

### 1️⃣ Random Forest
Builds multiple decision trees and combines their results.
* **Advantages:** High accuracy, handles large datasets, reduces overfitting.
* **Workflow Nodes:** `Random Forest Learner` ➔ `Random Forest Predictor`

### 2️⃣ Decision Tree
Simple interpretable model that splits data based on conditions.
* **Example:** `IF mba_p > 60 THEN Placed ELSE NotPlaced`
* **Nodes Used:** `Decision Tree Learner` ➔ `Decision Tree Predictor`

### 3️⃣ Tree Ensemble
Combination of multiple decision trees to improve prediction accuracy.
* **Nodes Used:** `Tree Ensemble Learner` ➔ `Tree Ensemble Predictor`

---

## 📊 Model Evaluation

### Scorer Node
Evaluates model performance using Accuracy, Precision, Recall, and F1 Score.

**Example Confusion Matrix:**

| Predicted / Actual | Actual Placed | Actual NotPlaced |
| :--- | :--- | :--- |
| **Predicted Placed** | 927 | 45 |
| **Predicted NotPlaced** | 30 | 260 |

### ROC Curve
Used to evaluate classifier performance. A higher AUC (Area Under Curve) score indicates a better model.

---

## 📈 Data Visualization

The workflow includes multiple visualization nodes:

* 📊 **Bar Chart:** Shows distribution of placed vs not placed students. *(Example: Placed ➔ 927, NotPlaced ➔ 260)*
* 🥧 **Pie Chart:** Displays placement ratio. *(Example: Placed ➔ 78%, NotPlaced ➔ 22%)*
* 📦 **Box Plot:** Shows the relationship between Academic Scores vs Placement Status.

---

## 📊 Sample Workflow

Your KNIME workflow structure:

```text
CSV Reader 
  ↓ 
Missing Value 
  ↓ 
Column Filter 
  ↓ 
Table Partitioner 
  ↓ 
One-to-Many 
  ↓ 
Random Forest Learner 
  ↓ 
Random Forest Predictor 
  ↓ 
Scorer 
  ↓ 
Bar Chart 

📁 Project Structure
Campus-Placement-Prediction
│
├── dataset
│   └── placement_data.csv
│
├── knime_workflow
│   └── placement_prediction.knwf
│
├── screenshots
│   ├── workflow.png
│   └── results.png
│
└── README.md 

🚀 How to Run the Project
 * Install KNIME Analytics Platform: Download it from https://www.knime.com/downloads
 * Open KNIME.
 * Import the workflow: Go to File ➔ Import KNIME Workflow
 * Load Dataset: Select your dataset inside the CSV Reader node.
 * Execute Nodes: Right-click each node and select Execute, or execute the entire workflow at once.
 * View Results:
   * Scorer ➔ Model Accuracy
   * Bar Chart ➔ Placement Distribution
   * ROC Curve ➔ Model Performance
📊 Results
Example Output:
| Model | Accuracy |
|---|---|
| Decision Tree | 82% |
| Random Forest | 89% |
| Tree Ensemble | 91% |
🏆 Best model: Tree Ensemble
🎯 Applications
This project can be used by:
 * Universities
 * Placement Cells
 * Career Guidance Teams
 * Training Institutes
Use Cases: Predict placement chances, identify weak areas, improve training programs.
🔮 Future Improvements
Possible enhancements:
 * Deep Learning models
 * Web dashboard integration
 * Real-time prediction system
 * Student recommendation system
 * Integration with university databases
👨‍💻 Author
Kunal Ekare
 * Project: Campus Placement Prediction Analysis
 * Tools Used: KNIME, Machine Learning, Data Visualization


