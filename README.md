<div align="center">

# 🌽 Hyperspectral Corn Analysis
### Predicting Vomitoxin Contamination in Corn with Hyperspectral Imaging

*A Hackathon project that turns 448 wavelengths of light into a food-safety decision in seconds.*

[![Python](https://img.shields.io/badge/Python-3.8%2B-3776AB.svg?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![PyTorch](https://img.shields.io/badge/PyTorch-2.0%2B-EE4C2C.svg?style=for-the-badge&logo=pytorch&logoColor=white)](https://pytorch.org/)
[![Streamlit](https://img.shields.io/badge/Streamlit-1.28%2B-FF4B4B.svg?style=for-the-badge&logo=streamlit&logoColor=white)](https://streamlit.io/)
[![License](https://img.shields.io/badge/License-MIT-2EA44F.svg?style=for-the-badge)](LICENSE)

[![GitHub followers](https://img.shields.io/github/followers/VishalLokhande7?style=social)](https://github.com/VishalLokhande7)

**Built by [Vishal Lokhande](https://github.com/VishalLokhande7)** as part of a team hackathon submission

</div>

<br>

## 🧭 Navigate

| | | |
|---|---|---|
| [💡 The Challenge](#-the-challenge) | [🔬 The Approach](#-the-approach) | [📊 The Results](#-the-results) |
| [🛠️ Under the Hood](#%EF%B8%8F-under-the-hood) | [🌍 Why It Matters](#-why-it-matters) | [🔭 What's Next](#-whats-next) |
| [👨‍💻 The Creator](#-the-creator) | [🤝 The Team](#-the-team) | [⭐ Support](#-support-this-project) |

---

## 💡 The Challenge

Vomitoxin (deoxynivalenol) contamination in corn is a serious agricultural and food-safety problem — but the standard way to detect it is **slow, expensive, and destructive**: send samples to a lab, wait days for results, and destroy the sample in the process.

At our hackathon, the team set out to answer one question:

> **Can hyperspectral imaging + machine learning replace the lab test with something faster, cheaper, and just as accurate?**

This repository is our answer.

---

## 🔬 The Approach

Instead of physically testing each sample, we capture its **hyperspectral signature** — how it reflects light across **448 spectral bands** — and feed that signature into trained ML models that have learned what contaminated vs. clean corn "looks like" spectrally.

```
  Hyperspectral Scan  →  Preprocessing  →  PCA (448 → ~15 dims)  →  ML Model  →  ppb Prediction
        📷                    🧹                  📉                  🤖              🎯
```

**Pipeline highlights:**
- 🧹 Cleaned and scaled raw spectral data (`StandardScaler`, outlier checks)
- 📉 Reduced 448 spectral bands down to a handful of components via **PCA**, retaining ~95% of the variance
- 🧠 Trained and benchmarked **six** different algorithms, from linear baselines to deep learning
- 🔍 Used **t-SNE** and feature-importance analysis to understand *which* wavelengths actually matter
- 📊 Shipped it all into a live **Streamlit dashboard** for real-time, interactive predictions

---

## 📊 The Results

| Model | Test R² | Verdict |
|---|---|---|
| 🥇 **Random Forest** | **0.9495** | **Best — production-ready** |
| 🥈 Decision Tree | 0.9433 | Strong, but more overfit-prone |
| 🥉 XGBoost | 0.9314 | Solid gradient-boosted baseline |
| ANN (PyTorch) | 0.6638 | Underfit — needs more data to shine |
| Linear Regression | 0.4726 | Too simple for this relationship |
| SVR | -0.0376 | Not competitive here |

<div align="center">

### 🏆 **Random Forest wins: 94.95% R² — accurate enough to act on**

*Tree-based ensembles dominate here because the relationship between spectral bands and toxin levels is highly non-linear — exactly what trees are built to capture.*

</div>

---

## ✨ Inside the Dashboard

<table>
<tr>
<td width="33%" valign="top">

**📊 Live Predictions**
Drop in a spectral sample and get an instant vomitoxin estimate — no lab, no waiting.

</td>
<td width="33%" valign="top">

**📈 Model Comparison**
See every model's accuracy side-by-side and inspect *why* Random Forest leads the pack.

</td>
<td width="33%" valign="top">

**🔍 Spectral Insights**
Visualize which of the 448 bands actually drive the prediction, via feature importance + t-SNE.

</td>
</tr>
</table>

---

## 🛠️ Under the Hood

<table>
<tr>
<td valign="top" width="25%">

**Data Science**
- Python
- Pandas
- NumPy
- Scikit-Learn

</td>
<td valign="top" width="25%">

**Modeling**
- XGBoost
- PyTorch (ANN)
- PCA / t-SNE

</td>
<td valign="top" width="25%">

**Visualization**
- Matplotlib
- Seaborn
- Plotly

</td>
<td valign="top" width="25%">

**Delivery**
- Streamlit
- Jupyter Notebook
- Git & GitHub

</td>
</tr>
</table>

---

## 🌍 Why It Matters

| Domain | Impact |
|---|---|
| 🚜 **Smart Farming** | Field-level contamination mapping & precision agriculture decisions |
| 🏭 **Grain Processing** | Real-time screening on the line instead of after-the-fact lab results |
| 🛡️ **Food Safety & Compliance** | Faster regulatory checks, batch certification, supply-chain transparency |
| 💰 **Cost Savings** | Cuts down on expensive, destructive laboratory testing at scale |

---

## 🔭 What's Next

- [ ] Grow the dataset past 1,000 samples for a more robust ANN
- [ ] Explore CNNs to capture spatial + spectral patterns together
- [ ] Extend to multi-toxin prediction (not just vomitoxin)
- [ ] Deploy the dashboard to the cloud (AWS/Azure)
- [ ] Build a companion mobile app
- [ ] Connect directly to a live hyperspectral camera feed

---

## 👨‍💻 The Creator

<div align="center">
<table>
<tr>
<td align="center" width="100%">

### Vishal Lokhande

🎓 B.Tech Computer Engineering Student
💻 Full-Stack Development · Data Science · Machine Learning
🧠 Data Structures & Algorithms Enthusiast
🌱 *Passionate about building AI-powered solutions for real-world problems*

[![GitHub](https://img.shields.io/badge/GitHub-VishalLokhande7-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/VishalLokhande7)

</td>
</tr>
</table>
</div>

> *"Turning imagination into reality through code."*

---

## 🤝 The Team

This was a **team hackathon build** — Hyperspectral Corn Analysis wouldn't exist without everyone's contribution. Here's specifically what **Vishal** brought to the table:

- 🤖 Machine learning model training & evaluation
- 🧹 Data preprocessing & feature engineering
- 📉 PCA-based dimensionality reduction
- ⚖️ Model performance comparison & analysis
- 📝 Project documentation & GitHub management
- 📊 Result visualization & interpretation
- 🎤 Project presentation support

---

## ⭐ Support This Project

If **Hyperspectral Corn Analysis** was useful, interesting, or just made you appreciate corn a little more — drop a ⭐ on the repo!

<div align="center">

**Connect with Vishal Lokhande**

[![GitHub](https://img.shields.io/badge/GitHub-Follow-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/VishalLokhande7)

</div>
