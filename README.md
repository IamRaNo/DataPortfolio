# 📊 DataPortfolio

A collection of end-to-end data analysis projects — from raw data collection to statistical testing and dashboards.

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![SQL](https://img.shields.io/badge/MySQL-4479A1?style=flat&logo=mysql&logoColor=white)
![Excel](https://img.shields.io/badge/Excel-217346?style=flat&logo=microsoftexcel&logoColor=white)
![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=flat&logo=powerbi&logoColor=black)

## 🔎 Projects at a Glance

| # | Project | Question | Key Finding |
|---|---------|----------|--------------|
| 1 | [Avoiding The Hype Trap](https://github.com/IamRaNo/DataPortfolio/tree/main/Avoiding%20The%20Hype%20Trap) | Do IPO Day 1 gains predict long-term returns? | Big gains are linked to better returns, but not reliably |
| 2 | [Men's IPL 2026](https://github.com/IamRaNo/DataPortfolio/tree/main/Men%E2%80%99s%20IPL%202026) | Are auction prices justified by performance? | Priyansh Arya was underpriced; Kartik Sharma was overpriced |
| 3 | [The Electoral Advantage](https://github.com/IamRaNo/DataPortfolio/tree/main/The%20Electoral%20Advantage) | Profile or political history — what wins elections? | Candidate profile matters more |
| 4 | [Suicide Risk Patterns in India](https://github.com/IamRaNo/DataPortfolio/tree/main/Suicide%20Risk%20Patterns%20in%20India) | Is there a pattern behind the numbers? | Unmarried students, 10th-grade education = highest risk |

---

## 1. 💸 Avoiding The Hype Trap – Do IPO Day 1 Gains Predict Long-Term Returns?
*Python, MySQL, Regression* | [View Project →](https://github.com/IamRaNo/DataPortfolio/tree/main/Avoiding%20The%20Hype%20Trap)

**Problem:** Can investors trust Day 1 IPO listing gains as a signal for long-term returns?

**Process:**
- Scraped Mainboard IPO performance data from Chittorgarh (JSON embedded in page source, parsed via regex) and daily OHLCV price history via `yfinance`
- Cleaned and merged the two sources on company name, standardized date/column formats
- Engineered features — `days_since_listing`, returns at multiple horizons (1w/1m/3m/6m/1y), max drawdown, volatility, gain buckets
- Loaded the final tables into MySQL and ran SQL queries to validate patterns spotted in Python (year-wise trends, outlier companies)
- In Python: univariate distributions, correlation checks, regression plot (Day 1 gain vs 1-year return), and a Kruskal-Wallis test across gain buckets

**Key Finding:** Big Day 1 gains are often linked to better long-term returns, but the relationship is not strong or consistent enough to rely on.

---

## 2. 🏏 Men's IPL 2026 – Are Auction Prices Justified?
*Python, Matplotlib, Seaborn* | [View Project →](https://github.com/IamRaNo/DataPortfolio/tree/main/Men%E2%80%99s%20IPL%202026)

**Problem:** Did IPL 2026 auction prices actually match player performance?

**Process:**
- Imported batting, bowling, and auction price data from Excel
- Cleaned inconsistent fields (e.g. average with placeholder `-` recalculated from runs/innings, `not-out` markers stripped from high scores)
- Engineered performance features — boundary %, average balls per innings, chance-taken %, final price rate (final/base price)
- Merged stats with auction prices, filtered to players with meaningful innings count
- Univariate + bivariate EDA to find performance thresholds that align with high price rates
- Scaled features with MinMaxScaler and built a weighted composite score per role (batter/bowler) to compare against price rate

**Key Finding:** Batter Priyansh Arya's performance was worth more than his auction price. Bowler Kartik Sharma's price was higher than his performance justified.

---

## 3. 🗳️ The Electoral Advantage – Candidate Profile vs Political History
*Excel, Statistics* | [View Project →](https://github.com/IamRaNo/DataPortfolio/tree/main/The%20Electoral%20Advantage)

**Problem:** What influences election outcomes more — candidate profile or political history?

**Process:**
- Raw election data cleaned into a usable dataset (RAW → CLEANED → USABLE stages, all in Excel)
- Univariate analysis on the usable dataset
- Split analysis into two angles: candidate profile factors vs political history factors
- Ran statistical tests to compare their influence on winning outcomes
- Summarized findings into a final report tab

**Key Finding:** A candidate's personal profile has a stronger influence on election results than their political history.

---

## 4. 🧭 Suicide Risk Patterns in India – Power BI Dashboard
*Power BI* | [View Project →](https://github.com/IamRaNo/DataPortfolio/tree/main/Suicide%20Risk%20Patterns%20in%20India)

**Problem:** Are suicides in India truly random, or do clear patterns exist among specific groups and regions?

**Process:**
- Cleaned and structured demographic-level suicide data for Power BI modeling
- Built a 4-page report covering national trends, demographic splits, and regional patterns
- Used DAX measures and visual drill-downs to surface high-risk group combinations

**Key Finding:** Unmarried students with 10th-grade education are the highest-risk group.

---

*If this is a sensitive topic for you personally, it's worth talking to someone you trust or a mental health professional — I'm happy to help find resources if that'd be useful.*
