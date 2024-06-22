# Precious Metals Price 🪙

## Introduction
**Precious Metals Price** is a financial data analysis showcase using Jupyter Notebook, focusing on the most popular precious metals. The recent surge in their prices has sparked curiosity, making this a compelling topic to study. This project aims to analyze and forecast gold and silver prices, incorporating several related datasets. For detailed information about the datasets source, check it [here](/data/README.md).


## Tools Used
- **YFinance**: To gather some of the financial data using the Yahoo Finance API.
- **Jupyter Notebook**: The interactive environment used for coding and data analysis.
- **Pandas**: For cleaning, standardizing, manipulating, and analyzing datasets.
- **Matplotlib and Seaborn**: For creating charts.
- **NumPy and SciPy**: For numerical operations.
- **Statsmodels**: For time series decomposition and statistical modeling.
- **Scikit-learn**: For model evaluation metrics.
- **Pmdarima**: For automated ARIMA modeling.


## Analysis Overview
This project delves into several aspects of the most traded precious metals prices using a range of Python libraries, primarily Pandas, to offer comprehensive insights. It includes an in-depth examination of historical gold and silver prices, a brief analysis of the US consumer price index (CPI), and an exploration of correlations between these commodities and other related datasets. Furthermore, it provides a comparative analysis of gold and silver and forecasts their prices using two distinct methods.


### Table of contents
- [Price of gold across time](#AU_price)
- [Price of gold YTD](#AU_price_YTD)
- [Price of silver across time](#AG_price)
- [Price of silver YTD](#AG_price_YTD)
- [Brief analysis of the US CPI](#CPI) 
- [Price of gold adjusted for inflation](#AU_real_price)
- [Price of silver adjusted for inflation](#AG_real_price)
- [Analysis of correlations](#AU_AG_correlations)
- [Comparison of gold and silver prices](#AU_AG_comparison)
- [Probabilistic forecasting of the gold price](#AU_Monte_Carlo)
- [Probabilistic forecasting of the silver price](#AG_Monte_Carlo)
- [Deterministic forecasting of the gold price](#AU_SARIMA)
- [Deterministic forecasting of the silver price](#AG_SARIMA)
- [Conclusions](#Conclusions)

---

### Price of gold across time (long-term analysis) <a name = "AU_price"></a>
![Gold price chart](/images/1.1_AU_price.png)
*Line chart of the historical price of gold and its one-year moving average.*

**It's easier to see the early price fluctuations with a logarithmic scale on the y-axis**
<details>
<summary>Click to reveal chart</summary>

![Gold price chart log](/images/1.1_AU_price_log.png)
*Line chart of the historical price of gold and its one-year moving average, with a logarithmic scale on the y-axis.*
</details>

**Key takeaways:**
- The all-time low occurred in 1970, with the price at approximately \$35.
- Prices surged rapidly from the early 1970s, following the collapse of the Bretton Woods system in 1973.
- Reached a peak in 1980 at around \$850.
- Experienced a decline over the next 20 years.
- Prices rose consistently until the early 2010s, peaking in 2011 at about \$1,500.
- Declined slightly until 2019, then started rising again.
- An all-time high was achieved in April 2024, with prices nearing \$2,400.
- The price of gold has appreciated by approximately 6,670% since the first entry.

#### Price change year-over-year
![Gold YoY return chart](/images/1.1_AU_YoY_return.png)
*Bar chart of the historical year-over-year return of gold.*

| Decade             | 1970  | 1980  | 1990  | 2000  | 2010 | 2020  |
| ------------------ | ----- | ----- | ----- | ----- | ---- | ----- |
| Average YoY return | 36.5% | -2.1% | -2.6% | 15.1% | 4.0% | 9.2%  |
| Median YoY return  | 27.4% | 1.2%  | -2.9% | 21.0% | 6.4% | 12.4% |

**Key takeaways:**
- In 1979, gold achieved a remarkable year-over-year return of 130%.
- Two years later, gold experienced its lowest return, dropping approximately 32.4%.
- The average annual return for gold has been around 9.8%, with a median return of about 5.5%.
- The 1970s were the most lucrative decade for gold, boasting an average annual return of 36.5%.
- During the 1980s and 1990s, gold's performance lagged, with an average annual return of around -2%.
- The 2000s delivered strong performance, with an average annual return of 15.1% and a median return of 21%.
- The current decade has shown promising results so far, with an average annual return of 9.2% and a median return of 12.4%.

#### Yearly volatility (EWMA method)
![Gold yearly volatility chart](/images/1.1_AU_Y_vlt.png)
*Line chart of the historical yearly volatility of the price of gold.*

| Decade                    | 1970 | 1980 | 1990 | 2000 | 2010 | 2020 |
| ------------------------- | ---- | ---- | ---- | ---- | ---- | ---- |
| Average yearly volatility | 1.3% | 1.6% | 0.7% | 1.2% | 1.0% | 0.9% |

**Key takeaways:**
- The largest five daily price changes occurred at the beginning of 1980.
- The average yearly volatility is 1.1%.
- The all-time low occurred in 1996, whereas the all-time high was observed a decade later, with yearly volatility almost tenfold higher.
- Volatility significantly increased following the collapse of the Bretton Woods system in 1973.
- The market was highly volatile from the mid-1970s through the early 1980s, and during the dotcom bubble, the Great Recession, and the EU sovereign debt crisis.
- The market remained very stable during the 1990s, and also during the current decade excluding the pandemic period.

#### STL decomposition (trend, seasonality, and residuals)
##### Trend analysis
![Gold trend chart](/images/1.1_AU_trend.png)
*Line chart of the trend component of the historical price of gold with a logarithmic scale on the y-axis.*

**Key takeaways:**
- The trend experienced significant growth during the 1970s.
- There was a slow decline over the following 20 years.
- Since then, it has been rising with notable consistency.

##### Seasonality analysis
![Gold seasonal chart](/images/1.1_AU_seasonal.png)
*Line chart of the average seasonal component of the price of gold throughout the year.*

**Key takeaways:**
- Seasonal patterns exhibit variations over the years.
- Based on monthly averages, it reveals favorable seasons during the first four months of the year and in September.
- Some analysts suggest that gold experiences a strong seasonal phase starting in mid-November, extending until the second half of February.

*For more details about this section, check the respective [Notebook](/notebooks/1.1_AU_price_analysis.ipynb).*
<br> <!-- Line break -->



### Price of gold year-to-date (short-term analysis) <a name = "AU_price_YTD"></a>
![Gold price YTD chart](/images/1.1_AU_price_YTD.png)
*Line chart of the historical price of gold year-to-date.*

**Key takeaways:**
- The year-to-date price change stands at a notable 17.4%, showcasing strong market movement.
- Before the breakout, the average price hovered around \$2,032.
- The breakout occurred in early March.
- Post-breakout, the price grew quickly, averaging a daily increase of approximately 0.5%.
- By mid-April, the price peaked at \$2,400.
- After reaching all-time high in mid-April, the average price has since stabilized around \$2,343, suggesting a period of consolidation.

#### Weekly volatility
![Gold weekly volatility YTD chart](/images/1.1_AU_W_vlt_YTD.png)
*Line chart of the historical weekly volatility of the price of gold year-to-date.*

**Key takeaways:**
- In the beginning, weekly volatility averaged at 0.6%, indicating relative stability.
- A breakout occurred on March 21st, dramatically altering the landscape.
- Following the breakout, the average volatility surged to 1.2%, doubling its previous level.

*For more details about this section, check the respective [Notebook](/notebooks/1.1_AU_price_analysis.ipynb).*



### Price of silver across time (long-term analysis) <a name = "AG_price"></a>
![Silver price chart](/images/1.2_AG_price.png)
*Line chart of the historical price of silver and its one-year moving average.*

**It's easier to see the early price fluctuations with a logarithmic scale on the y-axis**
<details>
<summary>Click to reveal chart</summary>

![Silver price chart log](/images/1.2_AG_price_log.png)
*Line chart of the historical price of silver and its one-year moving average, with a logarithmic scale on the y-axis.*
</details>

**Key takeaways:**
- Silver hit its historic low in 1970, hovering around \$1.3.
- Similar to gold, its value surged swiftly from the early 1970s.
- The pinnacle was reached in 1980, soaring to \$49.5.
- Following this peak, a period of decline ensued until the early 1990s, stabilizing thereafter until the early 2000s.
- Subsequently, there was a consistent ascent until the early 2010s, culminating in a peak of approximately \$48.7 in 2011.
- Despite some fluctuations, there was a general downtrend and stabilization until the onset of the pandemic, after which a renewed ascent began.
- The price has appreciated by approximately 1,270% since its initial point.

#### Price change year-over-year
![Silver YoY return chart](/images/1.2_AG_YoY_return.png)
*Bar chart of the historical year-over-year return of silver, with a symmetrical logarithmic scale on the y-axis.*

| Decade             | 1970  | 1980   | 1990  | 2000  | 2010  | 2020  |
| ------------------ | ----- | ------ | ----- | ----- | ----- | ----- |
| Average YoY return | 57.7% | -13.8% | 1.6%  | 14.6% | 3.5%  | 11.8% |
| Median YoY return  | 15.6% | -11.6% | -6.1% | 13.7% | -2.0% | 4.6%  |

**Key takeaways:**
- In 1979, silver experienced an astonishing surge, with a remarkable 430% increase.
- However, the following year, it plummeted, marking the lowest return at approximately -61.2%.
- Over the years, silver has shown an average year-over-year return of approximately 11.8%, surpassing gold. Yet, the median return stands at -1.5%.
- When 1979 is ignored, the average YoY drops significantly to about 4.4%.
- Mirroring gold's performance, the 1970s emerged as the standout decade for silver, boasting an average YoY return of around 58%, with a much lower median.
- The 1980s, in contrast, witnessed a downturn, with an average return of approximately -13.8%.
- During the 2000s, the price rebounded with an average return of about 14.6%.
- As we go through the current decade, silver continues to show promise with an average return of around 11.8%. However, the median return hovers around 4.6%.

#### Yearly volatility
![Silver yearly volatility chart](/images/1.2_AG_Y_vlt.png)
*Line chart of the historical yearly volatility of the price of silver.*

| Decade                    | 1970 | 1980 | 1990 | 2000 | 2010 | 2020 |
| ------------------------- | ---- | ---- | ---- | ---- | ---- | ---- |
| Average yearly volatility | 1.8% | 3.1% | 1.5% | 1.8% | 1.9% | 1.9% |

**Key takeaways:**
- The 1980s witnessed the largest daily price fluctuations.
- Over the years, the average yearly volatility has been 2%.
- The all-time high was in 1983, and the all-time low in 2001.
- Periods of heightened volatility occurred during the mid-70s and early 80s, and also during major economic events such as the Great Recession, EU sovereign debt crisis, and the pandemic.
- Conversely, the market was very stable during the 90s, early 2000s, and late 2010s.

#### STL decomposition (trend, seasonality, and residuals)
##### Trend analysis
![Silver trend chart](/images/1.2_AG_trend.png)
*Line chart of the trend component of the historical price of silver with a logarithmic scale on the y-axis.*

**Key takeaways:**
- The trend grew significantly throughout the 1970s.
- Following this peak, there was a gradual decline until the 1990s.
- After that, there was a resurgence from the early 2000s until the early 2010s.
- There's 30-year valley spanning from the 1980s to the 2010s.

##### Seasonality analysis
![Silver seasonal chart](/images/1.2_AG_seasonal.png)
*Line chart of the average seasonal component of the price of silver throughout the year.*

**Key takeaways:**
- Seasonality has variations across different years.
- Just like gold, based on monthly averages, there's favorable seasons during the first four months of the year, with an additional peak in September.

*For more details about this section, check the respective [Notebook](/notebooks/1.2_AG_price_analysis.ipynb).*



### Price of silver year-to-date (short-term analysis) <a name = "AG_price_YTD"></a>
![Silver price YTD chart](/images/1.2_AG_price_YTD.png)
*Line chart of the historical price of silver year-to-date.*

**Key takeaways:**
- The year-to-date price change stands at approximately 24%.
- Prior to the breakout, the average price lingered around \$23.
- A notable price breakout occurred in early March.
- Post-breakout, the price exhibited an average daily increase of about 0.9%.
- The price peaked around \$29 in mid-April.
- Since reaching its peak, the average price has stabilized around \$28.

#### Weekly volatility
![Silver weekly volatility YTD chart](/images/1.2_AG_W_vlt_YTD.png)
*Line chart of the historical weekly volatility of the price of silver year-to-date.*

**Key takeaways:**
- Average weekly volatility has been gradually increasing over time.
- Unlike gold, silver has not shown any clear breakout trends.

*For more details about this section, check the respective [Notebook](/notebooks/1.2_AG_price_analysis.ipynb).*



### Brief analysis of the US consumer price index (CPI) <a name = "CPI"></a>
#### CPI long-term analysis
![US CPI chart](/images/2_US_CPI.png)
*Line chart of the historical rate of the US consumer price index and 2% Fed target.*

| Decade      | 1950  | 1960  | 1970  | 1980  | 1990 | 2000  | 2010  | 2020  |
| ----------- | ----- | ----- | ----- | ----- | ---- | ----- | ----- | ----- |
| Average CPI | 2.15% | 2.33% | 7.09% | 5.56% | 3.0% | 2.57% | 1.77% | 4.42% |

**Key takeaways:**
- Inflation surged through the late 1960s, peaking at a historic high of 14.8% in 1980, before rapidly declining.
- During the early 1960s, CPI remained consistently below the 2% target, a level once considered a ceiling by the central bank.
- Throughout 1970s and early 1980s, inflation rates soared significantly, posing economic challenges.
- Throughout the 1990s and between the 2010s and the end of the pandemic lockdowns, inflation remained relatively contained.
- The 2010s marked the decade with the lowest average CPI rate, settling at 1.8%.
- Instances of deflation occurred only in 2009 and 2015.
- Recently, inflation has reemerged as a notable concern.

#### CPI + fed rates since 2020 analysis
![US CPI 2020 chart](/images/2_US_CPI_2020.png)
*Line chart of the rate of the US consumer price index and Fed funds effective rate since 2020 and 2% Fed target.*

**Key takeaways:**
- In March 2021, the CPI breached 2%, quickly escalating to 4.16% the following month, culminating at about 9% by June 2022.
- The Federal Reserve took about a year from the initial inflationary pressure to start the rate hikes, when inflation was no longer perceived as transitory.
- Initially, the Fed's rate adjustments were gradual, beginning in March 2022, but gained momentum by May, reaching a peak in August 2023 before stabilizing.
- Inflation decreased until June 2023, stabilizing at approximately 3.3%, still above the 2% target, and has remained "sticky" at this level.
- During this "sticky" period, there was an average gap of about 2 percentage points between the Fed's interest rates and the CPI rate.

*For more details about this section, check the respective [Notebook](/notebooks/2_US_CPI_analysis.ipynb).*



### Price of gold adjusted for inflation across time <a name = "AU_real_price"></a>
![Gold real price chart](/images/3.1_AU_real_price.png)
*Line chart of the historical price of gold in 2023 dollars and its one-year moving average.*

**Comparison of real price with nominal price**
<details>
<summary>Click to reveal chart</summary>

![Gold real and nominal price chart](/images/3.1_AU_real_and_nominal_price.png)
*Line chart of the historical price of gold in 2023 dollars and its nominal price.*
</details>

**Key takeaways:**
- The real price chart of gold closely resembles the nominal price chart of silver.
- Over a long-term period (15+ years), real gold prices do not show consistent growth, unlike the equities market.
- Despite significant fluctuations over the long term, gold prices generally seem to track inflation, establishing the precious metal as a store of value.
- The all-time high for the real gold price was reached in 1980.
- The current real value of gold is nearly the same as it was in the early 1980s.
- Gold real prices experienced a significant decline from the 1980s to the 2010s, followed by smaller declines in the 2010s and post-2020.
- There is notable resistance at the \$2,500 price level.
- Since the initial data point, the real price of gold has appreciated by approximately 646%.

#### Real price change year-over-year
![Gold YoY real return chart](/images/3.1_AU_YoY_real_return.png)
*Bar chart of the historical year-over-year real return of gold.*

| Decade                  | 1970  | 1980  | 1990  | 2000  | 2010 | 2020  |
| ----------------------- | ----- | ----- | ----- | ----- | ---- | ----- |
| Average YoY real return | 30.1% | -3.8% | -2.6% | 15.6% | 5.1% | 8.2%  |
| Median YoY real return  | 21.8% | -3.5% | -3.9% | 21.2% | 7.3% | 12.4% |

**Key takeaways:**
- Gold's average year-over-year real return is 8.5%, which is notably high.
- The median YoY real return for gold slightly surpasses the nominal return median.
- The average real return since the 1980s is 4%, increasing to 10% since the 2000s.
- Although the price chart suggests gold tracks inflation, the data indicates a significant positive return after accounting for inflation.

#### STL decomposition (trend, seasonality, and residuals)
##### Trend analysis
![Gold real trend chart](/images/3.1_AU_real_trend.png)
*Line chart of the trend component of the historical price of gold in 2023 dollars.*

**The valleys in the trend are more pronounced, and the peak in 2012 is higher than the peak in 1980, despite ATH being on 1980.**

##### Seasonality analysis
![Gold real seasonal chart](/images/3.1_AU_real_seasonal.png)
*Line chart of the average seasonal component of the real price of gold throughout the year.*

**When adjusting for inflation, the average seasonality aligns more closely with some analysts' descriptions.**

*For more details about this section, check the respective [Notebook](/notebooks/3.1_AU_real_price_analysis.ipynb).*



### Price of silver adjusted for inflation across time <a name = "AG_real_price"></a>
![Silver real price chart](/images/3.2_AG_real_price.png)
*Line chart of the historical price of silver in 2023 dollars and its one-year moving average, with a logarithmic scale on the y-axis.*

**Comparison of real price with nominal price**
<details>
<summary>Click to reveal chart</summary>

![Silver real and nominal price chart](/images/3.2_AG_real_and_nominal_price.png)
*Line chart of the historical price of silver in 2023 dollars and its nominal price, with a logarithmic scale on the y-axis.*
</details>

**Key takeaways:**
- The real price of silver shows significant fluctuations without substantial long-term increases.
- Silver's price has not kept pace with inflation as effectively as gold.
- Unlike gold, silver's all-time high remains unchanged, while the all-time low shifted to 2001.
- Similar to gold, silver experienced a major valley between the 1980s and 2010s, a smaller valley in the 2010s, and an even smaller valley after 2020. However, the peaks have become progressively smaller.
- Since the initial point, the real price of silver has only appreciated by approximately 50%.

#### Real price change year-over-year
![Silver YoY real return chart](/images/3.2_AG_YoY_real_return.png)
*Bar chart of the historical year-over-year real return of silver, with a symmetrical logarithmic scale on the y-axis.*

| Decade                  | 1970  | 1980   | 1990  | 2000  | 2010  | 2020  |
| ----------------------- | ----- | ------ | ----- | ----- | ----- | ----- |
| Average YoY real return | 49.1% | -15.0% | 1.7%  | 15.0% | 4.6%  | 10.9% |
| Median YoY real return  | 10.4% | -12.8% | -6.3% | 12.9% | -1.4% | 1.6%  |

**Key takeaways:**
- The average year-over-year real return of silver is 10.3%, which is notably high, although the median is 0%.
- When considering data since the 1980s, the average real return of silver drops to 2.6%.
- Since the 2000s, the real return averages 10%, aligning with gold's performance.

#### STL decomposition (trend, seasonality, and residuals)
##### Trend analysis
![Silver real trend chart](/images/3.2_AG_real_trend.png)
*Line chart of the trend component of the historical price of silver in 2023 dollars.*

**Similar to gold, silver exhibits a clearer valley in its trend, but its second peak is significantly smaller than the first, and the third is smaller than the second.**

##### Seasonality analysis
![Silver real seasonal chart](/images/3.2_AG_real_seasonal.png)
*Line chart of the average seasonal component of the real price of silver throughout the year.*

**Adjusting for inflation, silver's average seasonality shows significant changes. Notable decline in April and a rise in the last quarter.**

*For more details about this section, check the respective [Notebook](/notebooks/3.2_AG_real_price_analysis.ipynb).*



### Analysis of correlations of gold, silver and other datasets <a name = "AU_AG_correlations"></a>
#### Correlation matrix (Pearson method)
![Gold silver correlations matrix chart](/images/4_AU_AG_correlations_matrix.png)
*Heat map chart of the correlation matrix of all datasets, including gold and silver yearly volatilities.*

**Key takeaways:**
- The spot and futures markets have a perfect correlation, as anticipated.
- Gold and silver show a strong correlation, including their respective yearly volatilities.
- Gold is strongly correlated with the S&P 500 and US real GDP, while silver has a moderate correlation with these indicators.
- Gold has a strong correlation with Bitcoin, whereas silver shows no correlation.
- Gold exhibits a moderate negative correlation with the Fed funds rate and the US 10-year Treasury yield, with silver showing a slightly weaker negative correlation.
- Both metals have a weak to moderate negative correlation with the dollar index.
- Gold shows no correlation with mining stocks, in contrast to silver, which has a strong correlation, particularly with its miners.
- There is no correlation between central banks' gold reserves and the precious metals.
- Both metals have little to no correlation with US inflation and the volatility index; however, the metals' volatilities, especially gold's, are moderately correlated with these indicators.

*For more details about this section, check the respective [Notebook](/notebooks/4_AU_AG_correlations.ipynb).*



### Comparison of gold and silver prices <a name = "AU_AG_comparison"></a>
#### Price
![Gold silver comparison price scatter chart](/images/5_AU_AG_comparison_price_scatter.png)
*Scatter plot chart comparing the historical price of gold vs silver.*

**Key takeaways:**
- This scatter plot clearly shows the robust correlation (0.9) between gold and silver prices.
- In the 1970s, 1980s, and 2000s, there were periods when silver prices rose more sharply than gold prices.
- Overall, gold prices seem to have risen more than silver, though this varies by decade.

![Gold silver comparison price chart](/images/5_AU_AG_comparison_price.png)
*Line chart comparing the historical price of gold and silver, with a logarithmic scale on both y-axis.*

**Key takeaways:**
- During the 1970s, price fluctuations of gold and silver were close, but silver began losing momentum in the mid-1980s.
- In the 1990s, price fluctuations diverged, with silver showing some recovery in the late 2000s and early 2010s before falling again since the 2010s.
- To have a better notion, we need to analyze the gold-to-silver ratio.

##### Price ratio
![Gold silver comparison price ratio chart](/images/5_AU_AG_comparison_price_ratio.png)
*Line chart of the historical gold to silver price ratio and its one-year moving average.*

**Key takeaways:**
- The ratio was at its lowest before the mid-1980s.
- Throughout the 1980s, silver lost ground to gold, with the ratio peaking in the early 1990s.
- During this decade, silver partially recovered but then stabilized.
- In the 2010s, the ratio increased again.
- The current decade has the highest average ratio at 82.3, compared to 20.5 in the 1960s.

#### Price change year-over-year
![Gold silver comparison YoY return chart](/images/5_AU_AG_comparison_YoY_return.png)
*Bar chart of the historical year-over-year return of gold and silver, with a symmetrical logarithmic scale on the y-axis.*

**Since the 1980s, the absolute return on silver has generally been higher than gold, likely due to greater volatility. Comparing the difference of the return between bars will provide more insights.**

##### Price change year-over-year difference
![Gold silver comparison YoY return diff chart](/images/5_AU_AG_comparison_YoY_return_diff.png)
*Bar chart of the historical year-over-year return advantage of each metal in percentage points, with a logarithmic scale on the y-axis.*

**Key takeaways:**
- Gold has outperformed silver in 34 years, whereas silver outperformed gold in 23 years.
- This year, silver is outperforming gold by approximately 10 percentage points.
- On average, silver's year-over-year return is about 2 percentage points higher than gold's.
- However, excluding the anomalous year of 1979 for both metals, gold takes the lead, boasting a return approximately 3.2 percentage points higher than silver.
- Moreover, gold shines with a median YoY return about 7 percentage points greater than silver's.
- Gold also outperforms silver by approximately 470 percentage points in cumulative YoY returns.
- Given this, gold generally performs better than silver on a YoY basis.

#### Yearly volatility
![Gold silver comparison Y vlt chart](/images/5_AU_AG_comparison_Y_vlt.png)
*Line chart of the historical yearly volatility of the price of gold and silver.*

**Key takeaways:**
- The high correlation (0.78) between the metals' volatilities is evident, though not as strong as the correlation between their prices.
- Silver has shown significantly higher volatility, particularly since the 1980s.
- The average volatility of silver is almost double that of gold.

##### Yearly volatility ratio
![Gold silver comparison Y vlt ratio chart](/images/5_AU_AG_comparison_Y_vlt_ratio.png)
*Line chart of the historical gold to silver price yearly volatility ratio and equal volatility line.*

**Periods where gold was more volatile than silver are rare, occurring less than 6% of the time, mainly in the 1970s and also on early 2000s.**

*For more details about this section, check the respective [Notebook](/notebooks/5_AU_AG_comparison.ipynb).*



### Probabilistic forecasting of the gold price using Monte Carlo method 🎲 <a name = "AU_Monte_Carlo"></a>
#### One year forecast
![Gold Monte Carlo 1Y hist chart](/images/6.1_AU_Monte_Carlo_1Y_hist.png)
*Histogram chart of gold price distribution for mid-May 2025 from Monte Carlo simulation.*

**Key takeaways:**
- The probability of gold exceeding its all-time high by mid-May of 2025 is about 64%.
- The likelihood of surpassing \$3,000 by mid-May of 2025 is approximately 22%.
- The chance of falling below \$2,000 by mid-May of 2025 is nearly 10%.

#### Ten years forecast
![Gold Monte Carlo 10Y hist chart](/images/6.1_AU_Monte_Carlo_10Y_hist.png)
*Histogram chart of gold price distribution for mid-May 2034 from Monte Carlo simulation.*

**Key takeaways:**
- The probability of gold exceeding its all-time high by mid-May of 2034 is about 89%.
- The likelihood of surpassing \$5,000 by mid-May of 2034 is approximately 51%.
- The chance of falling below \$2,000 by mid-May of 2034 is nearly 7%.

*For more details about this section, check the respective [Notebook](/notebooks/6.1_AU_Monte_Carlo.ipynb).*



### Probabilistic forecasting of the silver price using Monte Carlo method 🎲 <a name = "AG_Monte_Carlo"></a>
#### One year forecast
![Silver Monte Carlo 1Y hist chart](/images/6.2_AG_Monte_Carlo_1Y_hist.png)
*Histogram chart of silver price distribution for mid-May 2025 from Monte Carlo simulation.*

**Key takeaways:**
- The probability of silver exceeding its all-time high by mid-May of 2025 is about 10%.
- The likelihood of surpassing \$35 by mid-May of 2025 is approximately 37%.
- The chance of falling below \$20 by mid-May of 2025 is nearly 11%.

#### Ten years forecast
![Silver Monte Carlo 10Y hist chart](/images/6.2_AG_Monte_Carlo_10Y_hist.png)
*Histogram chart of silver price distribution for mid-May 2034 from Monte Carlo simulation.*

**Key takeaways:**
- The probability of silver exceeding its all-time high by mid-May of 2034 is about 48%.
- The likelihood of surpassing \$100 by mid-May of 2034 is approximately 26%.
- The chance of falling below \$20 by mid-May of 2034 is nearly 23%.

*For more details about this section, check the respective [Notebook](/notebooks/6.2_AG_Monte_Carlo.ipynb).*



### Deterministic forecasting of the gold price using SARIMA method 🔮 <a name = "AU_SARIMA"></a>
![Gold SARIMA chart](/images/7.1_AU_ARIMA.png)
*Line chart of the historical price of gold since 2022, including a 6-month forecast and its confidence interval.*

**The forecast indicates that gold prices will consistently rise over the next six months.**

*For more details about this section, check the respective [Notebook](/notebooks/7.1_AU_ARIMA.ipynb).*



### Deterministic forecasting of the silver price using SARIMA method 🔮 <a name = "AG_SARIMA"></a>
![Silver SARIMA chart](/images/7.2_AG_ARIMA.png)
*Line chart of the historical price of silver since 2022, including a 6-month forecast and its confidence interval.*

**Silver prices are expected to rise steadily over the next six months, much like gold. Although the model parameters are the same to those used for gold, the confidence interval for silver is significantly wider.**

*For more details about this section, check the respective [Notebook](/notebooks/7.2_AG_ARIMA.ipynb).*



### Conclusions
- Gold YoY real returns are much higher than anticipated.
- Although silver YoY returns initially appeared higher than gold's, deeper analysis shows gold as the best-performing metal.
- Both metals are highly correlated, as expected, with silver being twice as volatile.
- ARIMA models use historical data to forecast future events, assuming past values impact future values. However, past performance is not a guaranteed indicator of future results, and these models cannot predict unpredictable events like market crashes or natural disasters.
- Gold is not a perfect inflation hedge, as shown by its correlation with the CPI. The metal's real historical value has significant valleys, as well as notable volatility. However, if held for at least 30 years, gold can indeed serve as an inflation hedge or even provide real returns. This is not the case for silver, which is much less likely to be an inflation hedge.
- According to the Lindy effect, gold (and to a lesser degree, silver) will continue to be what they have always been: safe havens.


## Disclaimer
The content of this project is provided for **demonstration and educational purposes only**. The information presented here is **not intended** to be financial advice.


## License
GNU General Public License v3.0.
