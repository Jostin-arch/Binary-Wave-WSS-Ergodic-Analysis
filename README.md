# Analysis of Wide-Sense Stationarity and Ergodicity in a Random Binary Wave

## Abstract

[cite_start]This project provides a computational analysis of the statistical properties of a random binary process[cite: 22]. [cite_start]A Python script is used to generate an ensemble of random binary waves and subsequently calculates their time and ensemble averages to determine if the process is Wide-Sense Stationary (WSS) and Ergodic[cite: 23].

[cite_start]This work was submitted as a course project for ECT305: Analog and Digital Communication  [cite_start]at the Department of Electronics and Communication Engineering, N.S.S College of Engineering, Palakkad[cite: 12, 13, 14].

---

## Table of Contents

1.  [Background Theory](#1-background-theory)
2.  [Implementation Details](#2-implementation-details)
3.  [Results and Discussion](#3-results-and-discussion)
4.  [Installation and Usage](#4-installation-and-usage)
5.  [Project Information](#5-project-information)
6.  [References](#6-references)

---

## 1. Background Theory

### Wide-Sense Stationary (WSS)
[cite_start]A random process is defined as Wide-Sense Stationary if its mean is constant over time and its autocorrelation function depends only on the time lag between two points, not on their absolute position in time[cite: 58].

### Ergodicity
[cite_start]An ergodic process is one in which the statistical properties of the entire ensemble of realizations can be deduced from a single, sufficiently long realization[cite: 61]. [cite_start]For an ergodic process, the time averages are equivalent to the corresponding ensemble averages[cite: 62, 63].

---

## 2. Implementation Details

The analysis is conducted via a Python script that implements the following algorithm:

* [cite_start]**Parameterization**: The simulation is configured with a set of `50` realizations (`n_realizations`) [cite: 28] [cite_start]and `1000` time samples (`n_samples`) per realization[cite: 29]. The probability for generating a binary 0 or 1 is set to `0.5`[cite: 30].

* [cite_start]**Data Generation**: An ensemble of binary waves is generated using NumPy's `random.choice` function, creating a `50x1000` array[cite: 32, 96].

* **Statistical Computations**:
    * [cite_start]**Time Averages**: The mean and autocorrelation are computed for each realization along the time axis[cite: 38, 40].
    * [cite_start]**Ensemble Averages**: The mean and autocorrelation are computed across all realizations at each time point[cite: 43, 46].

* [cite_start]**Verification**: The script programmatically checks for WSS and Ergodicity by comparing the computed averages using `np.isclose()` with a defined tolerance of 0.01[cite: 59, 60, 63].

---

## 3. Results and Discussion

The script's execution yields both graphical and textual outputs to support its conclusion.

#### Graphical Results

[cite_start]**Figure 1**: A plot of a single realization from the generated ensemble, displaying its random binary nature over 1000 time samples[cite: 171, 193].
![Random Binary Wave](https://i.imgur.com/Gj8T6mG.png)

[cite_start]**Figure 2**: A comparative plot of the time-averaged autocorrelation for a single realization versus the ensemble-averaged autocorrelation[cite: 211].
![Autocorrelation Comparison](https://i.imgur.com/T0bJvXl.png)

#### Final Conclusion

Based on the numerical comparison from the report's sample run, the script concluded:

> [cite_start]**The binary wave is not WSS but Ergodic** [cite: 176]

---

## 4. Installation and Usage

### Prerequisites
* Python 3.x
* [cite_start]NumPy [cite: 87]
* [cite_start]Matplotlib [cite: 87]

### Installation
Install the necessary Python libraries using pip:
```bash
pip install numpy matplotlib