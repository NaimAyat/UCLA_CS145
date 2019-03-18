# Lecture 13: Time Series Data: Similarity Search
## Time Series
* A time series is a sequence of numerical data points, measured typically at successive times, spaced at (often uniform) time intervals
  * Random variables for a time series are represented as:
    * 𝑌 = { 𝑌1, 𝑌2, … }
  * An observation of a time series with length N is represented as:
    * 𝑌 = {𝑦1, 𝑦2, … , 𝑦𝑁}
## Why Similarity Search?
* Wide applications
  * Find a time period with similar inflation rate and unemployment time series?
  * Find a similar stock to Facebook?
  * Find a similar product to a query one according to sale time series?
## Similarity Search for Time Series Data
* Time Series Similarity Search
  * Euclidean distances and 𝐿𝑝 norms
  * Dynamic Time Warping (DTW)
  * Time Domain vs. Frequency Domain
## Dynamic Time Warping (DTW)
* For two sequences that do not line up well in X-axis, but share roughly similar shape
  * We need to warp the time axis to make better alignment 
## Goal of DTW
* Given
  * Two sequences (with possible different lengths):
    * 𝑋 = {𝑥1, 𝑥2, … , 𝑥𝑁}
    * 𝑌 = {𝑦1, 𝑦2, … , 𝑦𝑀}
   * A local distance (cost) measure between 𝑥𝑛 and 𝑦𝑚: 𝑐(𝑥𝑛, 𝑦𝑚)
* Goal:
  * Find an alignment between X and Y such that the overall cost is minimized 
## Represent an Alignment by Warping Path
* An (N,M)-warping path is a sequence 𝑝 = (𝑝1, 𝑝2, … , 𝑝𝐿) with 𝑝𝑙 = (𝑛𝑙, 𝑚𝑙), satisfying the three conditions:
  * Boundary condition: 𝑝1 = 1,1 , 𝑝𝐿 = 𝑁, 𝑀
    * Starting from the first point and ending at last point
* Monotonicity condition: 𝑛𝑙 and 𝑚𝑙 are nondecreasing with 𝑙
* Step size condition:
  * 𝑝𝑙+1 − 𝑝𝑙 ∈ 0,1 , 1,0 , 1,1
* Move one step right, up, or up-right
## Time Domain vs. Frequency Domain
* Many techniques for signal analysis require the data to be in the frequency domain
* Usually data-independent transformations are used
  * The transformation matrix is determined a priori
    * discrete Fourier transform (DFT)
    * discrete wavelet transform (DWT)
* The distance between two signals in the time domain is the same as their Euclidean distance in the frequency domain
## Categories of Time-Series Movements 
* Categories of Time-Series Movements (T, C, S, I)
  * Long-term or trend movements (trend curve): general direction in which a time series is moving over a long interval of time
  * Cyclic movements or cycle variations: long term oscillations about a trend line or curve
    * e.g., business cycles, may or may not be periodic
  * Seasonal movements or seasonal variations
    * E.g., almost identical patterns that a time series appears to follow during corresponding months of successive years.
  * Irregular or random movements
## Prediction vs. Forecast
* A predicted value refers to the value of Y predicted (using a regression) for an observation in the sample used to estimate the regression – this is the usual definition
  * Predicted values are “in sample”
* A forecast refers to the value of Y forecasted for an observation not in the sample used to estimate the regression.
  * Forecasts are forecasts of the future – which cannot have been used to estimate the regression.
