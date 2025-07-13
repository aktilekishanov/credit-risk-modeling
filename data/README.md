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
https://www.dropbox.com/scl/fi/rzqaawjqwt4qe3rmnnxiw/loan_data_2007_2014.csv?rlkey=a5y6ojznit1ozu8fwt0m7w11w&e=1&dl=0

- **loan_data_2015.csv**: Test dataset for monitoring
https://www.dropbox.com/scl/fi/kywjooafv2jclu6epwe1o/loan_data_2015.csv?rlkey=0d6d9p05dhw2ln8ejacd4mqsp&e=1&dl=0

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