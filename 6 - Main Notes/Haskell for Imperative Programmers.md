2024-11-10 08:34

Status: #new 

Tags: [[Functional Programming]]

# Haskell for Imperative Programmer

## Useful Functions
### head
gives the head of the list

### fst
returns the first element of a tuple

### snd
Returns the second element of a tuple

### filter
Returns the elements of a list that are true
```
filter snd [(Ace, True), (King, False), (Queen, True)]
-- snd gets the second element of the tuples

filter [True,False,True]
-- filter returns the elements in the list that are true

== [(Ace,True), (Queen, True)]
```

## Types
### Basics
```
x :: Integer
x = 1

y :: Bool
y = True

z :: Float
z = 3.14
```

### Functions
```
in_range :: Integer -> Integer -> Integer -> Boolean
in_range min max x = x >= min && x <= max

in_range 0.5 1.5 1 (Type Error)
in_range 0 5 3 (Correct)
```

## Functions
### Let
- In imperative languages, you're able to save results in a variable and return an end statement
	- This is **not declarative**
```
in_range min max x =
	in_lower_bound = min <= x;
	in_upper_bound = max >= x;
	return (in_lower_bound && in_upper_bound);
```

- We can use Let Bindings to solve this
```
in_range min max x =
	let in_lower_bound = min <= x
		in_upper_bound = max >= x
	in
	in_lower_bound && in_upper_bound
```

### Where
- Alternative to Let
```
in_range min max x = ilb && iub
where
	ilb = min <= x
	iub = max >= x
```

### If
```
in_range min max x =
	if ilb then iub else False
	where
		ilb = min <= x
		iub = max >= x
```

### Infix
#### Built-In Infix Operators
- Some operators are naturally infix such as +,-,*
```
5 + 3 -- 8
4 == 4 -- True
```

#### Using any function as an Infix
- You can turn any 2 argument function into an infix function
- You have surround it with backticks 
```
-- Without infix notation
elem 3 [1,2,3]

-- With infix notation
3 `elem` [1,2,3] -- True

-- Another example with 'mod' (modulus)
10 `mod` 3 -- 1
```

#### Custom infix operators
```
-- Define a custom operator 
(>+<) :: Int -> Int -> Int a >+< b = a + 2 * b 
-- Usage 
5 >+< 3 -- 5 + (2 * 3) = 11

-- Define a regular function with letters 
combine :: Int -> Int -> Int 
combine x y = x + 2 * y 
-- Use `combine` as an infix function by using backticks 
result = 3 `combine` 4 -- This evaluates to 3 + 2 * 4 = 11
```

# Recursion
### Loops
- Do not exist in Haskell, we have to use Recursion

### Prime Example
```
fac n = 
	if n <= 1 then
		1
	else 
		n * fac (n - 1)
```

```
fac 3
- 3 * fac 2
- - 3 * 2 * fac 1
- - - 3 * 2 * 1
- - 6 * 1
- 6
```

## Guards
- There can be an infinite number of guards
```
fac n
	| n <= 1 = 1
	| otherwise = m * fac (n-1)
```

### Pattern Matching
```
is_zero 0 = True
is_zero _ = False
```

### Accumulators
- aux = auxillary
- acc = accumulator
```
fac n = aux n 1
	where
		aux n acc
			| n <= 1 = acc
			| otherwise = aux (n-1) (n*acc)
```

# Lists
Lists can only have internal type
```
[1,2,3,4,5] :: [Integer]
```

Can be created with constructors
- Empty List
```
[]
[1,2,3,4,5]
```
- Colon, Prepend, Cons
```
x:xs
1:2:3:4:5:[]
```

#### Generating a List
```
- Create an ascending list
asc :: Int -> Int -> [Int]
asc n m
	| m < n = []
	| m == n = [m]
	| m > n = n : asc (n+1) m

asc 1 3
	=> [1,2,3]
```

### Functions on List
Use import Data.List

head
```
head :: [a] -> a
head [1,2,3,4,5]
=> 1
```

tail
```
tail :: [a] -> [a]
tail [1,2,3,4,5]
=> [2,3,4,5]
```

length
```
length :: [a] -> Int
length [1,2,3,4,5]
=> 5
```

init
- Gives a copy of a list without the last element, can't remove it as datatypes are immutable
```
init :: [a] -> [a]
init [1,2,3,4,5]
=> [1,2,3,4]
```

null
```
null :: [a] -> Bool
null []
=> True

null [1,2,3,4,5]
=> False
```

and 
```
and :: [Bool] -> Bool
and [True, False, True]
=> False
```

or 
```
or :: [Bool] -> Bool
or [True, False, True]
=> True
```

### List Comprehension
General Syntax
```
[expression | variable <- list, condition]

- Example
[x * 2 | x <- [1,2,3,4,5]]
=> [2,4,6,8,10]
```

With a condition
```
[x * 2 | x <- [1, 2, 3, 4, 5], x `mod` 2 == 0]
=> [4,8]
```

Multiple Lists
```
[(x, y) | x <- [1, 2], y <- [3, 4]]
=> [(1, 3), (1, 4), (2, 3), (2, 4)]
```

Multiple Lists with Condition
```
[x * y | x <- [1, 2, 3], y <- [4, 5, 6], x * y > 10]
=> [12, 15, 12, 18]
```

### List Patterns
Match lists of specific lengths or structures
```
-- Match an empty list
isEmpty :: [a] -> Bool
isEmpty [] = True
isEmpty _  = False

-- Match a non-empty list and separate the head and tail
headOfList :: [a] -> a
headOfList (x:_) = x
```

### Cons Patterns
```
sumList :: [Int] -> Int
sumList [] = 0
sumList (x:xs) = x + sumList xs

- A List that only takes even numbers
evens :: [Int] -> [Int]
evens [] = []
evens (x:xs)
	| mod x 2 == 0 = x : evens xs
	| otherwise = evens xs
```

### Tuples
```
addTuples :: [(Int, Int)] -> [Int]
addTuples xs = [x+y | (x,y) <- xs]

addTuples [(1,2), (2,3), (100,100)]
=> [3,5,200]
```

### List Exercises
Create a function **elem** that returns True if an element is in a given list and returns False otherwise
```
elem :: (Eq a) => a -> [a] -> Bool

- Wrong Answer
elem x xs
	| x == (x:s) = True
	| otherwise = False

- Right Answer
elem _ [] = False
elem e (x:xs) = (e == x) || (elem e xs)

- How This Works
elem 3 [1, 2, 3, 4]
- First Call: elem 3 (1:[2,3,4]) -> (3==1) || (elem 3 [2,3,4])
- Second call: `elem 3 (2:[3,4]) -> (3 == 2) || (elem 3 [3,4])`
- Third call: `elem 3 (3:[4]) -> (3 == 3) || (elem 3 [4])`
- Since (3 == 3) is True, the function returns True
```

Create a function nub that removes all duplicates from a given list
```
nub :: (Eq a) => [a] -> [a]

nub [] = []

- Wrong Answer
nub xs = [x | x <- xs, x != x]

- Right Answer
nub (x:xs)
	| x `elem` xs = nub xs
	| otherwise = x : nub xs
```

Create a function isAsc that returns True if the list given to it is a list of ascending order
```
isAsc :: [Int] -> Bool

isAsc [] = []
- Wrong Answer
isAsc (x:xs)
	| x >= head[xs] = x : isAsc xs
	| otherwise = False 

- Right Answer
isAsc [] = True
isAsc[x] = True
isAsc (x:y:xs) = 
	(x <= y) && isAsc (y:xs)
```

## Maybe
```
data Maybe a = Nothing | Just a
```
Functions should be pure, meaning it gets an input and has an output, Maybe is used when there maybe an error

So if the result is valid it will return "Just result" and if there is an error it will return "Nothing"
# References

