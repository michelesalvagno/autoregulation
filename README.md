# autoregulation analysis using MxA

This repository contains a MATLAB script developed for the analysis of **dynamic cerebral autoregulation** using the **MxA (mean flow index)** method.

The script allows researchers and clinicians to compute MxA values from arterial blood pressure (ABP) and cerebral blood flow velocity (CBFV) signals, offering a simple and reproducible way to assess autoregulation at the bedside or in research settings.


## script origin

This script is based on a previous version originally developed some years ago by our intensive care research group at **Erasme Hospital, Université Libre de Bruxelles (ULB), Belgium** under the supervision of prof. Fabio Silvio Taccone.
The current version of the script has been updated for compatibility with MATLAB 2024 and improved for greater clarity, and ease of use.


## requirements

- MATLAB R2021b or later
- Input file: `filename.txt` (must contain PA and BFV signals in columns)
- corr requires one of the following: Econometrics Toolbox, Statistics and Machine Learning Toolbox


## citation

If you use this script for academic work or research, please cite our GitHub repository and acknowledge _Department of Intensive Care - Erasme Hospital - ULB Bruxelles_.

---

## overview

The script:
1. Loads time series data for PA and BFV.
2. Cleans signal artifacts using thresholds and linear interpolation.
3. Allows manual exclusion of noisy segments via interactive zoom and selection.
4. Segments the signals into X-minute epochs (we usually use 3 or 5 minutes).
5. Calculates moving averages and the MXA index (correlation between PA and BFV).
6. Summarizes key results in a final table.

---

## how to use

1. Place your input file `filename.txt` in the working directory.
2. Run the script.
3. When prompted:
   - Use `f` to zoom in horizontally on a plot.
   - Select two points with your mouse to define a noisy segment.
   - Use `e` to finish segment selection.
4. The script will automatically perform interpolations, cuts, and epoch-based analysis.

---

## signal preprocessing

- **Sampling rate (`fs`)**: 100 Hz
- Signals: 
  - **CBFV**: Column number to adjust if needed
  - **PA**: Column number to adjust if needed

Both signals are cleaned by excluding values outside defined thresholds:
- PA: 10–300 mmHg
- BFV: 10–300 cm/s

Missing or outlier data is linearly interpolated.

---

## manual artifact removal

You can interactively remove segments of noise from both BFV and PA:
- Click to select start and end of noisy segments
- The script keeps track of percentage of signal removed

---

## epoch division

Signals are divided into **minute epochs** (if 3 minutes : ~18,000 samples) after cleaning. Only clean data segments (NaNs excluded) are used for analysis.

---

## moving average and correlation

- Moving averages calculated using a pre-defined overlapping 10-second windows (1000 samples) (we also used 5-second windows) with 50% overlap (step of 500 samples - we also used 20% or 80% of overlap).
- For each epoch:
  - Moving average is computed separately for PA and BFV
  - **MXA** (Pearson correlation between averaged PA and BFV) is computed

---

Feel free to open an issue or contact us for any questions or improvements.
