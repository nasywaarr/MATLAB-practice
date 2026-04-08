# 🚗 Suspension Analysis Project

This project analyzes experimental data to quantify the **ride quality** of a car suspension using MATLAB. The system simulates a vehicle suspension subjected to sinusoidal motion at different frequencies.

Ride quality describes how comfortable it is to ride in a vehicle. 

<img width="1058" height="550" alt="_b8509dbae4c24e9180071bf92835344f_S1P1" src="https://github.com/user-attachments/assets/48a8a004-7609-4d0d-9e86-7a53c1153ff4" />

---

## 📌 Project Overview

The experiment runs for 30 seconds:

- **0–10 s:** Low-frequency motion (0.5 Hz)
- **10–20 s:** No motion
- **20–30 s:** High-frequency motion (5 Hz)

![_c8bf3759ca6e4da18662a7771748c42d_S1P2](https://github.com/user-attachments/assets/c644438c-3f4a-4a4c-8226-86c1c95520d3)

![_5ee06eaca3804c37bdc8ac5a80532840_S1P3](https://github.com/user-attachments/assets/44765e27-73d0-4277-b39e-cfb136aaab03)

---

## 🧪 Task 1: Import and Visualize the Raw Experimental Data

### 📥 Load Data

```matlab
data = readtable('suspensionDataVolts.csv');

time = data.time;
Vpos = data.Vpos;
Vacc = data.Vacc;

---

### ⏱ Sampling Period

```matlab
Ts = time(2) - time(1)
````

✅ The sampling period is:

```matlab
Ts = 0.005 seconds
```

---

### 💾 Save Workspace

```matlab
save('suspensionData.mat')
```

---

### 🔄 Load Data in Script

```matlab
load('suspensionData.mat')
```

---

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

### 🔍 Observation

* **0–10 s:** slow oscillations → low frequency
* **20–30 s:** fast oscillations → high frequency

---

## 🛠 Task 2: Prepare the Experimental Data for Analysis

### 🔄 Convert Voltage to Physical Values

```matlab
pos = 3.00 * (Vpos - 0.5);     % Position (cm)
acc = 5.09 * (Vacc - 0.1);     % Acceleration (G)
```

---

### ✂️ Extract Test Segments

```matlab
posLow = pos(1:2001);
posHigh = pos(4001:6001);

accLow = acc(1:2001);
accHigh = acc(4001:6001);
```

---

### ⏱ Create Test Time Vector

```matlab
testTime = (0:length(posLow)-1)' * Ts;
```

---

### 📊 Position Comparison

```matlab
figure
plot(testTime, posLow, 'b', testTime, posHigh, 'r')
xlabel('Time (s)')
ylabel('Position (cm)')
legend('Low Frequency', 'High Frequency')
title('Position Comparison')
grid on
```

---

### 📊 Acceleration Comparison

```matlab
figure
plot(testTime, accLow, 'b', testTime, accHigh, 'r')
xlabel('Time (s)')
ylabel('Acceleration (G)')
legend('Low Frequency', 'High Frequency')
title('Acceleration Comparison')
grid on
```

---

## 📈 Task 3: Analyze the Data

### 📐 RMS Calculation

```matlab
posLowRMS = sqrt(mean(posLow.^2));
posHighRMS = sqrt(mean(posHigh.^2));

accLowRMS = sqrt(mean(accLow.^2));
accHighRMS = sqrt(mean(accHigh.^2));
```

---

### 📦 Combine Results

```matlab
testFreq = [0.5 5];

posRMS = [posLowRMS posHighRMS];
accRMS = [accLowRMS accHighRMS];
```

---

### 📊 RMS vs Frequency

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

## 🧠 Task 4: Draw Conclusions and Share

### 🚗 Ride Quality Interpretation

* **Low-frequency motion (0.5 Hz):**

  * Smooth and gentle movement
  * More comfortable ride

* **High-frequency motion (5 Hz):**

  * Rapid vibrations
  * Less comfortable ride

---

### 📊 Key Findings

* RMS values **increase with frequency**
* Acceleration shows **larger variation than position**
* High-frequency motion produces stronger vibrations

---

### ✅ Final Conclusion

The suspension system provides **better ride quality at low frequencies**.

High-frequency motion causes:

* Increased acceleration
* More vibrations
* Reduced passenger comfort

---
