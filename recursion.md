## Recursion
* base case + general case:
	* general case: (a little bit of the work) + functionCall()

### Q1: Subset Sum
Check whether we can add together some subset of the numbers in the list to get a sum equal to the `target`

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

### Q2: Smallest # of coins for a amount (use Dictionary for memo)
Given an `amount` and a list of coin values, return the smallest # of coins to make that amount
```python
def change(amount, denominations, memo):
    if amount == 0:
        return 0 
    elif denominations == []:
        return float('infinity')
	elif (amount, denominations) in memo:
        return memo[(amount, denominations)]
    elif denominations[0] > amount:
        solution = memoizedChange(amount, denominations[1:], memo)
        memo[(amount, denominations)] = solution # store the solution to memo 
        return solution
    else:
        useIt = 1 + memoizedChange(amount-denominations[0],denominations, memo)
        loseIt = memoizedChange(amount,denominations[1:], memo)
        solution = min(useIt, loseIt)
        memo[(amount, denominations)] = solution
        return solution
```

### Q3: LCS (Longest Common Subsequence)
*Note: subsequence doesn't need to be contiguous*
```python
def LCS(S1, S2):
    
    # longest common subsequence of two input strings
    if S1 == '' or S2 == '':
        return 0
    elif S1[0] == S2[0]:
        return 1 + LCS(S1[1:], S2[1:])
    else: 
        # branching trees
        jump2 = LCS(S1, S2[1:])
        jump1 = LCS(S1[1:], S2)
        return max(jump2, jump1)
``` 


### Q4: Finding the _minimal_ set of transformations -> Aligning Sequences 
- assume simpliest transformation to cover the changes (deletion, insertion, mutation)
- matched score = matched_letter - (deletion + insertion + mutation)
	- want to maximize matched letters and minimize penalties 








