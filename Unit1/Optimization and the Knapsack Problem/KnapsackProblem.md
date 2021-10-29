# UNIT 1 - Knapsack Problem
## Optimization Model 
An optimization model includes:
- An objective function
- A set of constraints 

Solving an optimization problem can be quite challenging computationally. Hence, we approximate them and implement a greedy algorithm such that we have a solution good enough.

---

## Knapsack Problem
Imagine we have a knapsack that has a limited space, and we have a plenty items that we need to choose among them.

There are two variants: 
- 0/1 Knapsack Problem
- Continuous Knapsack Problem 

## 0/1 Knapsack Problem
0/1 Knapsack is for the problems in which we can take an item with all its fractions or we left this item behind. 
- Items are represented as (value, weight). 
- We have a limited weight w. 
- A vector L that has a size of n. Each element in the vector represents one item. 
- A vector V that has the information whether the item at that spot taken or not (1 or -1, taken or not taken)

In the problem, we follow the following formulations: 

- The sum of V[i]*L[i].value should be maximized
- Following the constraint this sum < w

Enumerating along the all possible sets (power sets) and eliminating those who do not obey the constraint is one solution. For each item we have 1 or 0. This leads to an exponential algorithm. 

## Greedy Algorithm
While the knapsack is not full, put the best item. 

1. Start with data abstraction -> Implement a class with helper functions. 
2. Create your objects/items -> Create the options with their values.
3. Implement the greedy algorithm. 

``` python
"""
- clone the list of items from 2,sort them out wrt to keyFunction 
- sort them out wrt to keyFunction
- greedy algorithm 
"""
taken_items = []
total_cost = 0
for i in range(len(itemsCopy)):
    if items[i].cost + total_cost <= weight_limit:
        taken_items.append(items[i])
        total_cost = total_cost + items[i].cost
```
>Greedy Algorithm is n*log(n) << 2^n. Since we have a better algorithm than exponential one. 

Greedy Algorithm finds local optimum points. The solution may not give the best possible solution (global maximum). 




















