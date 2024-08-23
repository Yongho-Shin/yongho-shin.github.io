---
layout: post
title:  "Convex Hull"
#date: 2024=08-23
categories: Algorithm
---

## Introduction

The ***Convex Hull*** is a subset of points that form <u>**a smallest convex polygon which includes all of points in the set**</u>, especially on the 2-dimensional space.

![img](https://miro.medium.com/v2/resize:fit:677/1*F4IUmOJbbLMJiTgHxpoc7Q.png)

On above figures, there are a lot of points on the 2-dimensional space and suppose the set of all of points *SET A*. Then, it's possible to find some points that form a smallest convex polygon including all of points in the *SET A* and we can set the *SET B* including these points {q1, ..., q7}. To find *SET B* from *SET A*, there are several algorithms and the ***Graham Scan*** is most famous one among them.



## Graham Scan

- Find a subset form the convex hull from a set of points in the 2-dimensional space.
- Input : A set of points of 2-dimensional space
- Output : A subset of the input, forming the convex hull.
- Time Complexity : O(nlogn)

