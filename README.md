# Car Attack Detection Models

This project implements machine learning models for detecting various types of attacks on car systems using multiple datasets including DoS, Fuzzy, Gear, and RPM data.

## Project Structure

```
├── Cleaning the datasets.ipynb           # Data preprocessing notebook
├── Cars Attack detection Models.ipynb    # Original 4 ML models notebook
├── more models for detection.ipynb       # Extended 10 ML models notebook
├── DoS_dataset.csv                       # Denial of Service attack data
├── Fuzzy_dataset.csv                     # Fuzzy attack data
├── gear_dataset.csv                      # Gear-related data
├── RPM_dataset.csv                       # RPM sensor data
├── normal_run_data.txt                   # Normal operation data
├── requirements.txt                      # Python dependencies
└── car_attack_detection_env/             # Virtual environment
```

## Setup Instructions

### 1. Clone the Repository
```bash
git clone <repository-url>
cd car-attack-detection
```

### 2. Create and Activate Virtual Environment
```bash
# Create virtual environment
python -m venv car_attack_detection_env

# Activate on Windows
.\car_attack_detection_env\Scripts\Activate.ps1

# Activate on Linux/Mac
source car_attack_detection_env/bin/activate
```

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

### 4. Launch Jupyter Notebook
```bash
jupyter notebook
```

## Models Implemented

### Original Models (`Cars Attack detection Models.ipynb`)

| # | Model | Type |
|---|-------|------|
| 1 | **AdaBoost** | Ensemble (with GridSearchCV tuning) |
| 2 | **Naive Bayes (NBC)** | Probabilistic classifier |
| 3 | **Decision Tree (CDT)** | Tree-based classifier |
| 4 | **XGBoost** | Gradient boosting |

### Extended Models (`more models for detection.ipynb`)

All 4 original models above **plus** 6 new models:

| # | Model | Type |
|---|-------|------|
| 5 | **SVM (RBF)** | Support Vector Machine with RBF kernel |
| 6 | **Random Forest** | Ensemble of decision trees |
| 7 | **Logistic Regression** | Linear classifier |
| 8 | **KNN** | K-Nearest Neighbors (distance-based) |
| 9 | **Neural Network (MLP)** | Multi-Layer Perceptron (128→64 hidden layers) |
| 10 | **Extra Trees** | Extremely Randomized Trees |

### Results Summary

| Rank | Model | Accuracy | Training Time |
|------|-------|----------|---------------|
| 🥇 | Extra Trees | 100.00% | 6.75s |
| 🥈 | XGBoost | 100.00% | 7.33s |
| 🥉 | Random Forest | 100.00% | 9.34s |
| #4 | AdaBoost | 100.00% | 103.34s |
| #5 | SVM (RBF) | 99.99% | 30.83s |
| #6 | Neural Network (MLP) | 99.99% | 65.10s |
| #7 | KNN | 99.98% | 2.17s |
| #8 | Decision Tree | 99.94% | 1.23s |
| #9 | Naive Bayes | 99.03% | 0.16s |
| #10 | Logistic Regression | 98.34% | 4.06s |

## 📥 Dataset

The dataset file `final_train_ready_scrubbed.csv` is **not included** in this repository due to its size (~55MB).

**To run the notebooks:**
1. Download the **Car Hacking Dataset** from [Kaggle](https://www.kaggle.com/) or your original source
2. Run `Cleaning the datasets.ipynb` to generate the cleaned dataset, OR place the pre-processed `final_train_ready_scrubbed.csv` in the root project folder
3. Then run the model notebooks in order

## Datasets

- **DoS Dataset**: Contains Denial of Service attack patterns
- **Fuzzy Dataset**: Fuzzy logic attack data
- **Gear Dataset**: Gear manipulation attack data
- **RPM Dataset**: Engine RPM-based attack data
- **Normal Run Data**: Baseline normal operation data

## Key Features

- **Data Preprocessing**: Comprehensive data cleaning and feature engineering
- **10 ML Models**: Comprehensive comparison across diverse algorithm families
- **Hyperparameter Tuning**: GridSearchCV with 5-fold CV for AdaBoost
- **Feature Scaling**: StandardScaler applied to models that need it (SVM, KNN, MLP, Logistic Regression)
- **Visualization**: Confusion matrices, accuracy bar charts, F1-score comparison, precision vs recall plots
- **Cross-Validation**: 5-fold CV for reliable model evaluation
- **Overfitting Detection**: Train vs test accuracy gap analysis
- **Per-Class Analysis**: Heatmap showing accuracy for each attack type per model

## Usage

1. Start with `Cleaning the datasets.ipynb` to preprocess your data
2. Run `Cars Attack detection Models.ipynb` for the original 4-model comparison
3. Run `more models for detection.ipynb` for the full 10-model comparison (includes all original models + 6 new ones)

## Results

The project provides:
- Full ranking of 10 models sorted by accuracy and speed
- Confusion matrices for each model
- Training vs. test performance analysis
- Overfitting detection for all models
- Per-class accuracy heatmap across all models and attack types
- Visual comparison charts (accuracy, F1-score, training time, precision vs recall)

## Requirements

- Python 3.8+
- See `requirements.txt` for complete package list

## Contributing

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details.