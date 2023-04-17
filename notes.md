# Data structures Complexity and  Algorithms

## Menu  
[Matrix & List cmprh]()  
[Map & Filter]()  
[Tuples]()  
[Sets]()  
[Dictionary]()  

## 1. Matrices and List comprehension

### Matrix
#### Mathematics
It is a representation of *numbers, symbols, or expressions* in a 2D array  
#### Computer Science
Store values in *rows and columns*  
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
When...
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
- **1+ For clauses** to explain its members
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
Objective: Use list comprehension to turn a 2D array called *vec* to a single list  

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
vec is an example of a [*matrix*](https://github.com/kazoo-cs/Data-Structures-Complexity-and-Algorithms/edit/main/notes.md#matrix) in Python 3 (2D List)

In order to take each and every value from the *rows*, follow the procedures.
- Each item will be explained as variable 'value'
- To access the values, take out each row/list using a **for clause** 
    - for row in vec
- Finally, use another **for clause** to indicate what values exist in the row/list acquired from *for row in vec*
    - for value in row
 
 The **ORDER** of **for clauses MATTER!**
 
 ## 2. Map and Filter in Python 3
 #### The Map Function
 Apply a **function** to an *iterable* data  
 Built in function that applies a given function to every single item in the given list  
 How to format:  
 ```python
 map(function_name, sequence)  
```
#### The Filter Function
Built in function
Filters out items in a sequence where a function decides 

## 3. Tuples
It is an *immutable* sequenceable data-type object
- Declared with *parenthesis* ()
- ()is an *empty* tuple
- (50,) is a singleton tuple; the comma is *required*
- Tuples are *sliceable*; therefore indexabl eusing square brackets

Operators
- Len function
- Concatenation (addition of same data type)
- Repetition (multiplication of same data type)
- Membership
- Max/Min functions
- Tuple function
## 4. Sets
Well-defined collectin of distinct objects, considered as an objet in its own right  
Aset can be denoted with {} brackets mathematically
- Does *not* need to be ordered
- Can contain *duplicates*; moreover, the set with no duplicates of same objects will still be considered equal
    -  {a,b,c} == {a,a,b,b,b,c,c,c,c}
-  A set can be expressed as a mathematical relationship
    -  A = {x|2x+6 = 0}
        -  "Set A consists of memers of x; such tha t2 times x plus6 equals 0"
### Membership
#### Subset
One set apart from another  
A = {Mark, Angela}  
B = {Mark, Angela, Frank, Laura}  
Any set whose its members are elements of another set  
"SetA is a subset of setB"  
#### Proper Subset
A = {Mark, Angela}  
B = {Mark, Angela, Frank, Laura}  
A cannot be equal to B  
#### Power Set
A set with all the subsets of the set  
B = {Fred, Mary}  
P(B) = { {}, {Fred}, {Mary}, {Fred, Mary}}  
#### Union
The union of towo sets is the result of all its member into a singular set with *dulicate members discarded*  
A = {Mary,Larry,Angela}
B = {Mary,Frank,Fred}
A U B = {Mary, Larry, Frank, Angela, Fred}
#### Intersection

#### Subtraction
Does not exist
Left to Right
A - B results to removing the members that exist in set B from set A

#### Symmetric Difference
Elements that are in either set, BUT they cannot intersect  

#### Universe Set
A set that 

#### Complement
left overs that doesnt exist 

### Sets in Python 3
A set is an unordered collection with no duplicate elements
Operations
- Union
- Intersection
- Difference
- Symmetric Difference

Built in DATA-TYPE in Python 3
```python
basket = {'apple','orange','apple','pear','orange'}

print("orange" in basket) # True
print(basket)
# output -> {'apple','orange','pear'}

# using set()
a = set('abracadabra')
print(a) 
# output -> {'a','b','r','c','d'}
# Duplicates disappear
```
Set can check the unique address for 
Tuples, lists check left to right, checking each and every value
```python
# Set Operations
a = set('abracadabra') # a = {'a','b','r','c','d'}
b = set
```
Why are there methods and operators??  
**Mutability** 

#### Set comprehension
a = set() is an EMPTY set not {}

Check membership -> x in set
Determine the number of members -> len(set)
Iterate throguh the set -> for x in set

What can't be done
-Sets are NOT INDEXABLE

Built in statements
Let s be a set
s.add(elem) # adds elem to the set
s.remove(elem) # removes elem from the set; ERROR if elem DNE
s.discard
s.clear

Coding notes
"in" is more efficient than strings and math operators  
Functional programming f(g(x))
g(x) -> f(x)


## 5. Dictionary
