Multi-Factor Stock Ranking Tool

A Python script that screens and ranks stocks using a quantitative multi-factor model. The program imports a list of stock tickers from an Excel workbook, retrieves market and fundamental data from Yahoo Finance, calculates factor scores, and exports the ranked results back into Excel.

Features
Reads stock tickers from an Excel workbook
Downloads historical price and company fundamentals using Yahoo Finance
Calculates:
Value factors (P/E and P/B)
Momentum (3-month and 6-month returns)
Quality (Return on Equity)
Risk (Debt-to-Equity)
Standardizes metrics using z-scores
Builds a weighted composite score
Ranks stocks from strongest to weakest
Automatically writes the results into a new Analysis worksheet
Factor Model

The composite score uses the following weights:

Factor	Weight
Value	25%
Momentum	25%
Quality	20%
Growth*	20%
Low Risk	10%

*Growth is currently approximated using 6-month price momentum.

Project Structure
project/
│
├── portfolio.xlsx      # Input workbook containing stock tickers
├── stock_analysis.py   # Main analysis script
└── README.md
Excel Workbook

The workbook should contain a sheet named Tickers with a column called:

Ticker

Example:

Ticker
AAPL
MSFT
NVDA
JPM

After the script runs, a new sheet called Analysis is created (or replaced) containing the rankings and calculated metrics.

Requirements

Install the required packages:

pip install pandas numpy yfinance openpyxl
How to Run
Update the EXCEL_PATH variable to point to your Excel workbook.
Ensure the workbook contains a Tickers sheet with a Ticker column.
Run:
python stock_analysis.py

The script will:

Load tickers from Excel
Download financial data
Calculate factor scores
Rank all stocks
Export the results to the Analysis worksheet
Technologies
Python
pandas
NumPy
yfinance
openpyxl
Future Improvements

Potential enhancements include:

Volatility-based risk factor
Earnings growth metrics
Free cash flow and profitability factors
Portfolio optimization
Backtesting framework
Interactive dashboard using Streamlit
Automated scheduled updates
Disclaimer

This project is intended for educational and research purposes only. It should not be considered financial advice or a recommendation to buy or sell securities.
