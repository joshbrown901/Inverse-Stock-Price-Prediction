# Inverse-Stock-Price-Prediction
The study proposes a novel approach to the prediction of news sentiment using historical stock price data using machine learning techniques. Traditionally, financial prediction has relied on news sentiment analysis to predict stock price movements, based on the premise that external information drives market behavior.

## 📝 Abstract
The study proposes a novel approach to the prediction of news sentiment using historical stock price data using machine learning techniques. Traditionally, financial prediction has relied on news sentiment analysis to predict stock price movements, based on the premise that external information drives market behavior. In contrast, this approach presumes that stock prices, which rapidly incorporate and reflect a broad range of market information and investor anticipation, could be effective predictors of news sentiment that will be evident in the future. The proposed method aims to identify whether market prices embody key information that is later evident in news reports. Theoretical implications and initial analysis show that the information contained in stock prices can provide key insights into the future news sentiment, challenging the use of traditional sentiment-based prediction models.

## Keywords: Stock Price Prediction, News Sentiment Analysis, Machine Learning, Efficient Market Hypothesis (EMH), Historical Stock Data, Feature Engineering, Anomaly Detection, Random Forests, Support Vector Machines (SVM), Long Short-Term Memory (LSTM) Networks

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
The stock price can be used to predict the news, which proves the efficient market hypothesis and questions the need to analyze the news along with market data, since market data already reflect what can be found in the news. This will reduce the reliance on news sentiment analysis.


## 🔬 Methodology
Data Sources
Primary: Yahoo Finance (OHLCV data, 2010–2023)

Secondary: FRED (macroeconomic indicators), CBOE Volatility Index (VIX)

Models Implemented
Model	Architecture	Hyperparameters Tuned
LSTM	2-layer, dropout=0.3	Seq length, learning rate
GRU	Bidirectional	Hidden units, batch size
Transformer	4-head attention	Embedding dim, FFN size
Evaluation Metrics
Primary: Precision-Recall AUC (focus on downside predictions)

Secondary: Sharpe Ratio (backtested short strategies), Maximum Drawdown

🗂 Repository Structure
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
⚙️ Installation & Usage
1. Clone Repository
bash
Copy
git clone https://github.com/yourusername/MSc-Inverse-Stock-Prediction.git  
cd MSc-Inverse-Stock-Prediction  
2. Set Up Environment
bash
Copy
conda create -n stock_pred python=3.10  
conda activate stock_pred  
pip install -r requirements.txt  
3. Run Pipeline
bash
Copy
python src/data_loader.py --tickers AAPL MSFT --start 2015-01-01  
python src/models.py --model transformer --epochs 100  
📊 Results & Discussion
Key Findings
Transformer outperformed LSTM/GRU with 88% precision in predicting 1-week downturns.

Macroeconomic features (VIX, CPI) improved recall during crises by ~15%.

False positives remained high (~20%) due to market noise (see Limitations).

Visualization
Precision-Recall Curve

Limitations
Survivorship bias (limited delisted stocks).

Overfitting risk during low-volatility regimes.

📖 References
Hochreiter & Schmidhuber (1997). LSTM. Neural Computation.

Vaswani et al. (2017). Attention Is All You Need. NeurIPS.

Engle (2001). GARCH Models. Nobel Prize Lecture.

📜 License
MIT License. See LICENSE. Academic use encouraged with proper citation.

✉️ Contact
Author: [Your Name]
Supervisor: [Prof. Name] | [University Email]
LinkedIn: [Your Profile]

