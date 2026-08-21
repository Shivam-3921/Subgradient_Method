# Geometric Median via the Subgradient Method

This project implements the **subgradient method** to solve the geometric median (Fermat–Weber point) problem — finding the point that minimizes the sum of Euclidean distances to a set of given points. Since the objective function (a sum of norms) is convex but non-differentiable at the data points, standard gradient descent doesn't apply directly, making this a natural setting for subgradient-based optimization.

## Problem

Given points `a_1, ..., a_m` in R², find:

```
x* = argmin_x  Σ ||x - a_i||
```

This is a classical non-smooth convex optimization problem with applications in facility location, clustering, and robust estimation.

## Approach

- Derived the subdifferential of the sum-of-norms objective
- Implemented an iterative subgradient descent method with a fixed learning rate and convergence tolerance
- Validated the method on a small toy example (3 points) with a visualized solution
- Applied the method to a real-world dataset of **1,217 U.S. city coordinates** to find the geometric median — i.e., the most "central" U.S. city location minimizing total distance to all others

## Results

The subgradient method converges reliably to the geometric median in both the toy case and the full 1,217-point real-world dataset, with the optimal solution visualized against the input data in each case (see notebook plots).

## Tech Stack

Python, NumPy, Pandas, Matplotlib

## Files

- `Subgradient.ipynb` — implementation, toy example, and real-data application
- `USCity.xlsx` — U.S. city coordinate dataset used for the real-world application
