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
#### 2.1 Remove Unwanted Attributes
Columns like Exchange, Shortname and others are dropped as they don't contribute to analyzing company growth. This initial cleanup streamlines the dataset for further analysis.
#### 2.2 Preliminary Feature Identification
Features are categorized into numerical and categorical types. This separation helps in applying different analysis methods tailored to each type, enabling a more targeted examination of the data.
#### 2.3 Feature Correlation Analysis
For numerical features, a correlation matrix is created and visualized. Features with high correlations, like Marketcap and Ebitda, are removed to avoid multicollinearity, thus enhancing the quality of features for model training.
#### 2.4 Statistical Significance Testing
chi - square test evaluates categorical features' significance. By encoding the features and calculating p - values, less significant ones, such as Country, are identified and removed, ensuring only relevant categorical information remains.
#### 2.5 Redundancy and importance analysis
Eliminate redundant features where one determines another (e.g., Sector based on Industry). Compare remaining features like City and State using a Random Forest model, and drop the less important one (State).
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
#### 3.1 Data loading
Load the sp500_for_engineering.csv dataset, setting Symbol as the index. Check data structure, including missing values and data types.
#### 3.2 Handling Missing Values
Fill missing values in the Fulltimeemployees column with the mean of each Industry group, reflecting industry - specific characteristics.
#### 3.3 Target Encoding with Kfold
First, we map the categorical Growth_Category labels to numerical values (0 - 4). Then, for high - cardinality categorical columns Industry and City, we apply a leakage - safe target encoding method. Using K - fold cross - validation, we calculate and map the mean of the target variable for each category, filling unknowns with the global mean to create encoded columns.
#### 3.4 Log - transforming Numerical Columns
To improve the distribution of numerical data, we apply log transformation to Currentprice and Fulltimeemployees using np.log1p(). Alongside this, we create ratio features like Price_per_employee and Log_PPE. These transformations and new features make the data more suitable for machine learning models and uncover meaningful relationships.
#### 3.5 Creating additional derive features
We generate several new features to capture diverse company aspects. Employees_per_million_usd shows the labor - price ratio. Binary features Is_large_employer and Is_expensive_stock compare values to the median. City_Industry_combo multiplies encoded columns to potentially reveal location - industry interactions.
### 4. Model training
#### 4.1 Train_test split
Split data into features (X) and the target variable (y). A set of engineered features is selected from the dataset. Then, the data is split into training and testing sets using train_test_split with a test size of 0.2 and a fixed random state for reproducibility. Additionally, the target variable in the test set is binarized using label_binarize for certain evaluation metrics.
#### 4.2 Hyperparameter Tuning 
Logistic Regression: GridSearchCV is used to find the best value of the regularization parameter C for Logistic Regression. The search is performed over a range of values ([0.01, 0.1, 1, 10), and the best model is selected based on the macro F1 - score. The best parameters and the corresponding best F1 - score are printed.
k - NN: Similar to Logistic Regression, GridSearchCV is employed for k - Nearest Neighbors classifier. The hyperparameter n_neighbors is tuned over the values [3 ,5 ,7] and the model with the best macro F1 - score is identified. The best parameters and score are printed.
Decision Tree: For the Decision Tree classifier, GridSearchCV is used to optimize the max_depth hyperparameter. The search is conducted over [3, 5, 10], and the best model based on the macro F1 - score is selected. The results are printed.
Random Forest: GridSearchCV is applied to the Random Forest classifier to tune two hyperparameters: n_estimators ([50, 100]) and max_depth ([5, 10]). The best model according to the macro F1 - score is determined, and the best parameters and score are printed.
### 5. Model evaluation
#### 5.1 evaluate_model function
It first trains the model on the training dataset and then makes predictions on the test set. The function calculates key metrics like accuracy and macro F1-score, prints a detailed classification report, generates and saves a confusion matrix for visualizing errors, and computes the ROC-AUC score if applicable, storing scores in dedicated dictionaries.
#### 5.2 Model Training and Comparision
A dictionary of various machine learning models, including hyperparameter-tuned ones and baseline models like Naive Bayes and XGBoost, is created. Two empty dictionaries are initialized to record model scores. The evaluate_model function is then looped through for each model, populating the score dictionaries, enabling a direct comparison of performance across different algorithms.
#### 5.3 Result visualization
Two bar plots are generated using seaborn to visually compare model performance. One plot showcases the macro F1-scores of all models, with model names on the x-axis and scores on the y-axis, titled "Model Comparison on Revenue Growth Category Prediction". The other plot displays the ROC-AUC scores, helping to quickly assess which models distinguish better between growth categories. 
