# Finance-Data-Analysis
Finance Transactions &amp; Customer Fraud Analysis  Analysed 50K banking transactions and 5K customers in Python (pandas, Jupyter): cleaned the data, merged datasets, and studied fraud, risk and segments. Found risk score is the key fraud signal (1.26% fraud rate), fixed a notebook bug that wiped out the fraud column, and flagged data quality issues.
# Finance_data_analysis

Finance Data Analysis | Data Analytics Project: Cleaned and analyzed 50,000 banking transactions and 5,000 customer records to uncover spending patterns, fraud signals and customer segment behavior using Python. Performed data cleaning, exploratory data analysis (EDA), a customer-transaction merge and a written report with actionable recommendations.

## Overview

This project demonstrates an end-to-end data analytics workflow using Python and Jupyter Notebook. The objective is to analyze transaction and customer data, identify fraud and risk indicators, understand customer segments, and present findings in a clear report for data-driven decision-making.

## Dataset

- finance_transactions.csv: 50,069 raw rows (50,000 after cleaning), Jan 2023 to Apr 2026
- customers1.csv: 5,000 customers with demographics, city/state, occupation, income and segment
- Transactions contain type, channel, merchant category, amount, status, risk score and fraud flag
- Used for data cleaning, exploration, merging and visualization

## Tools & Technologies

- Python (Pandas, NumPy, Matplotlib, Seaborn)
- Jupyter Notebook

## Project Steps

1. Load the transaction and customer datasets using Python.
2. Perform Exploratory Data Analysis (EDA).
3. Clean and preprocess the data.
4. Merge transactions with customers (many-to-one, 50,000 of 50,000 matched).
5. Run a second EDA on the merged table (fraud, segments, geography).
6. Generate a project report.

## Data Cleaning Summary

- Removed 69 duplicate rows and 1 empty column
- Standardized channel text into 7 clean channels and currency into INR
- Filled 24 missing fees with 0
- Flagged 9 negative amounts and converted them to absolute values
- Parsed dates (2023-01-01 to 2026-04-30)
- Customer file was already clean (unique IDs, no nulls)

## Key Findings

*Transactions*
- Total value: INR 45.6 crore (mean 9,111, median 5,002)
- Status: Success 85.7%, Failed 10.2%, Pending 4.1%
- Loan EMI and Transfer make up the largest share of value
- Channels, merchant categories and weekdays are almost evenly split
- Amount is driven mainly by transaction type

*Fraud and Risk*
- 630 fraud transactions out of 50,000 (1.26%)
- Risk score is the strongest fraud signal: mean 82.9 (fraud) vs 35.5 (non-fraud)
- Transaction amount barely differs between fraud and non-fraud
- Fraud rate differences by type, channel or state are small and likely noise

*Customers*
- Segments: Retail 54%, Premium 18%, SME 16%, Corporate 7%, Wealth 5%
- Segments track income (Retail median INR 4.5 lakh vs Wealth INR 13.6 lakh) but not spending, fraud or risk
- 1,017 customers (20%) have no transactions
- Top 10% of customers generate 30% of total spend

*Data Quality Flags*
- 521 customers marked Student are over 40; 443 marked Retired are under 45
- 165 customers joined before turning 18
- Column name typo: fisrt_name
- Patterns suggest the data is synthetic

## Results

- Identified spending, fraud and customer behavior patterns.
- Generated actionable business insights through data analysis.
- Presented findings through a detailed report with charts for better decision-making.

## Recommendations

1. Fix the is_fraud mapping and remove broken or duplicate notebook cells.
2. Add fraud analysis by segment, state and occupation with significance tests.
3. Build a customer-level table (transactions, spend, fraud count, average risk score).
4. Build a simple fraud model using risk score, amount and transaction type.
5. Run activation campaigns for the 20% inactive customers.
6. Resolve age and occupation inconsistencies before modelling.

## Known Notebook Notes

- The is_fraud Yes/No mapping cell returns NaN if run twice. Use Restart kernel and Run All, or the re-runnable form:
  python
  df['is_fraud'] = df['is_fraud'].replace({'Yes': 1, 'No': 0}).astype(int)
  
- Age is calculated with pd.Timestamp.today(), so results change with the run date.
- Make sure the customer filename in the notebook matches your local file.

## How to Run

1. Clone this repository.
2. Install the required Python libraries (pip install pandas numpy matplotlib seaborn jupyter).
3. Place the CSV files in the Dataset/ folder.
4. Open finance_analysis.ipynb in Jupyter Notebook.
5. Restart the kernel and run all cells for cleaning, EDA and the merge.
6. Review the project report (PDF).

## Project Structure


├── Dataset/
├── Python/
├── Report/
└── README.md


## Skills Demonstrated

- Data cleaning and preprocessing
- Exploratory Data Analysis (EDA)
- Data merging and validation
- Fraud and risk analysis
- Customer segmentation analysis
- Data visualization
- Business insight generation and reporting
