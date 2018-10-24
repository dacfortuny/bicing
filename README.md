# bicing scrapper (prototype)

Reads data from the bicing API and saves it in CSV files:

- One single CSV file storing information about the stations.
- One CSV file for each station containing the information updated every minute.

The prototype is coded in a **Jupyter Notebook**.

## Configuration parameters
 * `BICING_URL`: URL of the bicing API.
 * `OUTPUT_PATH`: Path in which store the output CSV files.
 * `STATIONS_FILE`: Name of the CSV file containing the information about the stations.
 
### Configuration example
```
BICING_URL = "http://wservice.viabicing.cat/v2/stations"
OUTPUT_PATH = "output"
STATIONS_FILE = "output/stations.csv"
```
