# Drivenest-task
# Data Scraping Project

This project involves scraping data from a webpage using two methods:
1. **Instant Data Scraper Chrome Extension**
2. **Python Script in Jupyter Notebook**

The scraped data is saved in separate Excel files for each method.

## Prerequisites

- Google Chrome browser
- Instant Data Scraper Chrome extension
- Jupyter Notebook
- Python 3.x
- Required Python libraries: `pandas`, `openpyxl`, `beautifulsoup4`, `requests`

## Method 1: Using Instant Data Scraper Chrome Extension

### Steps

1. **Install the Instant Data Scraper Extension:**
   - Open Google Chrome.
   - Go to the Chrome Web Store and search for "Instant Data Scraper".
   - Click "Add to Chrome" to install the extension.

2. **Scrape Data:**
   - Open the webpage you want to scrape in Google Chrome.
   - Click on the Instant Data Scraper extension icon in the Chrome toolbar.
   - The extension will automatically detect data patterns on the page. Review the detected data.
   - Click "Start Crawling" if you want to scrape multiple pages or "Download Data" to save the data.
   - The data will be downloaded as a CSV file.

3. **Save Data to Excel:**
   - Open the downloaded CSV file using Excel.
   - Save it as an Excel file (`.xlsx`) for better integration with other tools.

### Example

1. **Install the Extension:**
   - ![Install Extension](images/install_extension.png) *(Placeholder for the image)*

2. **Scrape Data:**
   - ![Scrape Data](images/scrape_data.png) *(Placeholder for the image)*

3. **Save Data to Excel:**
   - ![Save to Excel](images/save_to_excel.png) *(Placeholder for the image)*

## Method 2: Using Python Script in Jupyter Notebook

### Steps

1. **Set Up Your Environment:**
   - Ensure you have Python 3.x installed.
   - Install the required libraries using the following commands:
     ```bash
     pip install pandas openpyxl beautifulsoup4 requests
     ```

2. **Create and Run the Jupyter Notebook:**
   - Open Jupyter Notebook.
   - Create a new notebook and copy the following script into a cell:

     ```python
     import requests
     from bs4 import BeautifulSoup
     import pandas as pd

     # URL of the webpage to scrape
     url = "https://example.com"

     # Send a GET request to the webpage
     response = requests.get(url)

     # Parse the content of the request with BeautifulSoup
     soup = BeautifulSoup(response.content, 'html.parser')

     # Find the data you need to scrape
     data = []
     for item in soup.select('.my_border.ngo_listing_div'):
         name = item.select_one('.name_class').get_text(strip=True)
         address = item.select_one('.address_class').get_text(strip=True)
         data.append({'Name': name, 'Address': address})

     # Create a DataFrame from the data
     df = pd.DataFrame(data)

     # Save the data to an Excel file
     df.to_excel('scraped_data_python.xlsx', index=False)

     print("Data scraped and saved to scraped_data_python.xlsx")
     ```

3. **Run the Script:**
   - Execute the cell with the script.
   - The data will be scraped and saved to `scraped_data_python.xlsx`.

### Example

1. **Set Up Your Environment:**
   - ![Set Up Environment](images/setup_environment.png) *(Placeholder for the image)*

2. **Create and Run the Notebook:**
   - ![Run Notebook](images/run_notebook.png) *(Placeholder for the image)*

3. **Save Data to Excel:**
   - ![Save to Excel](images/save_to_excel_python.png) *(Placeholder for the image)*

## Conclusion

You have successfully scraped data from a webpage using both the Instant Data Scraper Chrome extension and a Python script in a Jupyter notebook. The data is saved in separate Excel files for each method.
