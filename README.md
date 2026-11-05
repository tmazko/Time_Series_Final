# MATH840: 48-Hour Electricity Generation Forecast

**Author:** Tetiana Mazko

This repository contains the code and final report for the MATH840 Time Series project. The final model is a blend of **30% LightGBM** (trained on the last 365 days) and **70% Chronos-2** (1440-hour context with weather covariates), utilizing a night multiplier of 0.8 and calibrated out-of-fold intervals to optimize the Winkler score.

## How to Run

1. **Environment Setup:** Ensure you have Python installed along with the required libraries. You will need `pandas`, `numpy`, `lightgbm`, `matplotlib`, `statsmodels`, and the `chronos` forecasting package.
2. **Data Files:** Place the provided `train.csv` and `weather_forecast.csv` files in the same directory as the notebook.
3. **Execution:** Open the Jupyter Notebook (or Google Colab) and run all cells sequentially from top to bottom. 
   * *Note: The Chronos-2 model with a 1440-hour context takes some time to run on CPU. Please allow ~15-20 minutes for the validation and final inference cells to execute.*
4. **Output:** The final cell will generate the submission file named `MAZKO_project_final_fixed_intervals.csv`.

## AI Usage Statement

During this project, Large Language Models (LLMs) were used as auxiliary assistants for the following tasks:
* **Code Assistant:** Writing boilerplate code, refactoring, and debugging Python scripts (specifically for `pandas` data manipulation and `matplotlib`/`seaborn` visualizations).
* **LaTeX Formatting:** Structuring the final report, generating tables, and troubleshooting syntax errors (e.g., missing brackets) in Overleaf.
* **Text Editing:** Proofreading, stylizing, and making the Ukrainian text in the report more concise.

**All conceptual and architectural decisions** — including feature engineering, the choice of models, blend weights (0.3/0.7), the 1440h context length discovery, and the interval calibration logic — were developed and verified independently by the author.