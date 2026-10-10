# DSCI 552 - Homework 3

Vishnu Gamini · GitHub: vishnugamini

Time-domain feature extraction for the AReM dataset and answers to ISLR exercise 3.7.4.

## Files

```text
data/
  AReM/
    bending1/   bending2/   cycling/   lying/   sitting/   standing/   walking/
    bendingType.pdf
    sensorsPlacement.pdf
  processed/
    cleaning_report.csv
    features.csv
    train_features.csv
    test_features.csv
    feature_uncertainty.csv
notebook/
  Gamini_Vishnu_HW3.ipynb
requirements.txt
```

## Run locally

Use Python 3.12. From the repository root:

```sh
python3 -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
python -m notebook
```

Open `notebook/Gamini_Vishnu_HW3.ipynb` and restart the kernel before running all cells. The notebook includes saved outputs and reads data using relative paths. Running it recreates the processed CSV files.

The 88 recordings are split into 69 training and 19 test recordings using the assignment's specified file numbers. Seven statistics from each of six series yield 42 features. Sample standard deviations use `ddof=1`, and quartiles use linear interpolation. Standard deviations across all recordings have 90% percentile bootstrap intervals based on 10,000 row resamples with seed 42. Mean, standard deviation, and maximum are selected as three feature types; the accompanying activity summaries use training recordings only.

## Data 

Palumbo, F., Gallicchio, C., Pucci, R., and Micheli, A. (2016). *Activity Recognition system based on Multisensor data fusion (AReM)*. UCI Machine Learning Repository. https://doi.org/10.24432/C5SS33. Dataset license: CC BY 4.0.
