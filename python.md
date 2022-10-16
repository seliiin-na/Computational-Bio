### Python Syntax Notes (List vs. String):
* length of list & string: `len(list)`

* add to a list: `list.append(item)`
* add to string (concatenate): `str += ""`

---
### Practice Qs

##### Q1: using math `random`
```python
# generates a random letter from "A", "T", "C", or "G"
# if the last three letters generated are "ATG", it returns the total number of symbols that were generated. 
# otherwise, it repeats the process by generating a next random letter
import random
def lengthToATG():
    seq = ""
    while (seq[-3:] != "ATG"):
        seq += random.choice(["A", "T", "C", "G"])
        
    print (seq)
    return len(seq)
```

##### Q2: using `range` with stepLength



##### Q3: using `in`
`in` in for-loops
```python
for food in ["spam", "hot dog", "hamburger", "arugula"]:
    # do something
```

`in` in list/strings
```python
if "spam" in "I really love spam with chocolate": 
    print True
if 42 in [1, 6, 7, 42, 9]: 
    print "Yup!"
```
