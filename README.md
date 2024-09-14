# NASA Coronal Mass Ejections (CME) and Geomagnetic Storms (GST) Data Analysis

This project involves fetching and analyzing Coronal Mass Ejections (CME) and Geomagnetic Storms (GST) data using NASA's DONKI API. The data includes CMEs that occurred between May 1, 2013, and May 1, 2024, and their linked geomagnetic storms. The goal is to merge these datasets and calculate the time it takes for a CME to cause a GST.

## Project Overview

The project is structured into several sections:
1. **Fetching CME Data**: Using NASA's DONKI API to fetch CMEs occurring between specified start and end dates.
2. **Fetching GST Data**: Similarly, fetching GST data from NASA's API within the same date range.
3. **Data Cleaning and Transformation**: Cleaning and expanding the linked events in the data to create connections between CMEs and GSTs.
4. **Data Merging**: Merging both datasets to find which CME events are linked to specific GST events.
5. **Time Calculation**: Computing the time difference between the CME start time and the corresponding GST start time.
6. **Exporting Results**: Saving the final results as a CSV file.

## Requirements

Before running this notebook, ensure you have the following dependencies installed:

- Python 3.x
- `pandas` for data manipulation
- `requests` for making API calls
- `dotenv` for loading environment variables
- `datetime` for handling time operations

## Environment Setup

1. Clone this repository or download the files.
2. Set up your environment variables by creating a `.env` file in the root directory. Include your NASA API key in this file:
    ```bash
    NASA_API_KEY=your_nasa_api_key
    ```
3. Install the required dependencies by running:
    ```bash
    pip install -r requirements.txt
    ```

## Running the Notebook

1. Open the Jupyter Notebook (`retrieve_data.ipynb`) in your preferred environment.
2. Run the cells sequentially to:
   - Fetch the CME and GST data.
   - Process and clean the data.
   - Compute the time difference between CME and GST events.
   - Export the final results to a CSV file.

## Key Sections in the Code

### Fetching CME Data

The CME data is retrieved using the NASA DONKI API. We specify the start and end dates for which the CMEs are requested. The response is stored in JSON format and then converted into a Pandas DataFrame for further analysis.

### Fetching GST Data

The GST data is also retrieved from the DONKI API for the same date range. The data is processed similarly, and we focus on linking these events to corresponding CMEs.

### Merging Data

Both datasets (CME and GST) are merged using a unique identifier, and the result is stored in a new DataFrame. This DataFrame contains only CMEs that are linked to GSTs.

### Time Calculation

A new column, `timeDiff`, is created by subtracting the start time of the CME from the start time of the GST, allowing us to analyze the time it takes for a CME to trigger a GST.

### Exporting Data

The final merged DataFrame is exported to a CSV file named `collected_data.csv` in the `output` folder.

## License

This project is open source and available under the MIT License.

## Author

Brian Hansen-Turton

