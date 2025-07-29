# PakWheels Used Bikes Data Scraper

## Project Description
This notebook implements a complete web scraping solution to collect used motorcycle listings from Pakistan's largest automotive marketplace, PakWheels.com.

## Features
- **Large-scale Data Collection**:
  - Scrapes 701 pages of listings
  - Collects 17,913 bike entries
- **Comprehensive Data Fields**:
  - Bike name and model
  - Price (in PKR)
  - Model year
  - Mileage
  - City location
- **Data Processing**:
  - HTML parsing with BeautifulSoup
  - Data structuring with Pandas
  - Automatic CSV export

## Technical Implementation
```python
# Core scraping logic
for page in range(1, max_pages + 1):
    url = f"{base_url}?page={page}"
    try:
        response = requests.get(url, headers=headers, timeout=10)
        soup = BeautifulSoup(response.text, "html.parser")
        # Data extraction here...
    except requests.RequestException as e:
        print(f"Error on page {page}: {e}")
        continue
