# 📊 Practice with Vectors

## 🧮 Creating Vectors

There are many ways to create vectors. Such as:
- Create vectors using concatenation.
- Create vectors with a set spacing.
- Create vectors with a set number of elements.

### Concatenation

Square brackets are used to group elements together into vectors. Use a space between elements to create a row vector, or add a semicolon between elements to create a column vector.

<img width="727" height="436" alt="Screenshot (1344)" src="https://github.com/user-attachments/assets/8b7587b3-f927-42f5-85be-01c8fa45cfc5" />

**Task:** Use concatenation to create a column vector `v1` with the following elements: 0, 1, 1, 0.

```matlab
v1 = [0; 1; 1; 0];
```

**Task:** Create a second column vector `v2` with the following elements: 0, 5, 0.

```matlab
v2 = [0; 5; 0];
```

**Task:** Square brackets are also used to combine vectors together. Create a new column vector `v3` that combines the `v1` and `v2` vectors together. This should create a new column vector with seven rows and one column.

```matlab
v3 = [v1; v2];
```

---

### Vectors with Set Spacing

The colon operator creates a row vector with a set spacing. If you do not specify the spacing value, it will use a default spacing of 1.

<img width="570" height="324" alt="Screenshot (1345)" src="https://github.com/user-attachments/assets/6f48ea0d-cafc-4eae-a6d8-b04f0a62a8fc" />

**Task:** Use the colon operator to create a vector named `v4` that starts at 45, ends at 90, with a spacing of 5.

```matlab
v4 = 45:5:90;
```

**Task:** Use the colon operator to create a vector named `v5` that starts at -10 and ends at 5, with the default spacing of 1.

```matlab
v5 = -10:5;
```

---

### Vectors with Set Number of Elements

The `linspace` function creates a vector with a set number of equally spaced elements:

<img width="739" height="340" alt="Screenshot (1346)" src="https://github.com/user-attachments/assets/2d06f36e-ba4b-4843-8867-da6c3fc37f33" />

**Task:** Use the `linspace` function to create a vector named `v6` that starts at 0, ends at 2π, with 5 equally spaced elements. Use the `pi` function for the value of π.

```matlab
v6 = linspace(0, 2*pi, 5);
```

---

### Summary

When creating vectors, choose the approach best suited for what you need to accomplish:

| Approach | When to Use |
|---|---|
| **Concatenation** `[ ]` | Combine multiple elements or vectors into a single vector |
| **Colon operator** `:` | Create a vector with a set spacing between elements |
| **`linspace`** | Create a vector with a set number of equally spaced elements |

---

## 🔍 Accessing and Manipulating Vector Elements

### Vector Indexing

To access elements from a vector, add parenthesis after the vector name. Inside the parenthesis, specify the indices of the desired elements. Use an equal sign (`=`) before the indexing operation to assign the result to a variable.

<img width="1212" height="389" alt="Screenshot (1347)" src="https://github.com/user-attachments/assets/e0a77fb4-44e3-40dd-a000-cd58b01f8da7" />

**Task:** Use indexing to obtain the fifth element from the vector `v6` and store it in a variable named `x`.

```matlab
x = v6(5);
```

---

### Vector Manipulation

Use an equal sign (`=`) after the indexing operation to assign new values to vector elements.

<img width="1380" height="356" alt="Screenshot (1348)" src="https://github.com/user-attachments/assets/21cf584b-177b-487b-ae21-9d640e32e34b" />

**Task:** Change the third value of the `v6` vector to 0.

```matlab
v6(3) = 0;
```

---

## ➕ Math Operations with Vectors

### Arithmetic Operations

Use elementwise operators to perform mathematical operations on the corresponding elements of two vectors. Below are examples of common math operators in MATLAB.

<img width="840" height="383" alt="Screenshot (1349)" src="https://github.com/user-attachments/assets/a279b231-466b-4798-a42b-88c8d8e104da" />

**Task:** Given the vectors `A` and `B`, compute the elementwise multiplication of A times B. Store the result in a new vector named `C`.

```matlab
A = [1; 28; 40];
B = [16; 35; 120];
C = A .* B;
```

---

### Math Functions

There are many common mathematical functions that operate on vectors. The function is automatically applied to every element of the vector.

<img width="1502" height="317" alt="Screenshot (1350)" src="https://github.com/user-attachments/assets/27f21ae2-f1af-450d-b23d-2c61f3830f23" />

**Task:** Given the vectors `expected` and `experimental` defined below, compute the percent error for each element using the equation below. Store the result in a new row vector named `percentError`. Use the `abs` function to compute the absolute value.

$$\text{percentError} = \text{abs}\left(\frac{\text{experimental} - \text{expected}}{\text{expected}}\right) \cdot 100$$

```matlab
expected     = [50 55 60 65 70 75];
experimental = [48.8 55.2 54 62.8 65.7 74.6];
percentError = abs((experimental - expected) ./ expected) * 100;
```

> The resulting row vector should have six unique values ranging from about 0.36 to 10.

---

## 📐 Vector Characteristics

### Transpose

You can use the transpose operator to transform a row vector into a column vector (or a column vector into a row vector).

<img width="963" height="435" alt="Screenshot (1351)" src="https://github.com/user-attachments/assets/57d14b07-55e1-489d-a10d-626f0ea8240e" />

**Task:** Transpose the `percentError` row vector calculated above into a column vector. Store the result in a new vector named `peCol`.

```matlab
peCol = percentError';
```

---

### Size and Length

The `size` function returns the number of rows and the number of columns of a vector. The `length` function is similar but returns only the length of the longest dimension, regardless of whether it is a row or column vector.

<img width="821" height="323" alt="Screenshot (1352)" src="https://github.com/user-attachments/assets/c1aa9c89-a78f-4d45-adef-9f0e31780620" />

**Task:** Use the `size` function to get the size (rows and columns) of the `peCol` vector. Use the `length` function to get the length of the `peCol` vector. Notice how the output of the `length` function differs from the `size` function.

```matlab
size(peCol)
length(peCol)
```

---

## ✅ Conclusion

I learned about:
- **Creating vectors** using concatenation, the colon operator, and `linspace`
- **Accessing vector elements** using indexing
- **Manipulating vector data** by assigning new values via indexing
- **Performing mathematical operations** with vectors using elementwise operators and math functions
- **Converting** between row and column vectors using the transpose operator
- **Getting a vector's dimensions** using `size` and `length`

*Copyright 2025 The MathWorks, Inc.*
