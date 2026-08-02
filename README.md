# tprc54_maps_scripts

## About

This repository contains the analysis code accompanying the paper *"Maps Without Witnesses: Closing the Participation Gap in FCC Mobile Broadband Challenges,"* submitted to TPRC54.

The FCC's Mobile Availability Challenge (MAC) process allows consumers, providers, and other stakeholders to formally dispute the accuracy of the National Broadband Map. However, participation in this process has been limited. This project investigates whether USPS mail carrier vehicles could serve as a passive, opportunistic measurement platform to help close this participation gap by evaluating the geographic overlap between USPS delivery routes, FCC MAC challenge locations, and crowdsourced Ookla speedtest data.

## Data Sources

- **FCC Mobile Availability Challenge data** — downloaded from the FCC Broadband Data Collection (BDC) portal
- **Ookla Speedtest Open Data** — quarterly mobile network performance data (2023 Q1–2025 Q4), obtained from Ookla for Good and via AWS S3
- **USPS EDDM Route Data** — carrier route geometries collected via the USPS Every Door Direct Mail (EDDM) GIS API
- **US Census Bureau** — TIGER/Line boundary files (state, tract, urban area) and American Community Survey (ACS) 2024 5-year income estimates

## To Use

The `notebooks/` folder contains the scripts used to produce the results and figures in the paper:

- `USPS_collection.ipynb` — collects USPS EDDM route data via the USPS GIS API
- `FCC_analysis.ipynb` — processes FCC MAC challenge hexagons and computes overlap with USPS routes
- `Ookla_analysis.ipynb` — processes Ookla speedtest tiles, computes overlap with USPS routes, and joins Census demographic data

Notebooks were run using Python with GeoPandas, Pandas, Matplotlib, and the H3 library. Spatial joins were performed using an Albers Equal Area projection (EPSG:5070).

## Cite

These scripts support findings for our publication in TPRC54:

Morgan Vigil-Hayes and Sri Chandana Julakanti. "Maps without Witnesses: Closing the Participation Gap in FCC Mobile Broadband Challenges." In the Proceedings of TPRC54. [Full citation to be added upon publication.]

## Contact

For questions about this repository, please contact Morgan Vigil-Hayes (vigilhay@msu.edu) or Srichandana Julukanti (srichandana22@gmail.com).