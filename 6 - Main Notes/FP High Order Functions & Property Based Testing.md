2024-10-12 12:25

Status:

Tags: [[Functional Programming]]

# FP High Order Functions & Property Based Testing

Use `:! clear` to clear cmd terminal

# Eta Reduction
```
f <=> \x -> f x
```

# Higher-order functions
A higher-order function is a function which takes another function as an argument
```
map :: (a -> b) -> [a] -> [b]
filter :: (a -> Bool) -> [a] -> [a]
twice :: (a -> a) -> a -> a
```

# Map
![[Pasted image 20241014123909.png]]
A map applies a function to every element in a list
Defined recursively as
- Building up a new list with function applied to each element

A simple example of `x:xs`  :
```
let (x:xs) = [1,2,3]
x = 1
xs = [2,3]
```

Example usage
```
map (\x -> x + 1) [1,2,3]
-- This would equal [2,3,4]
-- (\x -> x + 1) is a Anonymous function
```

How to create a map function
```
myMap :: (a -> b) -> [a] -> [b]
myMap f [] = [] -- Base Case
myMap f (x:xs) = (f x) : (myMap f xs)
	-- f :: (a -> b)
	-- x :: a
	-- xs :: [a]
	-- Target: [b]
	-- (:) :: c -> [c] -> [c]
	-- (f x) :: [b]
	-- map f xs :: [b]
```

# Filter
![[Pasted image 20241014144541.png]]
Filter retains every element which satisfies a **predicate** 
Only prepend the element if the predicate evaluates to **True**

Example Usage
```
filter (isUpper) "Hello FP Students!"
-- This returns "HFPS"
```

## Defining Map and Filter using list comprehensions
```
map f xs is equal to [f x | x <- xs]

filter p xs is equal to [x | x <- xs, p x]
```

# Fold
A fold is a way of reducing a list into a single value
Idea: We have a function which takes an element of a list, and an **accumulator** value, producing a new accumulator
We have 2 types of fold, depending on the desired **associativity**
- `fold1 :: (b -> a -> b) -> b -> [a] -> b`
- `foldr :: (a -> b -> b) -> b -> [a] -> b`

## Left Fold
```
foldl (+) 0 [1,2,3,4]
= (((0 +1 )+ 2)+ 3)+4
= 10
```
Since foldl is **left-associative**
- Brackets "bunched" at the left
- List traversed in order from left-to-right
## Right Fold
```
foldr (+) 0 [1,2,3,4]
= 1 + (2 + (3 + (4 + 0)))
= 10
```
Since foldr is **right-associative**
- Brackets "bunched" at the right
- List traversed in reverse from right to left

## Folds Side-by-Side
```
foldl :: (b -> a -> b) -> b -> [a] -> b
foldl _ acc [] = acc
foldl f acc (x:xs) = foldl f (f acc x) xs
```

```
foldr :: (b -> a -> b) -> b -> [a] -> b
foldr _ acc [] = acc
foldr f acc (x:xs) = f x (foldr f acc xs)
```

Main difference
- Recursive call outermost in left fold
- User-supplied function outermost in right fold

# QuickCheck
Import using
`import Test.QuickCheck`

Basics:
Define a property and check it with what we are expecting
`prop a b = (a + b) == (b + a)`

prop is just the name not a special keyword

When we QuickCheck this:
![[Pasted image 20241017104211.png]]

A more complex example:
```
prop xs =
	not (null xs) ==>
	(length $ tail xs) == ((length xs)-1) 
```
- `prop xs` takes a list xs as input
- `not (null xs)` checks whether the list xs is not empty. `null xs` returns True if xs is empty, so `not (null xs)` is True if the list contains at least one element.
	- This acts a guard that ensures the property only applies when xs is non-empty
- `==>` is an implication operator in QuickCheck. The expression `p == q` means that the property `q` should only be tested when the condition p is satisfied
	- In this case the property will only be tested when `not (null xs)` is True i.e, when the list is not empty
- `(length $ tail xs)` 
	- `tail xs` gives the list xs without its first element. For example:
		- `tail [1,2,3]` -> `[2,3]`
		- `tail [5]` -> `[]`
	- `length (tail xs)` computes the length of this new list after removing the first element. 
		- `$` is right associative so it runs the function call on the right first 
- `(length xs - 1)` computes the length of the new list after removing the first element
- Testing this should pass QuickCheck

Another example:
```
exceptLast :: [a] -> [a]
exceptLast [] = []  -- Base case: an empty list remains empty
exceptLast [x] = [] -- Base case: a single-element list becomes empty
exceptLast (x:xs) = x : exceptLast xs -- Recursive case: Keep Traversing

prop_exceptLast :: Eq a => [a] -> Bool
prop_exceptLast = \xs -> if length xs > 0
                         then (exceptLast xs == reverse (tail (reverse xs)))
                         else True
```

### 1. **Pattern Matching** `(x:xs)`

- The input list is matched against the pattern `(x:xs)`. In Haskell, this is a common way to decompose a list into:
    
    - `x`: The **head** of the list (the first element).
    - `xs`: The **tail** of the list (all elements after the first element).
    
    So, if you have a list like `[1, 2, 3]`, matching it as `(x:xs)` will result in:
    - `x = 1`
    - `xs = [2, 3]`

### 2. **Recursion**: `exceptLast xs`

- The function then **recursively calls itself** on `xs` (the tail of the list).
- This means that the function keeps calling itself until it reaches a base case.

### 3. **Constructing the Result**: `x : exceptLast xs`

- The expression `x : ...` is how you construct a new list in Haskell.
    - `x` is prepended to the result of the recursive call `exceptLast xs`.

So, each time you make a recursive call, the **current head element `x`** is prepended to the result of the recursive call. This effectively "builds" the result list, excluding the final element of the original list.

### Example Walkthrough:

Let's see how this works with an example list:

Suppose we call `exceptLast [1, 2, 3]`.

1. First call: `exceptLast (1:[2, 3])`
    
    - Pattern match: `x = 1`, `xs = [2, 3]`
    - Recursive call: `exceptLast [2, 3]`
    - Result: `1 : ...`
2. Second call: `exceptLast (2:[3])`
    
    - Pattern match: `x = 2`, `xs = [3]`
    - Recursive call: `exceptLast [3]`
    - Result: `2 : ...`
3. Third call: `exceptLast [3]`
    
    - Base case: `exceptLast [3] = []` (since the list has only one element)
    - This returns an empty list `[]`.

Now, we start returning results back up the recursive chain:

- In the second call: `2 : exceptLast [3]` becomes `2 : []` → `[2]`
- In the first call: `1 : exceptLast [2, 3]` becomes `1 : [2]` → `[1, 2]`

Thus, `exceptLast [1, 2, 3]` returns `[1, 2]`, which is the original list with the last element removed.

















# References

