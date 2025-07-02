# Repository Overview

This project demonstrates the extension of a localised aboveground carbon (AGC) model to the wider thicket biome of South Africa using Google Earth Engine (GEE). The repo contains JavaScript scripts and geospatial data used to calibrate and apply the model.

## Directory structure

- `extend_thicket_agc/` – utility modules such as the cloud masking library.
- `scripts/` – GEE scripts to calibrate the model and generate the AGC map.
- `data/inputs/` – ground truth plots and thicket boundary layers required for calibration.
- `data/outputs/` – example imagery and visualisation outputs.
- `LICENSE` and `DATA-LICENSE` – software and data licensing terms.

## Scripts

| Script | Purpose |
| --- | --- |
| `scripts/calibrate_agc_model.js` | Calibrates the local WorldView‑3 AGC model to Landsat 8 imagery and evaluates accuracy. |
| `scripts/generate_agc_map_ui.js` | Applies the calibrated model to the biome and creates an interactive map UI within the GEE Code Editor. |

The calibration script exports both the calibrated model parameters and an AGC image to GEE assets. The map generation script reads these assets to visualise AGC across the thicket biome.

## Data

Input datasets are located under `data/inputs/geospatial/`:

- `gef_calib_plots.geojson` – AGC estimates used for calibration and validation.
- `step_arid_and_valley_thicket.zip` – polygons defining combined arid and valley thicket types.

Outputs, such as example map screenshots, are stored under `data/outputs/`.

## Usage

1. Open the scripts in the [GEE Code Editor](https://code.earthengine.google.com/).
2. Upload the input GeoJSON and shapefile to your GEE assets if not already present.
3. Run `scripts/calibrate_agc_model.js` to calibrate the Landsat‑based model and export the results.
4. Run `scripts/generate_agc_map_ui.js` to produce the map interface. The script references the exported model coefficients.

A hosted version of the visualisation is available [here](https://dugalh.users.earthengine.app/view/thicket-aboveground-carbon). Give it some time to render the AGC estimates.

For further details see the top-level `README.md`.
