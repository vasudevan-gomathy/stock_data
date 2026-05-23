# Stock Pricing and Valuation Analysis

## Project Overview
This project uses Python to process a financial dataset containing stock names, trade dates, and closing prices to calculate option values and forward contract prices.

## Repository Contents
* `README.md`: Summary of questions and final answers.
* `Valuation_Control_Workbook.ipynb`: Jupyter notebook containing the full Python code.
* `Excel - EX.xlsx`: The raw data source file.

---

## Questions & Final Answers

### Question 1
How many unique underliers traded as of 30th April according to this dataset? List them. Describe briefly how you extracted the underliers.
* **Answer:** **99 unique stocks** traded as of April 30, 2021.
* **Method:** Filtered the data up to `2021-04-30`, removed any empty spaces from the stock names, and extracted the list using the pandas `.unique()` function.
* **List Includes:** `Aa`, `Aaa`, `Aaaa`, `Stock C1`, `Stock C2`, `Stock C3`, `Stock C4`, etc.

### Question 2
For each of the unique underliers find the Closing Price as of 30th Apr 2021.
* **Answer:** Prices were found using a look-back logic (pulls the latest price on or before April 30, 2021):
  * **Stock C3:** `$177.42`
  * **Stock C4:** `$41.10`
  * **Stock C17:** `$782.23`
  *(The full list for all 99 stocks is clearly printed inside the notebook).*

### Question 3
For each of the unique underliers, find the Average closing Price from the data set.
* **Answer:** Calculated using a standard group-by mean function across the entire dataset:
  * **Stock C6:** `$770.79`
  * **Stock C7:** `$129.91`
  *(The full list for all 99 stocks is inside the notebook).*

### Question 4 & 5
4) For each of the unique underliers, find the Minimum closing Price in the data set and the date at which it occurred. 
5) For each of the unique underliers, find the Maximum closing Price in the data set and the date at which it occurred.
* **Answer:** Found the lowest and highest prices along with their specific dates:
  * **Stock C51:** Min of `$689.20` on `2021-04-30` | Max of `$1,146.81` on `2020-07-15`
  * **Stock C52:** Min of `$128.46` on `2021-04-30` | Max of `$218.05` on `2020-07-14`

### Question 6
Price both a Call and Put option on "Stock C4" as of 30th April 2021 Close. Strike=$50 Implied Volatility=20%. Maturity=20th Dec 2025. No Dividends are Paid.
* **Answer:** Calculated using the Black-Scholes-Merton model (using a 4.64-year maturity and a 0.85% risk-free rate):
  * **Call Option Price:** `$4.61`
  * **Put Option Price:** `$11.58`

### Question 7
Price a Forward on "Stock C3" expiring in 3 Months. Dividend=1%, Risk Free Rate = 3%
* **Answer:** Calculated using a 3-month maturity (0.25 years):
  * **Continuous Compounding Forward Price:** `$178.31`
  * **Discrete Compounding Forward Price:** `$178.29`

---

## Extra Analysis Added
* **Data Visualization Check:** I added a clean line chart inside the notebook tracking the price trends for the **top 5 highest-priced stocks**. This was done as an extra baseline check to easily spot long-term market movements and monitor the data for any sudden abnormal jumps or errors.
