# Stock Market Headlines Sentiment Analysis

**NLP-based sentiment analysis of stock market news headlines to correlate sentiment scores with price movements.**

## Project Overview

This project uses Natural Language Processing (NLP) techniques to analyze sentiment from stock market news headlines and examines the correlation between sentiment scores and stock price movements. The tool provides automated sentiment analysis of financial news to support investment decision-making and market analysis.

## Objectives

- Extract and analyze sentiment from financial news headlines
- Correlate sentiment scores with stock price movements
- Compare different sentiment analysis approaches
- Provide insights for market sentiment trends

## Key Features

- **News Data Collection**: Scrape headlines from financial news sources
- **Sentiment Analysis**: Apply multiple NLP models including VADER and TextBlob
- **Stock Price Integration**: Fetch stock price data for correlation analysis
- **Data Visualization**: Generate charts showing sentiment trends and correlations
- **Statistical Analysis**: Perform correlation analysis between sentiment and price movements

## Technologies Used

- **Python 3.8+**
- **NLP Libraries**: NLTK, TextBlob, VADER
- **Data Collection**: BeautifulSoup4, Requests
- **Data Analysis**: Pandas, NumPy, Scikit-learn
- **Visualization**: Matplotlib, Seaborn
- **Financial Data**: yfinance API

## Installation

### Prerequisites
- Python 3.8 or higher

### Setup Instructions

1. Clone the repository:
```bash
git clone https://github.com/achoreim/stock-market-headlines-sentiment-analysis.git
cd stock-market-headlines-sentiment-analysis
```

2. Install required packages:
```bash
pip install -r requirements.txt
```

3. Download NLTK data:
```python
import nltk
nltk.download('vader_lexicon')
nltk.download('punkt')
```

## Usage

### Basic Example

```python
from sentiment_analyzer import StockSentimentAnalyzer

# Initialize analyzer
analyzer = StockSentimentAnalyzer()

# Analyze sentiment for a stock
ticker = "AAPL"
results = analyzer.analyze_stock_sentiment(ticker, days=30)

# Generate visualization
analyzer.plot_sentiment_vs_price(results)
```

### Command Line Interface

```bash
# Analyze single stock
python main.py --ticker AAPL --days 30

# Analyze multiple stocks
python main.py --tickers AAPL,GOOGL,MSFT --days 7
```

## Project Structure

```
stock-market-headlines-sentiment-analysis/
├── src/
│   ├── data_collection/
│   ├── sentiment_analysis/
│   ├── analysis/
│   └── visualization/
├── data/
├── notebooks/
├── tests/
├── requirements.txt
└── main.py
```

## Methodology

### Data Collection
- News headlines scraped from financial websites (FinViz, Yahoo Finance)
- Stock price data retrieved using yfinance API
- Data synchronized by timestamp for accurate correlation

### Sentiment Analysis
- **VADER**: Rule-based sentiment analysis for social media text
- **TextBlob**: Pattern-based sentiment analysis with polarity scoring
- **Ensemble Approach**: Combination of multiple models for robust results

### Analysis
- Pearson and Spearman correlation coefficients
- Statistical significance testing
- Time-lag analysis for delayed sentiment effects

## Example Results

### Sentiment Distribution
```
Positive Headlines: 45.2%
Negative Headlines: 31.8%
Neutral Headlines: 23.0%
Average Sentiment Score: 0.127
```

### Correlation Analysis
```
AAPL: Sentiment-Price Correlation = 0.34 (p < 0.05)
GOOGL: Sentiment-Price Correlation = 0.28 (p < 0.05)
TSLA: Sentiment-Price Correlation = 0.52 (p < 0.01)
```

## Key Findings

- News sentiment shows strongest correlation with same-day price movements
- Technology stocks demonstrate higher sentiment-price correlations
- High sentiment scores often coincide with increased trading volume
- Model ensemble approach provides more reliable results than individual models

## Dependencies

Core requirements include:
- pandas >= 1.3.0
- numpy >= 1.21.0
- nltk >= 3.6
- textblob >= 0.15.3
- yfinance >= 0.1.63
- beautifulsoup4 >= 4.9.3
- matplotlib >= 3.4.0
- seaborn >= 0.11.0

## Testing

Run tests to verify functionality:

```bash
# Run all tests
python -m pytest tests/

# Run with coverage
python -m pytest --cov=src tests/
```

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests for new functionality
5. Submit a pull request

Please ensure code follows PEP 8 style guidelines.

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Contact

**Author**: [Ahmad Choreim]
- GitHub: [@achoreim](https://github.com/achoreim)
- Email: AhmadChoreim@gmail.com

## Acknowledgments

- FinViz for financial news data
- Yahoo Finance for stock price data
- NLTK team for natural language processing tools
- Open-source Python community

## Future Work

- Real-time sentiment analysis dashboard
- Integration with additional news sources
- Advanced deep learning models
- Sentiment-based trading strategy development