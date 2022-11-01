## Python Dictionary (Hashmap in Java)
- **constant time lookup** –> don't need to loop to access anymore 
	- whereas in list: ineffecient to find items 
- **memoization** 
	- check if we already know the solution to our particular problem
	- each time we make a recursive call, store the output in memo (to be retrieved later)


```python 
# declare a new dictionary: Note the curly brackets! *NOT* square brackets
myZooDict = {}

# add things to a dictionary: 
myZooDict["lions"] = 17
myZooDict["penguins"] = 14
myZooDict["snakes"] = 12

# access value by key
myZooDict["lions"]
```

### List vs. Dictionary
```python 
myZooList = [["penguins",14],["lions",17],["snakes",12]]

# list version
for item in myZooList:
    if item[0] == "lions":
        print ("List version: ", item[0],",item[1])
                
# dict version
myZooDict = {}

for item in myZooList:
    myZooList[item[0]] = item[1]
    
print("Dictionary version: ", "lions,", myZooDict["lions"])

```


