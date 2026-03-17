# GeoJSON Parcel Processor

Python tool for merging cadastral GeoJSON and ownership tables into GIS-ready parcel outputs.

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![GeoJSON](https://img.shields.io/badge/GeoJSON-000000?style=flat)
![QGIS](https://img.shields.io/badge/QGIS-589632?style=flat&logo=qgis&logoColor=white)

---

## Overview

This project automates the integration of parcel geometries and ownership tables to produce an enriched GeoJSON output ready for use in GIS software such as QGIS.

The workflow was developed as a programming project during the SIGMA MSc, but the result is a practical GIS utility:

- reads cadastral GeoJSON data
- reads ownership data from CSV
- matches parcel identifiers across both sources
- creates a final GeoJSON with ownership attributes
- exports inconsistency tables for QA and debugging

---

## What the tool produces

Main outputs:

- `proprietaires.geojson` — final GIS-ready parcel layer with ownership information
- `parcelles_edited.csv` — normalized ownership table used during processing
- `inconsistencies_csv.csv` — parcels found in the CSV but missing in the GeoJSON
- `inconsistencies_json.csv` — parcels found in the GeoJSON but missing in the CSV
- `project.log` — execution log for troubleshooting

---

## Repository structure

```text
geojson-parcel-processor/
|-- main.py
|-- gui.py
|-- csv_handler.py
|-- geojson_handler.py
|-- config_manager.py
|-- utils.py
|-- config.ini
|-- data/
|-- bonus/
|-- docs/
`-- README.md
```

---

## How it works

1. Read the ownership CSV and normalize parcel identifiers.
2. Read the cadastral GeoJSON.
3. Join ownership information to parcel geometries.
4. Export the enriched GeoJSON.
5. Report mismatches between both sources.

The codebase includes logging, configuration management, and basic error handling to make the workflow easier to run and debug.

---

## Ways to run the project

### Command line

```bash
python main.py
```

### GUI

```bash
python gui.py
```

### QGIS integration

The `bonus/` folder also includes material for visualizing outputs directly in QGIS.

---

## Why this repo matters

This repository shows:

- practical Python applied to GIS workflows
- geospatial ETL logic using real cadastral data
- configurable processing with logging and QA outputs
- a small but useful bridge between tabular and spatial data

---

## License

This project is licensed under the Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License.
