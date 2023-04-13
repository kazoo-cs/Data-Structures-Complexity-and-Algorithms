# Data structures Complexity and  Algorithms

## 1. Matrices and List comprehension

### Matrix
#### Mathematics
It is a representation of numbers, symbols, or expressions in a 2D array  
#### Computer Science
Store values in rows and columns  
Utilize lists in a list (2D)  
```python
# Python 3 representation of Matrix A
matrix_A = [
    [1, 2, 3, 4],
    [5, 6, 7, 8]
]

# Accessing Matrix A
print(f'Row 1: {matrix_A[0]}') # Row 1: [1, 2, 3, 4]
print(f'Value at Row 2 Column 2: {matrix_A[1][1]}') # Value at Row 2 Column 2: 6
```
No data structure named "Matrix" is found in Python 3  

#### Rules of Matrix
- All rows must have the **same quantity** of values
- All columns must have the **same quantity** of values
- All items within the 2D List must have the **same data types**
- Indexing starts at **0**, meaning row 1 is matrix_A[0] and row 2 is matrix_A[1]

### List Comprehension 
It is a method in creating a list in Python 3

#### When is it used?
- List is the result of operations applied to **all of its items**
- List is made from iteration
- List is a member of another list/sequence/iterable data that satisfies a certain condition

#### Example 1
Objective: Create a list that squares nums 0~9
```python
# Old Method
squares = []
for i in range(10):
    squares.append(i ** 2)

print(f'Our result: {squares}') # Our result: [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]

# List Comprehension

squares = [i**2 for i in range(10)]

print(f'Our new result: {squares}') 
# Our new result: [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
```
##### Explanation
List comprehension consists of...  
- **Square brackets []** containing an expression describing the list
- **1+ For clauses ** to explain its members
- **0+ If clauses** when complexity is needed

Examine: [i\*\*2 for i in range(10)]
- i\*\*2 for i in range(10) is the *expression* that describes the list
- i\*\*2 describes each *item* in the list
- i is taken from the **for clause**
- for i in range(10) describes *where* **i** comes from

#### Example 2
Objective: Create the list [[1, 3], [1, 4], [2, 3], [2, 1], [2, 4], [3, 1], [3, 4]]  
From  
A = [1,2,3]  
B = [3,1,4]
```python
# Solution
a = [1,2,3]
b = [3,1,4]

result = [[x, y] for x in a for y in b if x != y]
print(result) 
# [[1, 3], [1, 4], [2, 3], [2, 1], [2, 4], [3, 1], [3, 4]]
```
##### Explanation
- Items in the list must be in shape [x,y]
- There will be **2 for clauses** because there are two sources of input
  - value **x** comes from list **a**
  - value **y** comes from list **b**
- A condition must be made, which is x != y in this case
    - As long as x != y is true, item [x,y] will be added to the resulting list
#### Example 3
Objective: Use list comprehension to turn a 2D array called vec to a single list  

vec = [[1,2,3], [4,5,6], [7,8,9]]  
Output: [1, 2, 3, 4, 5, 6, 7, 8, 9]  
```python
# Solution

vec = [[1,2,3], [4,5,6], [7,8,9]]

result = [value for row in vec for value in row]
print('Vec as a single list of values: %s' % result)
# Vec as a single list of values: [1, 2, 3, 4, 5, 6, 7, 8, 9]
```
##### Explanation
vec is an example of a *matrix* in Python 3 (2D List)

In order to take each and every value from the *rows*, follow the procedures.
- Each item will be explained as variable 'value'
- To access the values, take out each row/list using a **for clause** 
    - for row in vec
- Finally, use another **for clause** to indicate what values exist in the row/list acquired from *for row in vec*
    - for value in row
 
 The **ORDER** of **for clauses MATTER!**
