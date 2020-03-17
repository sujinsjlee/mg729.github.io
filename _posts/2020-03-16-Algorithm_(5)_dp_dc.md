---
layout: post
published: false
title: Algorithm - Dynamic Programming & Divide and Conqure (Concept and C++ examples)
description: (5) Understanding of DP & Divide and Conqure algorithm
modified: 2020-03-16
tags: [Algorithm]
categories: [Algorithm]
---

## Dynamic Programming and Divide and Conquer

> Dynamic planning method (often called DP)


  - Algorithm that solves the problem of the small input size, solves the problem of the larger size, and finally solves the whole problem by using the solution of the partial problem
  - With bottom-up approach, find the lowest answer, save it, and solve the upper problem using the result
  - Memoization technique is used
    - Memoization: A technique that saves the previously calculated values ​​when the program is executed and speeds up the overall execution by not recalculating.
  - When slicing problems, partial problems are duplicated and recycled
    - Example: Fibonacci sequence


> Split conquest


  - Algorithm to solve the problems by dividing each other until the problem cannot be divided, and then merging again to get the answer to the problem
  - With the Hayang-sik approach, descending downward to find the upper answer, the lower answer
    - Generally implemented as a recursive function
  - When splitting a problem, partial problems do not overlap with each other
    - Example: merge sort, quick sort, etc.

### Commonalities and differences
- Common
  - Split the problem into small pieces
- difference
  - Dynamic programming
    - Partial problems are duplicated and recycled when solving high-level problems
    - Using the Memoization technique (used as an optimization technique to save and recycle answers to partial problems)
  - Split conquest
    - Partial problems do not overlap with each other
    - No Memoization technique

## Understanding Dynamic Programming  
* fibonacci