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
Revenue Growth, our primary target variable, represents the percentage change in a company's revenue over a specified time period. This metric is fundamental in assessing the financial performance and operational vitality of companies within the S&P 500 dataset. Based on our analysis, we categorize companies into five distinct segments according to their revenue growth rates: Hyper Growth, High Growth, Moderate Growth, Low Growth, and Declining.

Our category analysis indicates a diverse distribution among the companies:

- Moderate Growth constitutes the largest segment, accounting for approximately 33.9% of the dataset, indicating steady but moderate increases in revenue.
- Low Growth companies, representing 25.1%, show minimal revenue increases, reflecting limited growth momentum.
- Declining companies, making up 24.8%, experienced reductions in revenue, signaling challenges or contraction in their market presence.
- High Growth companies comprise 11.6%, demonstrating strong and sustainable revenue increases, highlighting notable market performance.
- Hyper Growth firms, at 4.6%, represent a small yet distinct group achieving exceptionally high revenue growth, indicative of rapid expansion and substantial market potential.

This categorization provides valuable insights into the growth dynamics and financial health of the companies analyzed, enabling targeted strategic assessments and informed investment decisions.

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
