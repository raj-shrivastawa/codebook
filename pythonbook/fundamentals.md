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

### prime number using for loop(Not the best algo but to clear for loop)
```python
for num in range(2,10):
    for n in range(2, num):
        if num % n == 0:
            print(f"{num} is divisible by {n}")
            break
    else:
        print(f"{num} is prime number")
```

### List slicing

### List comprehension

### conditional compehension

### sets and dictionaries comprehension

### zip function
```python
a = ["Raj", "Ganesh", "Esanya", "Manu", "Arun"]
b = ["CSM", "CSM", "CSM", "Raksha", "Raksha"]
print(list(zip(a,b))) # if length of b is greater than a then extra value will be ignored.
```

### enumerate function
```python
a = ["Raj", "ranjan", "amit", "alice"]
for counter,name in enumerate(a):
    print(counter,name)

print(list(enumerate(a, start=1))) # print(list(zip([0,1,2,3], a)))
print(dict(enumerate(a)))
```

### Function
```python
def myfunction():
    pass
```
