# Script to obtain SILO point data and run statistical calculations based on date range

A Jypyter Notebook to obtain and run stats on historical weather data for point locations. It obtains open data from the [Queensland Goverment's SILO API](https://www.longpaddock.qld.gov.au/silo/). 

Originally designed to support a project using sheep drench data, this script can be used for any purpose where locations and dates are provided by an input dataset (Excel or CSV file format) and a date is specified. The outputs from statistical calculations on values such as temperature, rainfall and others across the specified date range are then appended to the input dataset (alternatively CSV file). Some sample code to plot the dataset is also provided.

For details of available weather data from the point API, please refer to the Queensland Government [SILO API Reference](https://www.longpaddock.qld.gov.au/silo/api-documentation/reference/#PointData).

## Requirements

- A user name and password for the SILO API. Note that an email address with blank password now suffices
- Rename sample config_sample.json as config.json and populate values for silo_user and silo_pw
- install Python libs as required (refer imports section)
- if using excel import/export, install openpyxl (used by pandas)


## Input

The import script was written to work with an excel file or a csv input file (refer cell 5). It is assumed that the file contains a latitude, longitude and a date (which will be the END date for the date range for the SILO API call). 

Please refer to "Specify settings" section and update as required to match your input file.

## Output

The script output is a new spreadsheet containing all values from the input file with the stats from the SILO weather data appended.

The start date for the date range is calculated using the input rows from the specified date column and the specified date range (daysToFetch).  

### Notes

There are commented out lines for additional test output, such as the complete SILO record returned from the API, just the weather data with the metadata stripped out, and the stats outputs. Use for testing or alternative output.

A folium map can be created with the last cells in the notebook. The currently just shows the locations of the points in the input spreadsheet, and the popups are populated from various values.
