# 🚀 DecodeLabs Data Science — Project 1
## Advanced EDA & Feature Engineering

![Python](https://img.shields.io/badge/Python-3.12-blue)
![Pandas](https://img.shields.io/badge/Pandas-2.0-green)
![Pandera](https://img.shields.io/badge/Pandera-validated-orange)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

---

## 📌 Project Overview
This project was completed as part of the **DecodeLabs Industrial Training Program (Batch 2026)** under the Data Science track.

The goal is to transform a raw, chaotic online sales dataset into a mathematically clean, ML-ready dataset using the **Input-Process-Output (IPO) Architecture**.

---

## 📂 Repository Structure
DecodeLabs-DS-Project1/
│
├── data/
│   ├── Dataset_for_Data_Analytics.csv       # Original raw dataset
│   └── cleaned_dataset_project1.csv         # Final cleaned dataset
│
├── notebooks/
│   └── DecodeLabs_Project1_Advanced_EDA_Feature_Engineering.ipynb
│
├── requirements.txt
└── README.md

---

## 📊 Dataset
- **Source:** DecodeLabs Industrial Training Kit
- **Size:** 1200 rows × 14 columns
- **Domain:** Online Sales Orders

---

## ⚙️ What Was Done

### MODULE 1 — INPUT: Securing Data Fidelity
- Identified missing values using the **Missing Data Decision Matrix**
- `CouponCode` (25.75% missing) → filled with `NO_COUPON` using domain logic
- Detected outliers using **Interquartile Range (IQR)**
- Neutralized outliers using **Winsorization** (`numpy.clip`) — zero rows deleted

### MODULE 2 — PROCESS: Vectorized Computation Engine
- Engineered **6 new predictive features**:
  - `RevenuePerItem` — revenue efficiency per cart slot
  - `IsSuccessful` — binary delivery outcome flag
  - `CouponApplied` — promotion usage flag
  - `OrderMonth` — seasonality signal
  - `OrderQuarter` — quarterly trend signal
  - `PriceTier` — product price band category
- Applied **One-Hot Encoding** on all categorical columns
- Checked and resolved **multicollinearity** (threshold: |r| > 0.80)
- All operations fully **vectorized** — zero Python for loops

### MODULE 3 — OUTPUT: Structural Contracts
- Validated final dataset using **Pandera** runtime schema assertions
- Exported final ML-ready dataset as CSV

---

## 📈 Results
| Metric | Before | After |
|---|---|---|
| Shape | 1200 × 14 | 1200 × 30 |
| Missing Values | 309 | 0 |
| Outliers | Present | Neutralized |
| ML Ready | ❌ | ✅ |

---

## 🛠️ Technologies Used
- Python 3.12
- Pandas, NumPy
- Matplotlib, Seaborn
- Pandera
- Google Colab
