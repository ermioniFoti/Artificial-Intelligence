# Unruly Puzzle Solver: Search & Optimization

A software project developed to solve the **Unruly** logic puzzle using Artificial Intelligence techniques. This repository contains implementations of **Systematic Search** and **Simulated Annealing** algorithms. 

This project was developed as part of the **1st Assignment** for the **Artificial Intelligence (PLH 311)** course at the **Technical University of Crete** (Fall 2024).



## 📌 Project Overview

**Unruly** is a logic puzzle played on an $n \times m$ grid. The goal is to color every square either Black or White such that:

1.  **No three consecutive squares** (horizontally or vertically) are the same color.
2.  Each row and each column contains an **equal number** of Black and White squares.



This project solves the puzzle using two distinct AI approaches:
* **Systematic Search (Problem 4):** Ensures finding a solution if one exists.
* **Simulated Annealing (Problem 5):** An optimization approach to minimize rule violations.



## 🚀 Implemented Algorithms

### 1. Systematic Search 
Solves the puzzle by exploring the state space to find a valid solution or determine that none exists.

* **Approach:** Formulates Unruly as a Search Problem using systematic strategies (e.g., DFS, BFS).
* **Functionality:**
    * Reads an initial puzzle state from a text file.
    * Prompts the user for a **maximum number of nodes** to expand.
    * Executes the search to fill the empty squares while satisfying constraints.
* **Output:**
    * Displays the solved grid state in standard string format.
    * Reports **Execution Time** (in seconds).
    * Reports the total **Number of Nodes Expanded**.

### 2. Simulated Annealing 
Approaches the puzzle as an optimization problem, minimizing the number of rule violations.



* **Approach:** Starts with a complete (but likely invalid) assignment and iteratively improves it using a cooling schedule.
* **Objective Function ($f(s)$):** Minimizes the sum of:
    * Difference between Black and White counts in every row and column.
    * Count of "3-in-a-row" violations in every row and column.
* **Key Features:**
    * **Local Moves:** Modifies the grid (e.g., swapping colors) without altering the fixed initial squares.
    * **Cooling Schedule:** Implements a temperature decay function to escape local optima.
* **Output:**
    * Returns the "best found" solution (ideally with 0 violations).
    * Reports the **Number of Violations** in the final state.
    * Reports **Execution Time** and **Total Steps** taken.



## 📄 Input File Format

The program accepts input files containing a single line of ASCII text describing the puzzle state.

**Format:** `RxC: <compressed_string>`

* **R, C:** Number of Rows and Columns (must be even, $\ge 6$).
* **String:** Encodes the position of colored squares.
    * **Capital Letters (A-Z):** Represent **Black** squares.
    * **Small Letters (a-z):** Represent **White** squares.
    * The letter value indicates the distance from the previous colored square (e.g., 'a' = 1 step, 'b' = 2 steps).

**Example (8x8 Grid):**
`8x8: bceadEDgCcAgCcabBi`



## 📊 Analysis

The project also includes a performance analysis for Simulated Annealing:
* **Success Rate:** The percentage of runs that find a perfect solution ($f(s)=0$).
* **Convergence:** Average number of steps and time required to solve instances of varying difficulty.

---

*Developed for the School of Electrical and Computer Engineering, Technical University of Crete.*
