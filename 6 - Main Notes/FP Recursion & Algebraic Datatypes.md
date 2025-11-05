2024-10-10 12:38

Status: #new 

Tags: [[Functional Programming]]

# FP Recursion & Algebraic Datatypes

# Case Expressions
## Numbers
```
case num of 
	1 -> "one"
	2 -> "two"
	3 -> "three"
	_ -> "something else"
```

## Lists
```
case list of 
	[] -> "empty"
	[x] -> "one element"
	_ -> "more elements"
```

Allows **pattern matching** within a definition

# Guards
Rather then doing a chain of if-else statements
```
gradeFromGPA :: Int -> String
gradeFromGPA gpa = 
	if gpa >= 18
	then "A" else
	if gpa >= 15
	then "B" else
	if gpa >= 12
	then "C" else
	"below C"
``` 

We can use guard notations which are cleaner
```
gradeFromGPA :: Int -> String
gradeFromGPA gpa
	| gpa >= 18 = "A"
	| gpa >= 15 = "B"
	| gpa >= 12 = "C"
	| otherwise = "below C"
```

# How are lists defined
Lists are inductively-defined data structures 
```
[] :: [a]
(:) :: a -> [a] -> [a]
```
So [1,2,3] is actually syntactic sugar for 
`1 : (2 : (3 : [] )))`
Where `:` is putting elements on top of the empty list

# Designing Recursive Functions
## Steps
1. Think about the **structure** you are defining recursion on?
	- Integers? Lists?
2. Write a **base case** you will want functions to terminate
3. Write a **recursive** or **inductive** case which calls the same function with an argument which **converges to the base case**
## Example
```
listSum :: [Int] -> Int
listSum [] = 0 -- Base Case
listSum (x:xs) = 
	x + (listSum xs) -- Recursive case
```
Base Case
- Sum of elements in an empty list is 0
Recursive case
- Add current elements to sum of the rest of the list

# Mutual Recursion
Sometimes we want to write functions which call each other
Haskell allows that as long as all definitions are in scope

## Example
```
tick :: Int -> String
tick 0 = ""
tick n =
	"tick " ++ (tock (n-1))
	
tock :: Int -> String
tock 0 = ""
tock n =
	"tock " ++ (tick (n-1))
```

# Defining Data Types
```
data Season = 
	Spring | Summer | Autumn | Winter
```
- This a **sum type**, with alternative values
- Doing `:t Spring` would return `Spring :: Season` due to Spring being a Season data type

```
data UofgGrade = Grade Char Int

-- Example: Grade 'B' 3
```
- This is a **product type** with a combination of values

## Example
```
-- Defining a new type UofGGrade 
data GradeLetter = A | B | C | D | E | F | G | H -- Enumerating valid grade letters 
	deriving (Show, Eq) -- Defining the UofGGrade type that combines a grade letter and an integer 

data UofGGrade = Grade GradeLetter Int 
	deriving (Show, Eq) -- Example usage 
	
exampleGrade :: UofGGrade 
exampleGrade = Grade A 85
```
- Example of enumerating the letters 

```
example1 = Grade A 90  -- Grade A with a score of 90
example2 = Grade C 65  -- Grade C with a score of 65
example3 = Grade H 50  -- Grade H with a score of 50
```
- Creating instances of UofGGrade

```
describeGrade :: UofGGrade -> String
describeGrade (Grade A score) = "Excellent! You scored " ++ show score
describeGrade (Grade B score) = "Great! You scored " ++ show score
describeGrade (Grade C score) = "Good! You scored " ++ show score
describeGrade (Grade letter score) = "You scored " ++ show score ++ " with grade " ++ show letter
```
- Using pattern matching to process the grades

# Recursive Data Types
It is a data type that is defined in terms of itself. 

```
data Tree = Leaf --Represents a leaf (an empty node)
			| Node Int Tree Tree - A node wiht an Int Value and 2 subtrees
```

Complex Example:
```
complexTree :: Tree
complexTree = Node 8
                (Node 3 Leaf Leaf)                   -- Left subtree
                (Node 10                             -- Right subtree
                    (Node 9 Leaf Leaf)               -- Left child of 10
                    (Node 12 Leaf Leaf))             -- Right child of 10

```
### Summary

- **`Tree`** is a recursive data type that can represent binary trees.
- **`Leaf`** is the base case, representing the end of a branch (a leaf node).
- **`Node Int Tree Tree`** represents a node with an `Int` value and two subtrees, which are also `Tree` structures.
- This recursive structure allows for building binary trees of any depth, and each node can have two subtrees (left and right), which can either be more nodes or leaf nodes.

# Parameterised Data Types

```
data BinaryTree a =
	Leaf | Node a (BinaryTree a) (BinaryTree a)
```
- We can parameterise a data type by putting a type variable on the left-hand side of the data definition
- So this tree can contain any type of value

# Maybe Type
```
data Maybe a = Just a | Nothing
safeHead :: [a] -> Maybe a 
safeHead []      = Nothing
safeHead (x : _) = Just x
```
- Used for potentially-failing computations

#### Explanation:

- **`safeHead :: [a] -> Maybe a`**: The type signature means that `safeHead` takes a list of any type (`[a]`) and returns a `Maybe a`, meaning it could either return a `Just` with a value of type `a`, or `Nothing` if the list is empty.
    
- **`safeHead [] = Nothing`**:
    
    - This pattern matches an **empty list** (`[]`). If the list is empty, there is no first element to return, so the function returns `Nothing`, indicating the absence of a value.
- **`safeHead (x : _) = Just x`**:
    
    - This pattern matches a non-empty list (`x : _`), where `x` is the **head** (first element) of the list and `_` represents the rest of the list (which we don’t need).
    - The function returns `Just x`, wrapping the first element `x` in a `Just` to indicate that there is a valid result.

### What Does This Function Do?

The purpose of `safeHead` is to **safely retrieve** the first element of a list:

- If the list is empty, `safeHead` returns `Nothing`, signaling that there is no head element.
- If the list is not empty, `safeHead` returns `Just x`, where `x` is the first element of the list.

# References

