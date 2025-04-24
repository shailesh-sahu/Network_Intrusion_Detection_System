
# 🔐 Network Intrusion Detection System (NIDS) Using Stacking Ensemble

This project implements a Network Intrusion Detection System (NIDS) leveraging a **stacking ensemble** approach trained on the **UNSW-NB15** and **NSL-KDD99** datasets. The ensemble combines multiple machine learning models to improve detection performance across diverse types of attacks.

## 📊 Datasets Used

- **[UNSW-NB15](https://research.unsw.edu.au/projects/unsw-nb15-dataset)**  
  A modern network intrusion dataset that includes a wide range of synthetic attack types generated in a controlled environment.

- **[NSL-KDD99](https://www.unb.ca/cic/datasets/nsl.html)**  
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
- Standardized features using `StandardScaler`.
- Aligned features between training and testing sets.
- Missing values handled using `SimpleImputer` (mean strategy).

## 🚀 Training and Evaluation

The stacking model was trained on the **UNSW-NB15** dataset. It was evaluated using:

- Accuracy
- Precision
- Recall
- F1-Score
- Confusion Matrix
- ROC Curve and AUC

### ✅ Performance (on UNSW-NB15 test set)
- **Accuracy**: 99.84%
- **Precision**: 99.84%
- **Recall**: 99.84%
- **F1-Score**: 99.84%

> 📌 Note: NSL-KDD99 was used for comparative experiments and model generalization, though results shown above are from UNSW-NB15.

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
└── datasets/                 # Contains UNSW-NB15 and NSL-KDD CSV files (not included)
```

## 🧪 Future Work

- Extend support for real-time packet detection.
- Integrate deep learning (e.g., LSTM, Autoencoders).
- Perform cross-evaluation between UNSW-NB15 and NSL-KDD.

## 👨‍💻 Author

**Shailesh Kumar Sahu**  
Final Year B.Tech (IT), DTU  
GitHub: [@shaileshkrsahu](https://github.com/shailesh-sahu)
