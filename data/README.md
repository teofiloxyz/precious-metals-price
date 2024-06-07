# Datasets Source
The data for this project was searched and collected between 14th and 18th of May. After collection, the data was cleaned and standardized into these CSV files.

## Datasets
1. **Gold price**:
    - **Description**: Daily price at 10:30 (London time) of a troy ounce of gold since 1968.
    - **Source**: [DBnomics](https://db.nomics.world/LBMA/gold_D)
    - **File**: `AU.csv`
2. **Silver price**:
    - **Description**: Daily price at 12:00 (London time) of a troy ounce of silver since 1968.
    - **Source**: [DBnomics](https://db.nomics.world/LBMA/silver_D)
    - **File**: `AG.csv`
3. **Gold futures**:
    - **Description**: Daily open, high, low, and close prices for gold futures since 2000.
    - **Source**: [Yahoo Finance](https://finance.yahoo.com/quote/GC%3DF/history) (using the API)
    - **File**: `AU_FUTURES.csv`
4. **Silver futures**:
    - **Description**: Daily open, high, low, and close prices for silver futures since 2000.
    - **Source**: [Yahoo Finance](https://finance.yahoo.com/quote/SI%3DF/history) (using the API)
    - **File**: `AG_FUTURES.csv`
5. **Gold miners ETF**:
    - **Description**: Daily open, high, low, and close prices for VanEck gold miners ETF (GDX) since 2006.
    - **Source**: [Yahoo Finance](https://finance.yahoo.com/quote/GDX/history)
    - **File**: `AU_MINERS_ETF.csv`
6. **Silver miners ETF**:
    - **Description**: Daily open, high, low, and close prices for Global X silver miners ETF (SIL) since 2010.
    - **Source**: [Yahoo Finance](https://finance.yahoo.com/quote/SIL/history)
    - **File**: `AG_MINERS_ETF.csv`
7. **Gold world reserves**:
    - **Description**: Monthly official amount of gold reserves held by all central banks in troy ounces since 1957.
    - **Source**: [DBnomics](https://db.nomics.world/IMF/IFS?dimensions=%7B%22REF_AREA%22%3A%5B%22W0%22%5D%2C%22FREQ%22%3A%5B%22M%22%5D%7D&q=RAFAGOLDV_OZT&tab=list)
    - **File**: `AU_WORLD_RESERVES_OZ_M.csv`
8. **US real GDP**:
    - **Description**: Quarterly real gross domestic product (GDP) of the United States (US) in billions of 2017 dollars since 1947.
    - **Source**: [Federal Reserve Economic Data (FRED)](https://fred.stlouisfed.org/series/GDPC1)
    - **File**: `US_REAL_GDP_Q.csv`
9. **US CPI**:
    - **Description**: Monthly consumer price index (CPI) for the US since 1956.
    - **Source**: [DBnomics](https://db.nomics.world/IMF/CPI/M.US.PCPI_PC_CP_A_PT)
    - **File**: `US_CPI_M.csv`
10. **Fed funds effective rate**:
    - **Description**: Monthly federal funds effective rate for the US since 1954.
    - **Source**: [FRED](https://fred.stlouisfed.org/series/FEDFUNDS)
    - **File**: `FED_FUNDS_EFFECTIVE_RATE_M.csv`
11. **US 10-year treasury yield**:
    - **Description**: Daily market yield on US treasury securities at a 10-year constant maturity since 1962.
    - **Source**: [FRED](https://fred.stlouisfed.org/series/DGS10)
    - **File**: `US_10Y_TREASURY_YIELD.csv`
12. **DXY**:
    - **Description**: Daily open, high, low, and close prices for US dollar index (DXY) since 1971.
    - **Source**: [Yahoo Finance](https://finance.yahoo.com/quote/DX-Y.NYB/history)
    - **File**: `DXY.csv`
13. **S&P 500**:
    - **Description**: Daily open, high, low, and close prices for Standard and Poor's 500 (S&P 500) index since 1927.
    - **Source**: [Yahoo Finance](https://finance.yahoo.com/quote/%5EGSPC/history) (using the API)
    - **File**: `SP500.csv`
14. **VIX**:
    - **Description**: Daily open, high, low, and close prices for CBOE volatility index (VIX) since 1990.
    - **Source**: [Chicago Board Options Exchange (CBOE)](https://cdn.cboe.com/api/global/us_indices/daily_prices/VIX_History.csv)
    - **File**: `VIX.csv`
15. **Bitcoin**:
    - **Description**: Daily open, high, low, and close prices for bitcoin since 2010.
    - **Source**: [Coin Codex](https://coincodex.com/crypto/bitcoin/historical-data)
    - **File**: `BTC.csv`
