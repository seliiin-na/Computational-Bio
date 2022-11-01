## Python Dictionary (Hashmap in Java)
- **constant time lookup** –> don't need to loop to access anymore 
	- whereas in list: ineffecient to find items 


```python 
# declare a new dictionary: Note the curly brackets! *NOT* square brackets
myZooDict = {}

# add things to a dictionary: 
myZooDict["lions"] = 17
myZooDict["penguins"] = 14
myZooDict["snakes"] = 12

# "cats" and "penguins" are known as keys. 17 and 14 are the values associated with each key.

myZooDict["lions"]
```


### List vs. Dict
```python 
# list version
myZooList = [["penguins",14],["lions",17],["snakes",12]]

for item in myZooList:
    if item[0] == "lions":
        print ("List version: ", item[0],",",item[1])
                
# dict version
myZooDict = {}

myZooDict["lions"] = 17
myZooDict["penguins"] = 14
myZooDict["snakes"] = 12
```


