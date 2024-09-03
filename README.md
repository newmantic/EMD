# EMD


Empirical Mode Decomposition (EMD) is a data-driven technique used to decompose a complex signal into a set of simpler oscillatory components known as Intrinsic Mode Functions (IMFs). EMD is particularly useful for analyzing non-linear and non-stationary time series data, such as signals in engineering, geophysics, and finance.


1. Intrinsic Mode Function (IMF)
An Intrinsic Mode Function (IMF) is a function that satisfies the following two conditions:
Number of extrema: The number of extrema (local maxima and minima) and the number of zero-crossings must either be equal or differ by at most one.
Symmetry: The mean value of the envelope defined by the local maxima and the envelope defined by the local minima is zero at every point.
IMFs represent the simple oscillatory modes extracted from the original signal.

2. Sifting Process
The sifting process is the core of EMD and involves iteratively extracting IMFs from the original signal. The steps in the sifting process are:
Identify Local Extrema: Identify all the local maxima and minima of the signal.

Create Envelopes:
Interpolate between the local maxima to form the upper envelope.
Interpolate between the local minima to form the lower envelope.

Compute the Mean Envelope:
Compute the mean of the upper and lower envelopes.

Subtract the Mean:
Subtract the mean envelope from the original signal to obtain a candidate IMF.

Check IMF Criteria:
If the candidate function satisfies the IMF criteria (number of extrema and zero-crossings, and symmetry), it is designated as an IMF.
If not, repeat the sifting process on the candidate function.

Extract IMF:
Once an IMF is extracted, subtract it from the original signal to obtain the residual signal.
Repeat the sifting process on the residual signal to extract further IMFs.
The process continues until the residual becomes a monotonic function, from which no more IMFs can be extracted.

3. EMD Decomposition
Given a signal X(t), EMD decomposes it into n IMFs and a residual R_n(t):
X(t) = IMF_1(t) + IMF_2(t) + ... + IMF_n(t) + R_n(t)
Where:
IMF_i(t) is the i-th intrinsic mode function.
R_n(t) is the final residual, which is typically a monotonic function or a trend.



Start: Begin with the original signal X(t).
Sifting: Extract the first IMF by identifying local extrema, creating envelopes, computing the mean, and subtracting the mean from the signal.
Repeat: Subtract the extracted IMF from the signal and repeat the sifting process on the residual.
Stop: The process stops when the residual becomes a monotonic function or when a predefined number of IMFs has been extracted.
