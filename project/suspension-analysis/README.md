# 🚗 Suspension Analysis Project

This project analyzes experimental suspension data to evaluate **ride quality** using MATLAB. The system simulates a vehicle suspension subjected to sinusoidal motion at different frequencies.

---

## 📌 Project Overview

The experiment runs for 30 seconds:

- **0–10 s:** Low-frequency motion (0.5 Hz)
- **10–20 s:** No motion
- **20–30 s:** High-frequency motion (5 Hz)

Sensors record:
- Position (voltage → displacement)
- Acceleration (voltage → G-force)

---

## 🧪 Task 1: Import & Visualize Raw Data

### 📥 Load Data

```matlab
load('suspensionData.mat')
````

### ⏱ Sampling Period

```matlab
Ts = time(2) - time(1)
```

### 📊 Plot Raw Signals

```matlab
figure
plot(time, Vpos, 'b', time, Vacc, 'r')
xlabel('Time (s)')
ylabel('Voltage (V)')
legend('Position Voltage', 'Acceleration Voltage')
title('Raw Sensor Data')
grid on
```

---

## 🛠 Task 2: Data Preparation

### 🔄 Convert Voltage to Physical Values

```matlab
pos = 3.00 * (Vpos - 0.5);     % cm
acc = 5.09 * (Vacc - 0.1);     % G
```

### ✂️ Extract Test Segments

```matlab
posLow = pos(1:2001);
posHigh = pos(4001:6001);

accLow = acc(1:2001);
accHigh = acc(4001:6001);
```

### ⏱ Create Test Time Vector

```matlab
testTime = (0:length(posLow)-1)' * Ts;
```

### 📊 Plot Position Comparison

```matlab
figure
plot(testTime, posLow, 'b', testTime, posHigh, 'r')
xlabel('Time (s)')
ylabel('Position (cm)')
legend('Low Frequency (0.5 Hz)', 'High Frequency (5 Hz)')
title('Position Comparison')
grid on
```

### 📊 Plot Acceleration Comparison

```matlab
figure
plot(testTime, accLow, 'b', testTime, accHigh, 'r')
xlabel('Time (s)')
ylabel('Acceleration (G)')
legend('Low Frequency (0.5 Hz)', 'High Frequency (5 Hz)')
title('Acceleration Comparison')
grid on
```

---

## 📈 Task 3: Data Analysis

### 📐 RMS Calculation

```matlab
posLowRMS = sqrt(mean(posLow.^2));
posHighRMS = sqrt(mean(posHigh.^2));

accLowRMS = sqrt(mean(accLow.^2));
accHighRMS = sqrt(mean(accHigh.^2));
```

### 📦 Combine Results

```matlab
testFreq = [0.5 5];

posRMS = [posLowRMS posHighRMS];
accRMS = [accLowRMS accHighRMS];
```

### 📊 RMS Visualization

```matlab
figure
plot(testFreq, posRMS, '-o')
hold on
plot(testFreq, accRMS, '-s')
xlabel('Frequency (Hz)')
ylabel('RMS Value')
legend('Position RMS', 'Acceleration RMS')
title('RMS vs Frequency')
grid on
```

---

## 🧠 Task 4: Conclusions

### 🚗 Ride Quality Interpretation

* **Low-frequency motion (0.5 Hz):**

  * Produces smoother and slower oscillations
  * Generally more comfortable for passengers

* **High-frequency motion (5 Hz):**

  * Produces rapid vibrations
  * Leads to discomfort and harsher ride quality

### 📊 Key Findings

* RMS values **increase with frequency**, especially for acceleration
* Acceleration is more sensitive to ride discomfort than position
* High-frequency motion significantly worsens ride quality

### ✅ Final Conclusion

The suspension system performs better at **low frequencies**, providing a smoother and more comfortable ride. High-frequency vibrations increase acceleration forces, making the ride less comfortable.

---

## 🧾 Skills Demonstrated

* Data Import & Preprocessing
* Signal Analysis
* MATLAB Visualization
* Statistical Analysis (RMS)
* Engineering Interpretation

---

## 📁 Files

* `suspensionDataVolts.csv` – Raw dataset
* `suspensionData.mat` – Saved workspace
* `suspension_analysis.mlx` – Live script with full analysis

---
