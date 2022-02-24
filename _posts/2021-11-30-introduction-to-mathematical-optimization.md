---
title: "Introduction to Mathematical Optimization"
layout: post
date: 2021-11-30 19:25
tag:
- optimization
- coursework
image: /assets/images/posts/introduction-to-mathematical-optimization/system-of-equations.jpg
headerImage: true
description: "An introduction to basic mathematical optimization techniques and their applications"
category: blog
author: kavishhukmani
externalLink: false
---

<span class="evidence">This report was initially written as part of my coursework for BAX 401 - Information, Impacts and Insights at UC Davis.</span>

# Introduction

A problem is classified as an optimization problem when the goal is to maximize the efficiency of a process by minimizing or maximizing an objective function. This is done by adjusting the values for a set of variables, known as the decision variables, such that they satisfy a set of predefined constraints while providing the best possible solution to the objective.
Optimization techniques can be classified into two groups-

## Deterministic Optimization Methods

Problems that have no random or unknown elements are solved using deterministic techniques. The solution provided in such cases is guaranteed to be the global optimum. Depending on the nature of the system of equations used to represent the problem, they are classified into categories such as Linear Programming(LP), Mixed Integer Programming(MIP), Nonlinear Programming(NLP) etc. These problems are typically solved using solving programs or “solvers”, which use a combination of various techniques such as Branch and Bound, Plane Cutting, Simplex Method etc. The primary challenge lies in defining the constraints in a manner that is easy to solve. There are both open-source and proprietary solvers available with varying feature sets and efficiency.

Deterministic optimization is generally used for problems that can be represented using a small number of equations or when a guaranteed global optimum is required. This is due to the fact that combinatorial explosion from a large number of constraint equations causes the solution time to increase exponentially. Formulation of equations for large scale problems requires exploitation of intricacies using domain knowledge to decrease the time taken to solve it.

## Stochastic Optimization Methods

Stochastic or probabilistic methods are used to solve problems with random or unknown elements. They cannot guarantee the optimality of the solution but instead, provide its probability of being the global optimum. This probability increases as time goes on and reaches 1 given infinite time. There are various methods that take different approaches to solve such problems. The following are some of the most popular methods-

### Genetic Algorithms

Genetic algorithms are a versatile approach based on the Theory of Natural Selection. The objective is represented in the form of a fitness function which measures the fitness of each individual. We begin with a population of potential solutions from which we pick the two fittest individuals and create a set of children by combining them. These children then go on to form the next population iteration. This process continues until some cutoff criterion, such as a limit on the number of generations, is reached.

### Simulated Annealing

Simulated annealing is generally used in discrete problems with uneven surfaces consisting of a large number of local minimas. It is based on the process of physical annealing in which metals are heated up and cooled down to change their physical properties. In simulated annealing, the optimization function can accept suboptimal solutions when the “temperature” is high, leading to exploration. This leads to the algorithm locating the approximate global minima rather than getting stuck at a local minima like a more precise algorithm such as gradient descent.

### Tabu Search

Tabu search is another approach used to solve problems with uneven surfaces. However, it can be applied to both discrete and continuous problems. It works by banning a set of moves that would lead to the same solution as those taken recently, thereby making some moves tabu or taboo. This leads to the acceptance of suboptimal solutions, which allows escaping local minima.

# Applications

The broad definition of mathematical optimization allows it to be applied across various domains from Operations Research to Computer Science. However, these can be generalized to basic problem types prevalent across fields. The following are a few examples of such problem types-

## Resource Allocation Optimization (or Scheduling Problems)

Such problems deal with effectively utilizing a set of resources given constraints to maximize an objective, usually revenue or profit. A typical example of such a problem is the optimization of machine usage/labor in a factory that is capable of producing multiple products.

## Route Optimization

Also known as the Traveling Salesman Problem (and its variants), these are problems that can be represented in the form of a graph where we need to traverse over the nodes while keeping the sum of edge costs/weights minimum. A typical example is the optimization of the routes for delivery trucks in a city.
