
# Personal finance scripts

Collection of small scripts for personal finance.
Configure them by modifying their source code.
For DCA_backtesting.sh and report.sh, use 'setup_env.sh' to setup a local python environment before executing.

## budget.py

Plots pie charts and breaks down the monthly spending percentages for a budget.

## rent_or_buy.py

Compares buying a home with a mortgage vs renting.
The first plot shows the monthly cost of each option over time.
The second plot shows the extra value of an investment portfolio, where every year the option with the lower cost is investing the difference (the highest cost minus its own).
This assumes all options are always affordable.

## DCA_backtesting.sh

Backtests Dollar Costs Averaging a constant inflation-adjusted amount over time (plus a 'hold' time with no contributions) into a portfolio given historical data.
Price and inflation data are located in the price_data folder in csv format.
Price data must not be inflation adjusted.

## investment_needs.py

Shows the required monthly investment to achieve a certain portfolio value depending on the time and the annual returns.

## ibkr_report.sh

Reads IBKR statements in CSV format and creates several simpler, abridged CSV files used in other scripts.
The script assumes that the CSVs contain all possible sections and dont overlap each other, as well as the base currency not changing.
Place them in the IBKR folder.

## download_price_data.sh

Downloads price data in CSV format from yahoo, to be used in other scripts.
Have a comma-separated yahoo_symbols.csv file with 'symbol' and 'yahoo' columns to establish equivalences between the symbol to be saved and its equivalent in yahoo.

## report.sh

Takes CSV files with transfers, trade and symbols data (generated by previous scripts), downloads price data using download_price_data.sh and calculates the inflation-adjusted portfolio value over time and IRR (internal rate of return).
For trade data in other currencies, it uses the convert_price_data.py script.
A 'currency_conversion.csv' file is needed in the 'price_data' directory, containing 'symbol' and 'currency' columns for prices listed in currencies other than your base currency.
Additionally, a separate CSV file for each currency is required, specifying its exchange rate to your base currency.
You can use the download_price_data.sh to get currency exchanges from yahoo.
