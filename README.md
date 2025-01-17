# Assignment 2: Web Scraping Travel Website

This project is a Python-based web scraping script designed to extract flight details from the Yatra travel website. The extracted data includes flight pricing, origin, destination, departure and arrival times, and duration. The data is then saved into a CSV file for further analysis or reporting.

---

## Project Overview

### Objective
The main objective of this assignment is to:
- Scrape data from a travel website.
- Extract relevant flight details such as:
  - Airline name
  - Departure time and airport
  - Arrival time and airport
  - Flight duration
  - Stops
  - Price
- Save the extracted data into a CSV file.

### Website Link
[Yatra Travel Website](https://www.yatra.com/react-home?utm_source=google&utm_medium=search&utm_campaign=brand&_gcl&utm_source=google&utm_medium=cpc&utm_campaign=&gad_source=1&gclid=CjwKCAiAnKi8BhB0EiwA58DA4Zz-7jGgd_iYFy2_G24BxbawgSlicnOm4iTH-cmkuU-DhZODRfFNjhoCEDgQAvD_BwE)

---

## Features
- **Automated Web Scraping**: Uses Selenium and BeautifulSoup to navigate and parse the website's HTML content.
- **Flight Details Extraction**: Extracts key information such as airline names, times, airports, flight duration, stops, and prices.
- **Data Cleaning**: Handles formatting and cleaning of data, such as removing unnecessary characters (e.g., `+1 Day`).
- **CSV Export**: Saves the extracted data into a CSV file for easy access and further analysis.

---

## Requirements

### Prerequisites
Make sure you have the following installed:
- Python 3.8+
- Google Chrome browser
- ChromeDriver (compatible with your Chrome version)

### Python Libraries
Install the required Python libraries using the following command:
```bash
pip install selenium beautifulsoup4 pandas
```

---

## How It Works

### Script Workflow
1. **Set Up Selenium WebDriver**:
   - The script initializes the Selenium WebDriver to open and navigate the website.
2. **Load Website**:
   - Navigates to the Yatra flight search page.
3. **Parse HTML Content**:
   - Uses BeautifulSoup to parse the loaded webpage.
4. **Extract Flight Details**:
   - Scrapes flight details such as airline names, times, prices, and other relevant information.
5. **Data Cleaning**:
   - Cleans and formats the extracted data to ensure accuracy.
6. **Save to CSV**:
   - Stores the extracted data in a CSV file for further use.

---

## Code Snippet
Below is a brief overview of the core functionality:

```python
from selenium import webdriver
from selenium.webdriver.chrome.service import Service
from bs4 import BeautifulSoup
import pandas as pd
import time
import re

# Set up Selenium WebDriver
chromedriver_path = "path/to/chromedriver"
service = Service(chromedriver_path)
driver = webdriver.Chrome(service=service)

# URL to scrape
url = "https://flight.yatra.com/air-search-ui/int2/trigger?flex=0&viewName=normal&source=fresco-flights&type=O&class=Economy&ADT=1&CHD=0&INF=0&noOfSegments=1&origin=DEL&originCountry=IN&destination=DXB&destinationCountry=AE&flight_depart_date=18/01/2025&arrivalDate="

driver.get(url)
time.sleep(14)  # Wait for the page to load
html_content = driver.page_source
driver.quit()

# Parse HTML with BeautifulSoup
soup = BeautifulSoup(html_content, 'html.parser')

# Extract flight details
flight_data = []
flight_containers = soup.find_all('div', class_='airline-holder clearfix')

for container in flight_containers:
    pass  # Add extraction logic here

# Save to CSV
pd.DataFrame(flight_data).to_csv('flight_data.csv', index=False)
```

---

## Output
The script generates a CSV file (`flight_data.csv`) with the following columns:
- Airline
- Departure Time
- Departure Airport
- Arrival Time
- Arrival Airport
- Flight Duration
- Stops
- Price

### Example Output
| Airline           | Departure Time | Departure Airport | Arrival Time | Arrival Airport | Flight Duration | Stops    | Price   |
|-------------------|----------------|-------------------|--------------|-----------------|-----------------|----------|---------|
| Srilankan Airlines| 18:35          | DEL               | 21:50        | DXB             | 28h 45m         | 1 Stop   | 25,662  |
| IndiGo            | 17:30          | DEL               | 14:35        | SHJ             | 22h 35m         | 1 Stop   | 25,677  |

---

## Challenges
1. **Dynamic Loading**:
   - The website uses JavaScript to dynamically load flight details, requiring Selenium for rendering.
2. **Data Cleaning**:
   - Formatting time strings and handling cases like `+1 Day` or `+0 Day (Non Stop)`.

---

## Future Enhancements
- Automate handling of dynamic date and destination inputs.
- Enhance scraping to include additional data such as baggage allowance.

---

This project is for educational purposes only.

