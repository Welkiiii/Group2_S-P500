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

## Target Variable
Revenue Growth refers to the percentage increase or decrease in a company's revenue over a defined period of time. It serves as a critical indicator of a company's financial health and market performance. In our analysis, we utilize revenue growth as our primary target variable to evaluate and classify companies into distinct performance categories: High, Middle, Low, and Negative. This classification allows us to effectively assess and compare the companies' growth potential and operational success within the context of the S&P 500 dataset.

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
