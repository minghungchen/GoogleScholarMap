> A collection of Python scripts to generate a map of countries from which a scholar is cited.

Tested with: Python 3.9.6 on Mac OS

This repo was patched for the latest Python modules available on 2024/3/27.
The requirements.txt is provided to ensure the patched codes can run.

Note: I only used Scholar citations and Citation locations. Impact chart can run but not tested.


## Usage:

### 1. Scholar citations

To fetch the list of citations of an author run:

```shell
python3 -m scholar_map.get_scholar -i SCHOLAR_ID -o OUTPUT_DIR
```

where `SCHOLAR_ID` is the ID of the Google Scholar profile / user. The profile ID is the string appearing
after "https://scholar.google.com/citations?user=".

### 2. Citation locations

To process all citations and fetch the locations of the citing authors, run:

```shell
python3 -m scholar_map.get_locations -o OUTPUT_DIR
```

This will generate a `locations.csv` file in `OUTPUT_DIR` containing a table with institutions and countries from which
the publications are cited, including latitude and longitude coordinates.
See https://support.google.com/mymaps/answer/3024836 on how to create a map and import coordinates from this file in
Google Maps.

Steps:
- Go to https://mymaps.google.com/ to create a new layer
- Add a new layer and click Import
- Select latitude and longitude to import, and select name as name
- Now you have the map layer ready

### 3. Impact chart

To generate detailed information about the institutions and countries citing each publication, run:

```shell
python3 -m scholar_map.get_impact_chart -i SCHOLAR_ID -o OUTPUT_DIR
```

and then check the file generated in `OUTPUT_DIR` named `impact_chart.csv`. 
