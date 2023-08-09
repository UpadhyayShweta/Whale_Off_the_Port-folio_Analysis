# Whale_Off_the_Port-folio_Analysis

## Background

Cnsider a scenario: your friend, Harold's company has been investing in algorithmic trading strategies. Some of the investment managers love them, some hate them, but they all think their way is best.

Using quantitative analysis techniques with Python and Pandas, we have to help him determine which portfolio is performing the best across multiple areas: volatility, returns, risk, and Sharpe ratios.

In this analysis notebook we have analyzed and visualized the major metrics of the portfolios across all of these areas, and determine which portfolio outperformed the others. We have used the historical daily returns of several portfolios: some from the firm's algorithmic portfolios, some that represent the portfolios of famous "whale" investors like Warren Buffett, and some from the big hedge and mutual funds. We then used this analysis to create a custom portfolio of stocks and compare its performance to that of the other portfolios, as well as the larger market ([S&P TSX 60 Index](https://en.wikipedia.org/wiki/S%26P/TSX_60)).

For this we have performed three main tasks:

1. [Read in and Wrangle Returns Data](#Prepare-the-Data)

2. [Determine Success of Each Portfolio](#Conduct-Quantitative-Analysis)

3. [Choose and Evaluate a Custom Portfolio](#Create-a-Custom-Portfolio)

---

**Files:**

* [Whale Analysis](whale_analysis.ipynb)

* [algo_returns.csv](Resources/algo_returns.csv)

* [otex_historical.csv](Resources/otex_historical.csv)

* [sp_tsx_history.csv](Resources/sp_tsx_history.csv)

* [l_historical.csv](Resources/l_historical.csv)

* [shop_historical.csv](Resources/shop_historical.csv)

* [whale_returns.csv](Resources/whale_returns.csv)

### Prepare the Data

First, read and clean several CSV files for analysis. The CSV files include whale portfolio returns, algorithmic trading portfolio returns, and S&P TSX 60 Index historical prices. Use the starter code to complete the following steps:


### Conduct Quantitative Analysis

Analyzed the data to see if any of the portfolios outperform the stock market (i.e., the S&P TSX 60).

#### Performance Analysis

* Calculated and plot daily returns of all portfolios.

* Calculated and plot cumulative returns for all portfolios. 

#### Risk Analysis

* Created a box plot for each of the returns. 

* Calculated the standard deviation for each portfolio. 

* Determining which portfolios are riskier than the S&P TSX 60

* Calculated the Annualized Standard Deviation.

#### Rolling Statistics

* Calculated and plot the rolling standard deviation for all portfolios using a 21-day window.

* Calculated and plot the correlation between each stock to determine which portfolios may mimick the S&P TSX 60.

* Chose a custom portfolio, then calculate and plot the 60-day rolling beta for it and the S&P TSX 60.

#### Rolling Statistics Challenge: Exponentially Weighted Average

An alternative method to calculate a rolling window is to take the exponentially weighted moving average. This is like a moving window average, but it assigns greater importance to more recent observations. used the [`ewm`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.ewm.html) with a 21-day half-life.

### Sharpe Ratios

Investment managers and their institutional investors look at the return-to-risk ratio, not just the returns. After all, if you have two portfolios that each offer a 10% return, yet one is lower risk, you would invest in the lower-risk portfolio, right?

* Using the daily returns, calculated and visualized the Sharpe ratios using a bar plot.

* Determined whether the algorithmic strategies outperform both the market (S&P TSX 60) and the whales portfolios.

### Creating a Custom Portfolio

Harold is ecstatic that we were able to help him prove that the algorithmic trading portfolios are doing so well compared to the market and whales portfolios. However, now we will explore whether we can choose our own portfolio that performs just as well as the algorithmic portfolios. We will approach this task by doing the following:

1. Check [Google Sheets](https://docs.google.com/spreadsheets/) and use the built-in Google Finance function to choose one stock for our portfolio.

2. Download the data as CSV files and calculate the portfolio returns.

3. Calculate the weighted returns for our portfolio, assuming equal number of shares per stock.

4. Add our portfolio returns to the DataFrame with the other portfolios.

5. Run the following analyses:

    * Calculated the Annualized Standard Deviation.
    * Calculated and plotted rolling `std` with a 21-day window.
    * Calculated and plotted the correlation.
    * Calculated and plotted the 60-day rolling beta for your portfolio compared to the S&P 60 TSX.
    * Calculated the Sharpe ratios and generate a bar plot.
    

### Summary (Post Analysis)

**Note:** Our custom portfolio performed well, scoring a sharpe ratio of [`1.395425`] but could not outperform algorithmic trading portfolio "Algo 1" which scored a sharpe ratio of [`1.903790`].

---

## Resources

* [Pandas API Docs](https://pandas.pydata.org/pandas-docs/stable/reference/index.html)

* [Exponential weighted function in Pandas](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.ewm.html)

* [`GOOGLEFINANCE` function help](https://support.google.com/docs/answer/3093281)

* [Supplemental Guide: Fetching Stock Data Using Google Sheets](../../../01-Lesson-Plans/04-Pandas/Supplemental/googlefinance_guide.md)
  


