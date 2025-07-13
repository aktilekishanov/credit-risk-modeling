# Credit Risk Modeling Course

Credit Risk Modeling Project
Implemented as part of the 365 Careers Data Science Case Study Course on Credit Risk Modeling, this comprehensive project covers the full credit risk modeling pipeline. Certificate of successful completion of the course -> [Here](https://drive.google.com/file/d/1FjMDLmfbjUBfmEpRC9NLy3EvwZgU0kw5/view?usp=sharing)

## 📋 Project Overview

This project demonstrates the complete credit risk modeling workflow, from data preparation to model deployment and monitoring. It includes:

- **Data Preparation**: Feature engineering, missing value handling, and data preprocessing
- **PD Model**: Probability of Default prediction using logistic regression
- **LGD Model**: Two-stage Loss Given Default model (logistic + linear regression)
- **EAD Model**: Exposure at Default prediction using linear regression
- **Expected Loss Calculation**: Combining PD, LGD, and EAD models
- **Model Monitoring**: Population Stability Index (PSI) analysis

## 🏗️ Project Structure

```
credit_risk_modeling_course/
├── 01_Data_Preparation.ipynb          # Data preprocessing and feature engineering
├── 02_PD_Model.ipynb                  # Probability of Default model
├── 03_Monitoring.ipynb                # Model monitoring and PSI analysis
├── 04_Calculating_Expected_Loss.ipynb # LGD, EAD, and Expected Loss models
├── data/
│   ├── raw/                          # Original loan data files
│   ├── processed/                    # Preprocessed data files
│   ├── pd_model_outputs/            # PD model outputs and scorecard
│   ├── calculating_el_outputs/      # LGD and EAD model outputs
│   └── monitoring_outputs/          # Monitoring results
└── from_course/                     # Original course materials with comments
```

## 🚀 Getting Started

### Prerequisites

- Python 3.8+
- Jupyter Notebook or JupyterLab
- Required Python packages (see requirements.txt)
- 2007-2014 dataset: https://www.dropbox.com/scl/fi/rzqaawjqwt4qe3rmnnxiw/loan_data_2007_2014.csv?rlkey=a5y6ojznit1ozu8fwt0m7w11w&e=1&dl=0
- 2015 dataset: https://www.dropbox.com/scl/fi/kywjooafv2jclu6epwe1o/loan_data_2015.csv?rlkey=0d6d9p05dhw2ln8ejacd4mqsp&e=1&dl=0

### Installation

1. Clone the repository:
```bash
git clone https://github.com/aktilekishanov/credit_risk_modeling.git
cd credit_risk_modeling
```

2. Install required packages:
```bash
pip install -r requirements.txt
```

3. Download the data files:
   - Place the loan data files in the `data/raw/` directory
   - The project expects loan data from LendingClub (2007-2015)

### Running the Notebooks

Execute the notebooks in the following order:

1. **01_Data_Preparation.ipynb** - Prepare and preprocess the data
2. **02_PD_Model.ipynb** - Build and validate the PD model
3. **03_Monitoring.ipynb** - Monitor model performance and stability
4. **04_Calculating_Expected_Loss.ipynb** - Build LGD, EAD, and calculate EL

## 📊 Models Overview

### 1. Probability of Default (PD) Model
- **Algorithm**: Logistic Regression
- **Features**: 85 engineered features including:
  - Loan characteristics (grade, term, purpose)
  - Borrower information (income, employment, credit history)
  - Geographic and demographic factors
- **Output**: Probability of default for each loan

### 2. Loss Given Default (LGD) Model
- **Stage 1**: Logistic Regression (recovery rate > 0 vs = 0)
- **Stage 2**: Linear Regression (actual recovery rate for positive recoveries)
- **Output**: Expected recovery rate (1 - LGD)

### 3. Exposure at Default (EAD) Model
- **Algorithm**: Linear Regression
- **Target**: Credit Conversion Factor (CCF)
- **Output**: Expected exposure at default

### 4. Expected Loss (EL) Calculation
- **Formula**: EL = PD × LGD × EAD
- **Output**: Expected loss amount for each loan

## 📈 Model Performance

### PD Model Metrics
- **AUROC**: ~0.75
- **Accuracy**: ~85%
- **Confusion Matrix**: Balanced performance across classes

### LGD Model Performance
- **Stage 1 AUROC**: ~0.70
- **Stage 2 R²**: ~0.25
- **Combined Performance**: Realistic recovery rate predictions

### EAD Model Performance
- **R²**: ~0.30
- **Correlation**: Moderate correlation with actual CCF

## 🔍 Model Monitoring

The project includes comprehensive model monitoring using:

- **Population Stability Index (PSI)**: Detects distribution shifts
- **Feature Stability Analysis**: Monitors individual feature changes
- **Score Distribution Analysis**: Tracks score stability over time

## 📁 Data Requirements

### Input Data Format
The models expect loan data with the following key fields:
- `loan_status`: Target variable (default/non-default)
- `funded_amnt`: Original loan amount
- `total_rec_prncp`: Total principal received
- `recoveries`: Recovery amounts
- Various borrower and loan characteristics

### Data Sources
- LendingClub loan data (2007-2015)
- Publicly available credit risk datasets

## 🛠️ Technical Details

### Key Libraries Used
- **pandas**: Data manipulation and analysis
- **numpy**: Numerical computations
- **scikit-learn**: Machine learning models
- **matplotlib/seaborn**: Data visualization
- **statsmodels**: Statistical modeling

### Model Validation
- Train/Test split (80/20)
- Cross-validation for hyperparameter tuning
- Out-of-time validation for temporal stability

## 📝 Notes

### Known Issues
- Some pandas SettingWithCopyWarning messages (non-critical)
- Large data files excluded from repository (see .gitignore)
- Model files (.sav) excluded due to size

### Best Practices Implemented
- Proper train/test splitting
- Feature engineering with domain knowledge
- Model interpretability considerations
- Comprehensive documentation

## 📄 License

This project is for educational purposes. Please ensure compliance with data usage agreements when using real credit data.

## 👨‍💻 Author

**Aktilek Ishanov**
- Credit Risk Modeling Course Project

## 🙏 Acknowledgments

- Course materials and guidance
- LendingClub for providing the dataset
- Open-source community for tools and libraries

---

**Note**: This project is for educational purposes and should not be used for actual credit risk assessment without proper validation and regulatory compliance. 
