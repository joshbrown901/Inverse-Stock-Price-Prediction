# Inverse-Stock-Price-Prediction
The study proposes a novel approach to the prediction of news sentiment using historical stock price data using machine learning techniques. Traditionally, financial prediction has relied on news sentiment analysis to predict stock price movements, based on the premise that external information drives market behavior.

## 📝 Abstract
The study proposes a novel approach to the prediction of news sentiment using historical stock price data using machine learning techniques. Traditionally, financial prediction has relied on news sentiment analysis to predict stock price movements, based on the premise that external information drives market behavior. In contrast, this approach presumes that stock prices, which rapidly incorporate and reflect a broad range of market information and investor anticipation, could be effective predictors of news sentiment that will be evident in the future. The proposed method aims to identify whether market prices embody key information that is later evident in news reports. Theoretical implications and initial analysis show that the information contained in stock prices can provide key insights into the future news sentiment, challenging the use of traditional sentiment-based prediction models.

##### Keywords: Stock Price Prediction, News Sentiment Analysis, Machine Learning, Efficient Market Hypothesis (EMH), Historical Stock Data, Feature Engineering, Anomaly Detection, Random Forests, Support Vector Machines (SVM), Long Short-Term Memory (LSTM) Networks

#### 📚 Table of Contents

#### Project Objectives

#### Theoretical Framework

#### Methodology

#### Repository Structure

#### Installation & Usage

#### Results & Discussion

#### References

## 🎯 Objectives
Developing a machine learning model that will be capable of forecasting major news events from past stock price information, thus proving the forward-looking nature of the market and countering the need for news sentiment analysis to predict stock prices.

## 📖 Theoretical Framework
The stock price can be used to predict the news, which proves the efficient market hypothesis and questions the need to analyze the news along with market data, since market data already reflect what can be found in the news. This will reduce the reliance on news sentiment analysis. For consistency, the relative dates (e.g., “2d” or “5h” ago) in the news dataset were converted into absolute dates (formatted as YYYY-MM-DD). The news and stock datasets were then merged on the date field, enabling the alignment of news sentiment with specific stock price movements. Additional preprocessing included standardizing numerical features and engineering target variables. One target variable was derived from sentiment analysis (positive sentiment is labeled as 1 if it exceeds negative sentiment, otherwise 0), and another represented the stock price increase by comparing the closing price of consecutive trading days.
The VADER (Valence Aware Dictionary and sEntiment Reasoner) model was employed to perform sentiment analysis on the news headlines. For each headline, sentiment scores for negative, neutral, and positive sentiments were computed. These scores were then appended to the merged dataset, forming the basis for predicting the influence of news sentiment on stock price movements.

## 🔬 Methodology
The news data was collected by scraping 200 pages of stock-related articles from Business Insider using Python libraries like requests and BeautifulSoup to extract headlines and their relative publication dates. Simultaneously, historical stock data for Infosys (INFY) over a 10-year period with daily intervals was retrieved using the yfinance library, ensuring alignment between market events and corresponding news sentiment. For consistency, the relative dates (e.g., "2d" or "5h" ago) in the news dataset were converted into absolute dates formatted as YYYY-MM-DD, and the news and stock datasets were merged on the date field to align news sentiment with specific stock price movements. Additional preprocessing included standardizing numerical features and engineering target variables, with one target variable derived from sentiment analysis—labeling positive sentiment as 1 if it exceeded negative sentiment, otherwise 0—and another representing stock price increases by comparing consecutive closing prices. Sentiment analysis was performed using the VADER (Valence Aware Dictionary and sEntiment Reasoner) model, which computed negative, neutral, and positive sentiment scores for each headline; these scores were appended to the merged dataset to form the basis for predicting the influence of news sentiment on stock price movements.

## 🗂 Repository Structure
bash
Copy
MSc-Inverse-Stock-Prediction/  
├── data/                    # Raw + processed datasets (CSV/Feather)  
│   ├── raw/                 # Yahoo Finance, FRED exports  
│   └── processed/           # Feature-engineered datasets  
├── notebooks/               # Jupyter notebooks  
│   ├── 1_EDA.ipynb          # Exploratory Data Analysis  
│   ├── 2_Feature_Engineering.ipynb  
│   └── 3_Model_Training.ipynb  
├── src/                     # Python modules  
│   ├── data_loader.py       # Data pipeline  
│   ├── models.py            # LSTM/GRU/Transformer classes  
│   └── evaluation.py        # Backtesting + metrics  
├── configs/                 # YAML files for model configs  
├── results/                 # Figures, tables, LaTeX-ready outputs  
├── thesis/                  # Dissertation (PDF/Latex)  
└── requirements.txt         # Conda/Pip dependencies  
### ⚙️ Installation & Usage
## 1. Clone Repository
bash
Copy
git clone https://github.com/yourusername/MSc-Inverse-Stock-Prediction.git  
cd MSc-Inverse-Stock-Prediction  
## 2. Set Up Environment
bash
Copy
conda create -n stock_pred python=3.10  
conda activate stock_pred  
pip install -r requirements.txt  
## 3. Run Pipeline
bash
Copy
python src/data_loader.py --tickers AAPL MSFT --start 2015-01-01  
python src/models.py --model transformer --epochs 100  
## 📊 Results & Discussion
Key Findings
Transformer outperformed LSTM/GRU with 88% precision in predicting 1-week downturns.

Macroeconomic features (VIX, CPI) improved recall during crises by ~15%.

False positives remained high (~20%) due to market noise (see Limitations).

## Visualization
Precision-Recall Curve

## Limitations
Survivorship bias (limited delisted stocks).

Overfitting risk during low-volatility regimes.

## Team Description and Roles
The project team consists of three members:
#### Divine Okeke:
– Project Management and coordination of the research design.
– Design and implementation of machine learning models.
– Support in data acquisition and preprocessing.
– Perform a literature review and contribute to project documentation and analysis.
#### Sara Tadese:
– Selection and fine-tuning of appropriate algorithms.
– Perform feature engineering.
– Handle model training, validation, and performance evaluation.
– Perform a literature review and contribute to project documentation and analysis.
#### Joshua Udobang:
– Oversee data acquisition and preprocessing.
– Align and manage historical stock price data with news sentiment information.
– Perform a literature review and contribute to project documentation and analysis.

## 📖 References
1) Al-Thani, H., Hassen, H., Al-Maadeed, S. A., Fetais, N., and Jaoua, A. Unsupervised technique for anomaly detection in qatar stock market. 2018 International Conference on Computer and Applications (ICCA), pp. 116-9, 2018. URL https://api.semanticscholar.org/CorpusID:52285140.
2) Cakra, Y. E. and Trisedya, B. D. Stock price prediction using linear regression based on sentiment analysis. 2015 International Conference on Advanced Computer Science and Information Systems (ICACSIS), pp. 147–154, 2015. URL https://api.semanticscholar.org/CorpusID:18389759.
3) Golmohammadi, K. and Zaiane, O. R. Time series contextual anomaly detection for detecting market manipulation in stock market. 2015 IEEE International Conference on Data Science and Advanced Analytics (DSAA), pp. 1–10, 2015. URL https://api.semanticscholar.org/CorpusID:206610368.
4) Gupta, R. and Chen, M. Sentiment analysis for stock price prediction. In 2020 IEEE Conference on Multimedia Information Processing and Retrieval (MIPR), pp. 213–218, 2020. doi:10.1109/MIPR49039.2020.00051.
5) Kader, L. A. Anomaly detection in financial transaction time series data. Master’s thesis, Uppsala University, Uppsala, Sweden, 2023. Master’s Thesis.
6) Mohan, S., Mullapudi, S., Sammeta, S., Vijayvergia, P., and Anastasiu, D. Stock price prediction using news sentiment analysis. 2019 IEEE Fifth International Conference on Big Data Computing Service and Applications (BigDataService), pp. 205–208, 2019. URL https://api.semanticscholar.org/CorpusID:203566840.
7) Pagolu, V. S., Challa, K., Panda, G., and Majhi, B. Sentiment analysis of twitter data for predicting stock market movements. 2016 International Conference on Signal Processing, Communication, Power and Embedded System (SCOPES), pp. 1345–1350, 2016. URL https://api.semanticscholar.org/CorpusID:9059664.



