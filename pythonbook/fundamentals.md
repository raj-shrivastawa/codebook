### if else
```python
if condition:
    statement
elif condition:
    statement
else:
    statement
```

### loops (while, for)
```python
while condition:
    statement
```  
* else with loop
```python
l = ["ok", "ok", "ok", "faulty", "ok", "ok"]
for d in l:
    if d == "faulty":
        break
    print("shipping")
# else condition will run if loop run without break
else:
    print("All cars shipped successfully")
```

### iterating over dictionaries
```python
a = {"name": "raj", "age":25}
for v in a: print(v) # will iterate over keys.
for v in a.values(): print(v) # iterate over values
for k,v in a.ietms(): print(k,v) # iterate over keys and values
```

### Destructuring syntax and tuple unpacking
```python
a = 1,2 # Its a tuple
c,d = a
# It can be benefitial in the loop.
a = [('raj',1), ('sonal', 2)]
for name,num in a:
    print(name)
    print(num)
a = [1, 2, 3, 4, 5, 6]
first, *middle, last = a
*first, last = a
```

### break and continue
```python
l = ["ok", "ok", "ok", "faulty", "ok", "ok"]
for d in l:
    if d == "faulty":
        break # here loop will exit if condition match.
        continue # loop will continue to next by skipping next statement
    print("shipping")
```
