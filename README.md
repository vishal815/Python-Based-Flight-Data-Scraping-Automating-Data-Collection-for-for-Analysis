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
- **Data Visualization**: Enhances the presentation of extracted data using plots and graphs to provide insights into flight trends.

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
pip install selenium beautifulsoup4 pandas matplotlib seaborn
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
   - Cleans and formats the extracted data.
6. **Save to CSV**:
   - Stores the extracted data in a CSV file for further use.
7. **Visualize Data**:
   - Uses Python libraries like Matplotlib and Seaborn to create visual representations of the data, such as:
     - Bar charts for price comparison between airlines.
     - Line plots for flight duration trends.

---


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
| Airline           | Departure Time | Departure Airport | Arrival Time | Arrival Airport | Flight Duration | Stops    | Price (INR)   |
|-------------------|----------------|-------------------|--------------|-----------------|-----------------|----------|---------|
| Srilankan Airlines| 18:35          | DEL               | 21:50        | DXB             | 28h 45m         | 1 Stop   | 25,662  |
| IndiGo            | 17:30          | DEL               | 14:35        | SHJ             | 22h 35m         | 1 Stop   | 25,677  |

---

## Data Visualization
### Why Visualize?
- Visualization makes it easier to identify trends and patterns in the flight data.
- Provides actionable insights for travel planning, such as:
  - Identifying the most cost-effective airline.
  - Observing peak travel times.

### Example Visualizations
1. **Price Distribution**:
   - A histogram to display the frequency of flight prices.
2. **Airline Comparison**:
   - A bar chart comparing average prices across airlines.
3. **Flight Duration Trends**:
   - A line plot to observe how flight durations vary with stops.

---

## Challenges
1. **Dynamic Loading**:
   - The website uses JavaScript to dynamically load flight details, requiring Selenium for rendering.
2. **Data Cleaning**:
   - Formatting time strings and handling cases like `+1 Day` or `+0 Day`.

---

## Future Enhancements
- Add error handling for network or browser-related issues.
- Automate handling of dynamic date and destination inputs.
- Enhance scraping to include additional data such as baggage allowance.

---

