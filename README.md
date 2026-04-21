# Ideal, Natural, & Flat-top -Sampling
# Aim
Write a simple Python program for the construction and reconstruction of ideal, natural, and flattop sampling.
# Tools required
# Program
```
// Parameters
fm = 5;
fs = 50;

t = linspace(0, 1, 1000);
ts = 0:1/fs:1-1/fs;

// Original signal
x = sin(2 * %pi * fm * t);

// Sampled values
xs = sin(2 * %pi * fm * ts);

// Flat-top sampling
flat_top = zeros(t);

for i = 1:length(ts)-1
    idx = find(t >= ts(i) & t < ts(i+1));
    flat_top(idx) = xs(i);
end

// Plotting
clf;

// Original signal
subplot(4,1,1);
plot(t, x);
title("Original Analog Signal");

// Ideal Sampling
subplot(4,1,2);
plot(ts, xs, 'ro');
title("Ideal Sampling");

// Natural Sampling
subplot(4,1,3);
plot(t, x);
plot(ts, xs, 'ro');
title("Natural Sampling");

// Flat-top Sampling
subplot(4,1,4);
plot(t, flat_top);
title("Flat-top Sampling");

```
# Output Waveform

<img width="1514" height="1008" alt="image" src="https://github.com/user-attachments/assets/1221be99-eea4-4a83-8d53-ba8dc6f62427" />

# Results
```
Attach the output waveform
```
# Hardware experiment output waveform.
