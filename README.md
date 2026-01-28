# 🧠 SKAB Industrial Anomaly Detection (Valve 1)

Anomaly detection on industrial time-series sensor data from **SKAB (Skoltech Anomaly Benchmark)** using:
**IQR heuristics**, **KMeans/DBSCAN**, and **Isolation Forest** + feature engineering.

---

## 📂 Dataset
- File: `skab_valve_1.csv` (SKAB, Valve 1)
- Main signal: `Thermocouple`
- Ground-truth label: `anomaly` (`1` = anomaly)

> Put the dataset here: `data/skab_valve_1.csv`

---

## ✅ What’s inside
- Data loading + basic cleaning
- Missing values check + basic stats
- Visualization of all sensors
- Feature engineering for time-series (lags, rolling mean/std)
- Methods:
  - **IQR** on raw signal + on Δ-signal
  - **KMeans (k=2)**
  - **DBSCAN** (eps tuned ~ `3.35`)
  - **Isolation Forest** (best config `contamination=0.1`)
- Evaluation:
  - Confusion Matrix + F1 (anomaly) + Accuracy

---

## 📊 Results Summary
| Method | F1 (anomaly) | Accuracy |
|--------|---------------|----------|
| IQR | 0.00 | 0.63 |
| KMeans (k=2) | 0.13 | 0.47 |
| DBSCAN (eps≈3.35) | 0.07 | 0.62 |
| Isolation Forest (cont=0.1) | 0.05 | 0.55 |

**Conclusion:** Feature Engineering + **Isolation Forest** gives the best practical visual match for industrial trends.

---

## ⚙️ Reproducibility
- `random_state=42` is used where applicable
- Code follows a clean notebook structure with markdown explanations
- No runtime errors (reproducible workflow)

---

## 🛠 Requirements
- Python 3.10+ (recommended)
- Common libraries:
  - `pandas`, `numpy`, `matplotlib`
  - `scikit-learn`

Install:
```bash
pip install -r requirements.txt
