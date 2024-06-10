### Minimal Parser for Cities data in GeoNames

Probably the most fragile script you'll ever find. I was after the timezone and country codes for each city and in it's current state it (almost) works. Tested it against cities500 data at the time of writing, provided here: https://download.geonames.org/export/dump/

Data gets parsed into the following columns in a CSV/TSV file<br>
* 'Name', 'Latitude', 'Longitude', 'Country Code', 'Timezone'

The script relies on the fact the first number that you encounter in a row will be the latitude entry, and the following one will be longitude. Country code and Timezone are matched against a pre-populated list within the script. Project uses pypoetry (https://python-poetry.org/) to install and manage dependencies.

Note: After extraction, I suggest sorting the data by each column, one at a time and observing the top and the bottom lines - this will most likely reveal if your columns have some unexpected data.

Note 2: Some of the cities have country code set to NA (Not Available, perhaps). Some of those are valid, being cities in Namibia. But the rest of them would need to be fixed manually
