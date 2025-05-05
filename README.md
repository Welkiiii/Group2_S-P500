# S&P 500 Company Growth Classification 

## Project Background
In today's volatile markets, identifying companies with high growth potential is critical for investors and policymakers. This project leverages machine learning to classify S&P 500 companies intov **`growth categories`** based on their financial and operational characteristics. The insights can support:
- ​**Investment decisions**​ (identifying high-growth stocks)
- ​**Economic trend analysis**​ (sector/region performance)
- ​**Corporate benchmarking**​ (comparing against peers)

## Dataset: S&P 500 Companies
A comprehensive collection of financial and operational metrics for major US companies, with focus on technology sector constituents.

### Key Features
| Feature | Description | Type |
|---------|-------------|------|
| ​**Exchange**​ | Stock exchange listing (NYSE/NASDAQ) | Categorical |
| ​**Symbol**​ | Unique ticker symbol (e.g., AAPL) | Identifier |
| ​**Shortname**​ | Abbreviated company name | Text |
| ​**Longname**​ | Full legal company name | Text |
| ​**Sector**​ | Broad economic category (e.g., Technology) | Categorical |
| ​**Industry**​ | Specific business classification (e.g., Semiconductors) | Categorical |
| ​**Current price**​ | Latest trading price (USD) | Numerical |
| ​**Market Cap**​ | Total company valuation (USD billions) | Numerical |
| ​**EBITDA**​ | Earnings before interest/tax/depreciation/amortization | Numerical |
| ​**Revenue growth**​ | Year-over-year revenue change (%) | Numerical |
| ​**City**​ | Headquarters location | Categorical |
| ​**State**​ | Headquarters state | Categorical |
| ​**Country**​ | Headquarters country | Categorical |
| ​**Full_time employees**​ | Total permanent staff count | Numerical |
| ​**Long business summary**​ | Company description (50-200 words) | Text |
| ​**Weight**​ | Index weighting percentage | Numerical |

### Target Variable
**Revenue Growth**, our target variable, measures the percentage change in a company's revenue over a given period, reflecting financial performance. Analyzing its distribution among S&P 500 companies, we classified growth into five categories: **Declining** (negative growth), **Low Growth (0–5%)**, **Moderate Growth** (5–15%, largest segment at 33.9%), **High Growth** (15–30%), and **Hyper Growth** (>30%). This categorization highlights different levels of company performance, enabling focused analysis and strategic decision-making.

## Project workflow

### 1. Data Preparation

### 2. Feature Selection
#### Dataset after feature selction

| Feature | Description | Type |
|---------|-------------|------|
| ​**Symbol**​ | Unique ticker symbol (e.g., AAPL) | Identifier |
| ​**Industry**​ | Specific business classification (e.g., Semiconductors) | Categorical |
| ​**Current price**​ | Latest trading price (USD) | Numerical |
| ​**City**​ | Headquarters location | Categorical |
| ​**Full_time employees**​ | Total permanent staff count | Numerical |
| ​**Weight**​ | Index weighting percentage | Numerical |
| ​**Growth_Category**​ | Revenue growth classification (5-level Declining/Low/Moderate/High/Hyper) |  Target variable |

### 3. Feature engineering

### 4. Model training

### 5. Model evaluation
