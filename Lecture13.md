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
  * Euclidean distances and 𝐿𝐿𝑝𝑝 norms
  * Dynamic Time Warping (DTW)
  * Time Domain vs. Frequency Domain
