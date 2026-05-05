# Real Estate Scraper Project 🏠

This project scrapes real estate listings from major platforms like **99acres** (India) and **Fotocasa** (Spain) using **ScraperAPI** to bypass bot detection and JavaScript rendering.

## 🚀 Features
- **Multi-City Support**: Scrapes data for cities like Delhi and Mumbai.
- **Bot Bypass**: Uses ScraperAPI with custom country codes and rendering options.
- **Data Cleaning**: Includes a robust price parser that converts strings (e.g., '1.5 Cr', '85 Lac') into standardized numeric INR values.
- **Export**: Automatically saves cleaned data to `99acres_clean_data.csv`.

## 🛠️ Setup
1. **API Key (Secure)**: Create a `.env` file in project root and add:
   - `SCRAPERAPI_KEY=your_key_here`
   - Notebook reads key from `.env`; no hardcoded key in code.
2. **Libraries**:
   - `requests` for API calls.
   - `BeautifulSoup` for HTML parsing.
   - `pandas` for data manipulation.
   - `matplotlib` for basic visualization.

## 📊 Data Pipeline
1. **Extraction**: Fetching raw HTML via ScraperAPI proxies.
2. **Parsing**: Identifying property cards using CSS selectors and extracting Title, Price, and Location.
3. **Transformation**: Normalizing price units (Cr/Lakh) to a single numeric column.
4. **Storage**: Exporting to CSV for further analysis.

## 🔄 Real-Time Scraping & Historical Tracking
- **Live Data**: Each notebook run fetches current prices from 99acres
- **Timestamp**: Every scrape is tagged with date/time (`Scraped_Date` column)
- **Historical Archive**: Timestamped backups saved as `99acres_historical_YYYYMMDD_HHMMSS.csv`
- **Trend Analysis**: Main CSV (`99acres_clean_data.csv`) appends new data for price history comparison

## 🔍 Selector Optimization
- **Robust CSS Selectors**: Multiple fallback selectors ensure compatibility as 99acres updates its HTML
- **Diagnostic Tool**: Run the diagnostic cell to verify which selectors work on current page structure
- **Data Validation**: Only valid records (with proper Title) are appended to results
- **Better Error Handling**: Graceful fallbacks if selectors don't match

---
