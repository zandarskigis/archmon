# Archaeological Vegetation Monitoring (archmon)

This project uses remote sensing and machine learning to monitor vegetation change at archaeological sites potentially impacted by human activity — including low-level military flights. It focuses on a case study site (5HF737) and builds a scalable pipeline for broader use.

## Project Structure

archmon/ ├── notebooks/ # All analysis notebooks │ ├── ndvi_savi_change_analysis.ipynb │ ├── kmeans_analysis.ipynb │ ├── rnn_sequence_generation.ipynb │ └── lstm_forecasting.ipynb ├── data/ # Input rasters and site folders │ └── 5HF737/ │ ├── ndvi_by_month/ │ └── savi_by_month/ ├── outputs/ # Forecasts, difference maps, model outputs │ └── forecasts/ │ ├── ndvi_diffs/ │ └── *.npy, *.tif, *.png ├── environment.yml # (or requirements.txt) — dependencies └── README.md

## Summary

- NDVI and SAVI rasters (from Sentinel-2) are preprocessed externally and loaded here.
- `ndvi_savi_change_analysis.ipynb`: calculates difference rasters and visualizes 1-year vegetation change.
- `kmeans_analysis.ipynb`: clusters NDVI/SAVI difference values to segment areas of potential disturbance.
- `rnn_sequence_generation.ipynb`: prepares multiyear NDVI/SAVI sequences for training an LSTM.
- `lstm_forecasting.ipynb`: trains a 12→1 NDVI forecast model and compares 2025 predictions to observed rasters.
- Annotated difference maps and statistical metrics (RMSE, MAE) are saved to `outputs/`.

## Outputs

- NDVI and SAVI difference maps
- Clustered landscape segments (KMeans)
- Forecast panels for 2025 NDVI/SAVI
- Difference heatmaps with embedded metrics
- `.npy` sequence datasets for training and forecasting

## Dependencies

See `environment.yml` (or `requirements.txt`) for setup. Core libraries include:

- `rasterio`
- `numpy`
- `matplotlib`
- `scikit-learn`
- `tensorflow` (for LSTM model)

## How to Run

1. Clone the repo
2. Set up your environment
3. Start with `ndvi_savi_change_analysis.ipynb` for 1-year change detection
4. Continue with sequence generation and forecasting in order

## License

MIT License

Copyright (c) 2025 Benjamin A. Zandarski II

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

---

*Built by Benjamin A. Zandarski II — Fort Carson Cultural Resources.*
