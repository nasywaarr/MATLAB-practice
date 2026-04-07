# 🧮 MATLAB as a Calculator

A simple MATLAB project demonstrating how to use MATLAB as a calculator to solve geometric problems using:

- 📐 Pythagorean Theorem  
- 📏 Law of Cosines  

---

## Calculating the Distance Between Two Points (Pythagorean Theorem)

Two ships are approaching a lighthouse. We know that the ship at location A is 1200 meters away from the lighthouse at point C, and the ship at location B is 500 meters away from the lighthouse. It is also known that the angle at (ACB) is a right angle (90 degrees). What is the distance between the ships that are at locations A and B?  

<img width="484" height="545" alt="Screenshot (1341)" src="https://github.com/user-attachments/assets/87a47f72-5ebb-4cc2-80d0-a3aba0c16422" />  

**Create variables `a` and `b` that contain the known lengths of the triangle sides.**

```matlab
a = 1200;
b = 500;
```

**Calculate `a^2 + b^2` and store it in the variable `cSq`.**

```matlab
cSq = a^2 + b^2
```

**Calculate the hypotenuse using the `sqrt` function. Store it in the variable `c`.**

```matlab
c = sqrt(cSq)
```

---

### ✅ Results

-   cSq = 1,690,000
-   c = 1300 m

Distance between ships: 1300 meters

------------------------------------------------------------------------

## Calculating the Distance Between Two Points (Law of Cosines)

Two ships are approaching a lighthouse. We know that the ship at location A is 1200 meters away from the lighthouse at point C, and the ship at location B is 500 meters away from the lighthouse. It is also known that the angle γ is a 60-degree angle. What is the distance between the ships that are at locations A and B?  

<img width="532" height="482" alt="Screenshot (1343)" src="https://github.com/user-attachments/assets/12268adf-d3b1-431d-972f-9ef09b80cf13" />

**Create variables `a` and `b` that contain the known side lengths of the triangle.**

```matlab
a = 1200;
b = 500;
```

**Calculate the cosine of angle γ. Store it in the variable `cosGamma`.**

```matlab
cosGamma = cosd(60)
```

**Calculate `c^2` using the law of cosines: `a^2 + b^2 - 2ab·cos(γ)`. Store it in the variable `cSq`.**

```matlab
cSq = a^2 + b^2 - 2*a*b*cosGamma
```

**Calculate the length `c` using the `sqrt` function. Store it in the variable `c`.**

```matlab
c = sqrt(cSq)
```
### ✅ Results

-   cosGamma = 0.5000
-   cSq = 1,090,000
-   c = 1044 m

Distance between ships: 1044 meters

------------------------------------------------------------------------

| Scenario | Angle | Formula               | Distance |
|:--------:|:-----:|-----------------------|:--------:|
| Case 1   | 90°   | Pythagorean Theorem  | 1300 m   |
| Case 2   | 60°   | Law of Cosines       | 1044 m   |

------------------------------------------------------------------------

© 2025 The MathWorks, Inc.
