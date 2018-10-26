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

## Fields

In the stations file:

 * **internalId**: Internal ID, different for each station and for each version of each station (considering different versions those in which one of the following fiels differs from the former one: *id*, *type*, *streetName*, *streetNum*, *latitude*, *longitude*, *altitude*, *nearbyStations*. This corresponds with the name of the data file for each station.
 * **id**: Official id of the station.
 * **type**: Whether the bikes in the station are mechanical (**BIKE**) or electric (**BIKE-ELECTRIC**).
 * **streetName**: Street in which the station is located.
 * **streetNum**: Street number in which the station is located.
 * **latitude**: Latitude of the station.
 * **longitude**: Longitude of the station.
 * **altitude**: Altitude of the station in meters.
 * **nearbyStations**: Closer stations. These may change if one of them is out of order.
 
 In each of the data files, for which the name is the *internalId* found in the stations file:
 
 * **updateTime**: Datetime of the data row (in UTC).
 * **status**: Whether the station is working (**OPN**) or out of order (**CLS**).
 * **bikes**: Number of available working bikes.
 * **slots**: Number of working slots.
