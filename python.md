### Python Syntax Notes (List vs. String):
* Length of list & string: `len(list)`

* Add to a list: `list.append(item)`
* Add to string (concatenate): `str += ""`
* String splicing:
    * getting the last 3 elements: `string[-3:]`
* can use `[]` to get characters from specific indices of a string
* indexing & slicing work the SAME for both lists and strings!

---
### Practice Qs

##### Q1: using math `random`
```python
# generates a random letter from "A", "T", "C", or "G"
# if the last three letters generated are "ATG", it returns the total number of symbols that were generated
# otherwise, it repeats the process by generating a next random letter
import random
def lengthToATG():
    seq = ""
    while (seq[-3:] != "ATG"):
        seq += random.choice(["A", "T", "C", "G"])
    print (seq)
    return len(seq)
```

##### Q2: using `range` with stepLen
```python
# takes a sequence of DNA nucleotides from the coding strand and 
# returns the corresponding amino acids as a string
def codingStrandToAA(DNA):
    result_aa = ""
    # walk through the DNA string 3 base pairs at a time, converting each 3-bp to aa & add to result
    for index in range(0, len(DNA), 3):
        result_aa += amino(DNA[index:index + 3])
    return result_aa
```
```python
def oneFrame(DNA):
    result = []
    # look for the 3 codon demarcation possibilities (starting at 0th, 1st, 2rd positions)
    # if sees a START codon, add the result of restOfORF() to the list 
    for index in range(0,len(DNA),3):
        if DNA[index : index + 3] == "ATG":
            result.append(restOfORF(DNA[index:]))
    return result
```

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

`in` in both for-loop & list 
```python
# takes as input a codon string (a string of three letters) and returns the corresponding amino acid
# aa is the list of amino acids 
# codons is a list of list (each inner list =  list of 3-bp codon that represent the same aa)
def amino(codon):
    for i in range(len(aa)):
        if (codon in codons[i]):
            return aa[i]
```

##### Q4: declaring list in Python:
```python
# empty list
my_list = []

# list with mixed data types
my_list = [1, "Hello", 3.4]
```


