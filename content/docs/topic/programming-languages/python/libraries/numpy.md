---
title: "NumPy"
---

# NumPy

## Arrays

### Creating Arrays

#### One-Dimensional Arrays

```python
mylist = [1, 2, 3]
x = np.array(mylist)
```

#### Multi-Dimensional Arrays

```python
m = np.array([[7,8,9],[10,11,12]])
```

#### Arange

```python
# n = np.arange(start, stop, step_size)
n = np.arange(0, 30, 2)

# reshape n to 3x5 array
n = n.reshape(3, 5)
```

#### Linspace

```python
# np.linspace(start, stop, num_of_elems)
o = np.linspace(0, 4, 9)
```

### Manipulating Arrays

#### Repeat

```python
# np.repeat(input_array, num_repetitions)
np.repeat([1,2,3],3)
```

#### Vstack/Hstack

```python
# np.vstack([first_array, second_array,...])
np.vstack([p,2*p])
```

## Array Iteration

```python
test = np.random(0,10, (4,3))

for row in test:
    print(row)

for i in range(len(test)):
    print(test[i])

for i,row in enumerate(ttest):
    print('row',i,'is',row)
```

## Operations

### Dot Products

```python
x.dot(y)
```

### Array Transposing

```python
x.T
```

### Array Element Types

```python
x.dtype
```

### Set Array Type

```python
z = x.stype('f')
z.dtype
```

### Index of Maximum/Minimum

```python
a.argmax()
a.argmin()
```
