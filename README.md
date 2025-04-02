# autoregulation analysis using MxA

This repository contains a MATLAB script developed for the analysis of **dynamic cerebral autoregulation** using the **MxA (mean flow index)** method.

The script allows researchers and clinicians to compute MxA values from arterial blood pressure (ABP) and cerebral blood flow velocity (CBFV) signals, offering a simple and reproducible way to assess autoregulation at the bedside or in research settings.

## overview

Cerebral autoregulation is a critical physiological mechanism that maintains constant cerebral blood flow despite fluctuations in systemic arterial pressure. The MxA index quantifies this relationship by computing the moving Pearson correlation coefficient between slow waves of ABP and CBFV.

The script:
- Takes input time series of ABP and CBFV
- Applies smoothing and resampling
- Segments the signals into windows
- Computes the Pearson correlation coefficient over each segment
- Outputs the MxA value and optionally visualizes the process

## Script Origin

This script is based on a previous version originally developed by our intensive care research group at **Erasme Hospital, Université Libre de Bruxelles (ULB), Belgium** under the supervision of prof. Fabio Silvio Taccone.
The current version has been modified and updated to adapt the script to the new version of MatLAB 2024, and clarity, robustness, and ease of use.

## Requirements

- MATLAB R2024b or later 

## How to Use

## Citation

If you use this script for academic work or clinical research, please cite our GitHub repository and acknowledge _Department of Intensive Care - Erasme Hospital - ULB Bruxelles_.

---

Feel free to open an issue or contact us for any questions or improvements.
