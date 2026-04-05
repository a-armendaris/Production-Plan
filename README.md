# Linear Programming for Enterprise Resource Planning
## Executive Summary
This project implements a production planning model using linear programming to optimize a factory’s production plan. The aim is to maximize profit / minimize cost subject to constraints like capacity, labor, demand, and resources. A linear program consists of decision variables, an objective function, and linear constraints that represent real-world production limitations.
The model determines:

- How much of each product to produce internally
- How much to purchase externally
- How to allocate limited production resources efficiently

This project demonstrates applied operations research, cost optimization, and data-driven decision modeling using Python.

## Features
- Mathematical model for production optimization
- Decision variable setup for resource allocation
- Objective function implementation
- Constraint formulation for production limits and requirements
- Solutions obtained via LP solver 
- Visualization / results summary
  
## Tools Used
- Python
- Pandas (data processing)
- PuLP (optimization modeling)
- Linear Programming
- Cost minimization modeling
- Resource allocation analysis

---

### Technical Skills

* Python
* Pandas (data processing & transformation)
* PuLP (Linear Programming modeling & solving)
* Mathematical Optimization
* Cost Modeling
* Constraint Programming
* CSV data handling & export

### Analytical Skills

* Operations Research modeling
* Resource allocation optimization
* Cost trade-off analysis (Make vs Buy decisions)
* Constraint-based decision systems
* Optimization result interpretation

---

## Project Structure

* `Production Plan (linear programming).ipynb` – Main optimization notebook
* Input datasets:

  * Product demand & cost data
  * Resource capacity data
* Output:

  * Optimal production & purchasing quantities (`optimal_quantities.csv`)
  * Exported LP model file for transparency

---

## Methodology

### Data Preparation

Two datasets were loaded and processed using **Pandas**:

**Product Data**

* Demand per product
* Internal production cost
* External purchasing cost
* Resource time requirements per unit

**Resource Data**

* Available capacity per resource
* Operating parameters

Data was cleaned and converted into structured parameter lists for modeling.

---

### Model Formulation

The problem was formulated as a **cost minimization linear program**.

#### Decision Variables

For each product:

* `X_i` = Quantity produced internally
* `Y_i` = Quantity purchased externally

Both variables are continuous and non-negative.

---

#### Objective Function

Minimize total cost:

[
\text{Minimize} \quad \sum (C_i X_i + P_i Y_i)
]

Where:

* (C_i) = Internal production cost
* (P_i) = Purchasing cost

This captures the trade-off between producing in-house and outsourcing.

---

#### Constraints

**1. Demand Satisfaction**

[
X_i + Y_i \ge D_i
]

Ensures customer demand is fully met.

**2. Resource Capacity**

[
\sum (t_{ri} X_i) \le \text{Available Capacity}_r
]

Ensures production does not exceed available resource time.

---

### Model Implementation

* Implemented using **PuLP**
* Constraints generated dynamically via loops
* LP file exported for validation
* Solver executed to find optimal solution
* Results extracted and saved to CSV

---

## Results

The optimization successfully produced an **optimal production strategy** that:

* Meets all product demand requirements
* Respects all resource capacity constraints
* Minimizes total operational cost

### Key Insights

* Identifies when it is more cost-efficient to **produce internally**
* Identifies when it is optimal to **purchase externally**
* Reveals which resources act as **capacity bottlenecks**
* Quantifies the minimum achievable total cost

When internal production is cheaper and capacity is available, the model prioritizes manufacturing. When capacity is constrained or purchasing is cheaper, the model shifts toward outsourcing.

---

## Recommendations for Future Improvements

### 1. Integer Programming

Convert to Integer Linear Programming (ILP) if production must occur in whole units or batches.

### 2. Profit Maximization Model

Extend the model to include revenue and maximize profit instead of minimizing cost.

### 3. Sensitivity & Scenario Analysis

Add what-if analysis for:

* Demand fluctuations
* Capacity changes
* Cost variations

This would enable risk analysis and capacity planning decisions.

### 4. Fixed & Setup Costs

Incorporate:

* Setup costs
* Overtime costs
* Fixed operating costs

This would increase model realism.

### 5. Visualization Dashboard

Add charts for:

* Resource utilization
* Cost breakdown
* Produce vs Buy comparison
* Bottleneck identification

### 6. Multi-Period Planning

Extend to:

* Multi-week/month planning
* Inventory holding costs
* Rolling horizon optimization

---

## Business Impact

This model supports:

* Data-driven production planning
* Strategic outsourcing decisions
* Cost minimization under constraints
* Capacity planning and bottleneck analysis

It demonstrates practical application of optimization techniques in operations, supply chain, and analytics environments.

---


## Concepts Demonstrated

* Linear Programming
* Operations Research
* Resource Allocation
* Cost Optimization
* Mathematical Modeling in Python

---

