# Vehicle Performance Analysis using Fuzzy Logic

![Python](https://img.shields.io/badge/Python-3.x-blue?style=for-the-badge&logo=python)
![Library](https://img.shields.io/badge/Library-Scikit--Fuzzy-orange?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed-green?style=for-the-badge)

## 📌 Project Overview

This project implements a **Fuzzy Logic System** to evaluate the performance of vehicles manufactured between **2019 and 2020**. By analyzing technical specifications and market data, the system outputs a performance score (Low, Medium, or High).

The system compares two fuzzy inference methods:
1.  **Mamdani Method:** Uses `scikit-fuzzy` for centroid defuzzification.
2.  **Sugeno Method:** Uses a custom implementation with linear output functions.

## 👥 Team Members

* **Rafid Al Afif Khumaini** - 103012300200
* **Faisal Surya Saputra** - 103012330152

## ⚙️ How It Works

The system processes data from `Car details v3.csv`, cleans it, and applies fuzzy logic rules based on three antecedent variables to determine one consequent variable.

### Input Variables (Antecedents)
1.  **Engine Capacity (cc):** Range [750 - 5200]
    * *Membership:* Small, Medium, Large
2.  **Fuel Efficiency (Mileage kmpl):** Range [5 - 35]
    * *Membership:* Low, Medium, High
3.  **Selling Price (INR):** Range [200,000 - 7,500,000]
    * *Membership:* Low, Medium, High

### Output Variable (Consequent)
* **Performance Score:** Range [0 - 100]
    * *Membership:* Low, Medium, High

## 🛠️ Prerequisites

Make sure you have the following Python libraries installed:

```bash
pip install numpy pandas matplotlib seaborn scikit-fuzzy scikit-learn
```

🚀 Features
Data Preprocessing: Filters data for 2019-2020 models, handles missing values, and cleans unit strings (e.g., removing 'CC' and 'kmpl').
- Fuzzy Logic Implementation:
   - Defines Triangular Membership Functions (Trimf).
   - Implements 27 distinct fuzzy rules.
- Comparison: Calculates both Mamdani and Sugeno scores for every vehicle in the dataset.
- Visualization:
  - 3D Surface plots for Sugeno output.
  - 2D plots for Membership Functions.
- Evaluation: Computes Accuracy and F1-Score to compare the Sugeno approximation against the Mamdani baseline.
📊 Methodology (Rules Example)
The logic relies on expert rules, for example:

- IF Engine is Small AND Mileage is High AND Price is Low THEN Performance is Medium.

- IF Engine is Medium AND Mileage is Medium AND Price is Medium THEN Performance is High.

📈 Results
The script outputs a comprehensive table sorting vehicles by their calculated fuzzy scores and classifies them into:
- Buruk (Poor)
- Cukup (Fair)
- Bagus (Good)
It also generates visualizations to help understand the decision boundary of the fuzzy system.
