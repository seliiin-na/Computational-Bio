### Q1: Subset Sum
Check whether we can add together some subset of the numbers in the list to get a sum equal to the target

```python
def subset(target, numList):
    # base cases: one for each input to prevent infinite loop
    # order MATTERS! 2nd case is false only based on the fact that target is non-zero
    if target == 0:
        return True
    elif numList == []:
        return False
    elif numList[0] > target:                            # num is too large, don't need it
        return subset(target, numList[1:])
    else:  
        # branching decision tree
        useIt = subset(target - numList[0], numList[1:]) # use 1st element
        loseIt = subset(target, numList[1:])             # discard 1st element 
        # BELOW: if either useIt or loseIt returns True, the whole thing returns True
        return useIt or loseIt
    

```
