# Data Directory

This directory contains all data files for the credit risk modeling project.

## Directory Structure

```
data/
├── raw/                          # Original loan data files
│   ├── loan_data_2007_2014.csv  # LendingClub data 2007-2014
│   └── loan_data_2015.csv       # LendingClub data 2015
├── processed/                    # Preprocessed data files
│   ├── loan_data_2007_2014_preprocessed.csv
│   ├── loan_data_inputs_train.csv
│   ├── loan_data_inputs_test.csv
│   ├── loan_data_targets_train.csv
│   └── loan_data_targets_test.csv
├── pd_model_outputs/            # PD model outputs
│   ├── pd_model.sav
│   ├── df_scorecard.csv
│   └── inputs_train_with_ref_cat.csv
├── calculating_el_outputs/      # LGD and EAD model outputs
│   ├── lgd_model_stage_1.sav
│   ├── lgd_model_stage_2.sav
│   └── loan_data_defaults.csv
└── monitoring_outputs/          # Monitoring results
```

## Data Requirements

### Raw Data Files
- **loan_data_2007_2014.csv**: Main training dataset
- **loan_data_2015.csv**: Test dataset for monitoring

### Key Variables Required
- `loan_status`: Target variable (default/non-default)
- `funded_amnt`: Original loan amount
- `total_rec_prncp`: Total principal received
- `recoveries`: Recovery amounts
- Borrower characteristics (income, employment, credit history)
- Loan characteristics (grade, term, purpose, etc.)

## Data Sources
- LendingClub loan data (2007-2015)
- Publicly available credit risk datasets

## Note
Large data files are excluded from the repository due to size limitations. Please download the required data files and place them in the appropriate directories before running the notebooks. 