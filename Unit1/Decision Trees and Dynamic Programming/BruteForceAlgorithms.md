# Brute Force Algorithms 

1. Enumerate all possible combinations.
2. Remove the ones that do not satisfy the requirements.
3. Choose the best from remaining combinations.

## Search Tree Implementation - Enumeration
Create 2 child node from its parent. One node (left node) represents taking the item,  other  node(right node) represent not taking the item. It is depth first enumeration. From the left, you should go to the deepest possible solution. After that, come back and create the possible nodes remaining.

> Number of nodes at level i = 2^i

The pseudo code is as follows:

``` python
def maxVal(available_items,available_weight):
    """
    It is an recursive function that returns the total_value of the solution and the items
    """
    if available_items == empty or available_weight < 0:
        result = (0,())
    elif available_items[0].weight() > available_weight: 
        #only consider right branch - not taking the item
        result = maxVal(available_items[1:],available_weight)
    else: 
        candidate_item = available_items[0]
        #consider right branch - not taking the item 
        valueWithout, WithOut_to_take = maxVal(available_items[1:],available_weight)
        #consider left branch - taking the item
        valueWith, With_to_take = maxVal(available_items[1:],available_weight - candidate_item.weight())
        valueWith = valueWith + candidate_item.value()
        #decide which is better
        if valueWith > valueWithout:
            result = valueWith, With_to_take+candidate_item 
        else:
            result =valueWithout, WithOut_to_take
    return result
```

The algorithm gives a better solution (more optimal compared to the Greedy Algorithm). And, we do not examine all the nodes; we implement DFS. Hence, the complexity is reduced.

