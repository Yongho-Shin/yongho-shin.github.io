---
layout: post
title:  "Convex Hull"
#date: 2024=08-23
categories: Algorithm
---

## What's the Convex Hull ?

The ***Convex Hull*** is a subset of points that form <u>a smallest convex polygon which encloses all of points in the set</u>, especially on the 2-dimensional space.

![img](https://miro.medium.com/v2/resize:fit:677/1*F4IUmOJbbLMJiTgHxpoc7Q.png)

In above figures, there are points on the 2-dimensional space and suppose the set of all of points *SET A*. Then, it's possible to find some points that form a smallest convex polygon enclosing all of points in the *SET A* and we can set these points {q1, ..., q7} to *SET B*, the Convex Hull of *SET A*.

There are several algorithms to find *SET B* from *SET A* and the ***Graham Scan*** is most famous one.

## Graham Scan

It's to find a subset that forms the convex hull from a set of points in the 2-dimensional space.
- Input : A set of points of 2-dimensional space
- Output : A subset of the input, forming the convex hull.
- Time Complexity : O(nlogn)

It has simple steps like following,

1. Select a pivot P<sub>0</sub> which is the leftmost (and bottommost if there is a tie) point.

2. Sort all of the points by their counterclockwise angle around P<sub>0</sub> and suppose that the sorted points {P<sub>0</sub>, P<sub>1</sub>, ... P<sub>n-1</sub>}, where n is the number of points.

3. Push P<sub>0</sub> and P<sub>1</sub> to a stack W and repeat following with P<sub>i</sub> from {P<sub>2</sub> ... P<sub>n-1</sub>}.

   1. Push P<sub>i</sub> to the stack W, if the P<sub>i</sub> is on the left side of line L, where L is a straight line from P<sub>top-1</sub> through P<sub>top</sub>.

   2. Pop P<sub>top</sub> from the stack W, else if the P<sub>i</sub> is not on the left side of line L <sub>from P<sub>top-1</sub> through P<sub>top</sub></sub>, then continue step#3-1 with same P<sub>i</sub>.
   
      > *Note that P<sub>top</sub> and P<sub>top-1</sub> are points on the top and below the top of the stack W. The stack W has at least two points, because P<sub>0</sub> (pivot, leftmost and bottommost point) and P<sub>1</sub> (a point with most counterclockwise angle around P<sub>0</sub>) suppose to be included to the convex hull. On the other hand, P<sub>0</sub> and P<sub>1</sub> are not going to pop out from the stack W, because all of the points are on the left side of line L <sub>from P<sub>0</sub> through P<sub>1</sub></sub>.*
   
4. Return a set of points of the stack W.









