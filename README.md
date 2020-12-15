# Building Factor Portfolios for Indian Market
# Factor Portfolios have been around for quite some time. Globally Asset Managers have been moving from taking bets on stocks to bets on Factors. Below are couple of Factors which have been quite popular:
## 1. Momentum Factor: Return of a stock over 12m - 1m. This Factor counts on taking bets on stocks having good historical returns.

## 2. Value Factor: There are couple of defeinitons for this factors relying on taking bets on stocks with high earnings/price, book value/ price, EBIT/ Enterprise Value

## 3. Quality Factor: Again there are multiple definitons here where we suggest to take bets on stocks with high ROE and low leverage(Debt/Equity) ratios

## 4. Dividend: This factor signifies taking bet on stocks with high divident yield(Div/Price)

## 5. Growth Factor: This factor has multiple variants again taking bet on stocks with fast earning, sales, opeerating cash flows.

## 6. Multi Factors: A Multi Factor Portoflio can be created in mutiple ways by combining above individual factors in additive, tilt fashion or through a machine learning algorithm. 

# While there are multiple ways of evaluating and taking bet on these factors below is a high level process of same.

## 1. Universe Definiton: Define or use a custom universe on which to evaluate the relevancy of a Factor like S&P500 or NIFTY500.

## 2. Factor Pre-Treatment: Treat Factor for null values,back-filling, winsorization at 1% and 99% levels.

## 3. Factor Scoring: There are multiple ways of scoring Factor Exposure for each asset like Ranking them, or using a normal distribution.

## 4. Portoflio Building: Here we define a strategy around taking bets on a factor with either Long only or Long-Short portfolio in mind. We also define the recon period in mind(like monthly, quarterly, bi-yearly, yearly)

## 5. Strategy Execution: Once we build portfolio we select stocks with top scores at each rebalcing date and carry forward thise assets till next recon date.

## 6. Signal Strength Evaluation: Here we test the signal of a Factor Strength in various ways by Backtesting, Informtion Co-efficient evaluation, Factor Turnover. For a Factor to be relevent it should have good backtesting metrics(Sharpe Ration, Returns, Low Risk, Low Drawdowns),High & Relevant Informtion Coefficient, High Factor Auto Correlation for low turnover at each re-balancing and a statistically significant L-S Alpha.

# While there are a lot of materials available to build such portfolios for US Markets. There are very few for Indian markets. I attempt here to leverage proven Quant methodlogies to test Factors in Indian market. 

## I use a lot of Open Source Materials for building/testing Single/ Multi-Factor Portfolios. Here I use Yahoo for Market Price Data. Screener.in for Fundamental Data testing Factors on Nifty 500 universe which is a broad index to track Large, Mid& Small cap companies.

# Below are Steps to run all Jupyter notebooks in order.

## Step 1: Run Step1_Extract_Yahoo_Data_Nifty500.ipynb to extract all Pricing Data for NIFTY500 stocks for Yahoo Finance.

## Step 2: Run Step2_Extract_Screener_Data_Nifty500.ipynb to extract all Fundamental Data for NIFTY 500 companies from Screener.in website. Here we use Selenium and Beautiful Soup for all Data Extraction.

## Step 3: Run Step3_Integrate_Fundamental_Market_Data_nifty500.ipynb for extracting all Fundamental and Market data for downstream bakctesting and Alpha Lens Evaluation.

## Step 4: Step4_Backtesting_Stocks_nifty500.ipynb for building and bakctesting long only factors over various recon dates. Here we use BT & FFN libraries.

## Step 5: Step5_Run_ Factor_Alpha_Lens.ipynb for testing Significace of Long Short Alpha, Information Coefficient, Factor Auto Co-rrelation etc.

## All output(Backtesting Metric, Alpha Lens Output, Plots) gets geenrated in data folder.

# Below are some caveats:

## 1. This is a research project and should not be used for investment decission making. 

## 2. I am using lot of Open Source Data so there may be some data quality issues. 

## 3. I am using latest NIFTY Holdings(2020). Hence there will be survivorship bias in the data during backtesting exercise.

## All analysis is ex-Transaction Cost.