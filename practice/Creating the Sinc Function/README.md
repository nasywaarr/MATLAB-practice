# 📈 Creating the Sinc Function

A MATLAB challenge activity to calculate and plot the sinc function using vectors, elementwise operations, and indexing.

---

## 📖 Introduction

The sinc function is a sinusoid with a central peak and decaying oscillations on either side. This function has many applications in mathematics, physics, and engineering. For example, it is used in describing the diffraction of light after passing through a thin slit.

<img width="866" height="322" alt="Screenshot (1353)" src="https://github.com/user-attachments/assets/0bbcb2ac-1533-401c-8842-d5430a797895" />

---

## 📝 Task

In this activity, you'll calculate and plot the sinc function using the equation below:

$$\text{sinc}(x) = \frac{\sin(\pi x)}{\pi x}$$

When evaluated in MATLAB, this equation becomes undefined when `x = 0` because the denominator is zero. To handle this, you'll manually replace this data point with a value of `1`.

<img width="558" height="431" alt="Screenshot (1354)" src="https://github.com/user-attachments/assets/aa45f790-94fd-47d3-b9d4-0b6f89284e47" />

Write code to complete each of the tasks below:

1. Define a row vector `x` with equally spaced values that range from `-10` to `10`, with a spacing of `0.2`.
2. Transform the `x` vector into a column vector using the transpose operator. Be sure to store the result back into the variable `x`.
3. Compute the sinc function for all values of `x` using the equation above. Store the result in a new vector `y`. Use the `pi` function for the value of π.
4. The sinc function is undefined when `x = 0`, which occurs at index `51` in the `y` vector. Change the 51st element of the `y` vector to equal `1`.
5. Use the `plot` function to make a line plot. The vector `x` contains the X-coordinate values, and the vector `y` contains the Y-coordinate values.

---

## 💻 Code

```matlab
% Task 1 — Define x as a row vector from -10 to 10 with spacing 0.2
x = -10:0.2:10;

% Task 2 — Transpose x into a column vector
x = x';

% Task 3 — Compute the sinc function for all values of x
y = sin(pi * x) ./ (pi * x);

% Task 4 — Replace the undefined value at index 51 with 1
y(51) = 1;

% Task 5 — Plot the sinc function
plot(x, y)
```

---

*Copyright 2025 The MathWorks, Inc.*
