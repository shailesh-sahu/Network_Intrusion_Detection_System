
# 🔐 Network Intrusion Detection System (NIDS) Using Stacking Ensemble

This project implements a Network Intrusion Detection System (NIDS) leveraging a **stacking ensemble** approach trained on the **UNSW-NB15** and **KDD99** datasets. The ensemble combines multiple machine learning models to improve detection performance across diverse types of attacks.

## 📊 Datasets Used

- **[UNSW-NB15](https://research.unsw.edu.au/projects/unsw-nb15-dataset)**  
  A modern network intrusion dataset that includes a wide range of synthetic attack types generated in a controlled environment.

- **[KDD99](https://kdd.ics.uci.edu/databases/kddcup99/kddcup99.html)**  
  An improved version of the KDD'99 dataset that addresses issues like redundant records and imbalance.

## 🧠 Model Architecture

This project uses a **StackingClassifier** from `scikit-learn`, composed of the following base learners:

- 🌲 `RandomForestClassifier`
- 👥 `KNeighborsClassifier`
- 💻 `SVC (Support Vector Classifier)`

The final meta-model is:

- ➕ `LogisticRegression`

## 🔧 Preprocessing Steps

- Handled categorical variables using `pd.get_dummies`.
- Feature selection upto 30 using chi-square test.
- Standardized features using `StandardScaler`.
- Aligned features between training and testing sets.
- Missing values handled using `SimpleImputer` (mean strategy).

## 🚀 Training and Evaluation

The stacking model was trained on the **UNSW-NB15 & KD99** dataset. It was evaluated using:

- Accuracy
- Precision
- Recall
- F1-Score
- Confusion Matrix
- ROC Curve and AUC
### ✅ Performance (on KD99 test set)
- **Accuracy**: 99.96%

### ✅ Performance (on UNSW-NB15 test set)
- **Accuracy**: 99.82%


## 📈 Visualization

- 📊 **Confusion Matrix**
- 📉 **ROC Curve**

## 🛠️ Requirements

Install dependencies using:

```bash
pip install pandas numpy scikit-learn matplotlib seaborn
```

## 📁 File Structure

```
├── NIDS_base_meta.ipynb      # Main notebook with model training and evaluation
├── README.md                 # Project documentation
└── datasets/                 # Contains UNSW-NB15 and NSL-KDD CSV files (download from above given links)
```

## 🧪 Future Work

- Extend support for real-time packet detection.
- Integrate deep learning (e.g., LSTM, Autoencoders).
- Perform cross-evaluation between UNSW-NB15 and NSL-KDD.

## 👨‍💻 Author

**Shailesh Kumar Sahu**  
Final Year B.Tech (IT), DTU  
GitHub: [@shaileshkrsahu](https://github.com/shailesh-sahu)
