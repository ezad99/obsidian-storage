2024-10-03 11:54

Status: #new 

Tags: [[Functional Programming]]

# FP Functions & Lists

Tuples
Deconstructing Tuples
	We can deconstruct using
		fst
		
		snd

Functions
	Functions with Single Parameter
		Maps a value to another value
	Functions with Multiple Parameters

Equation
Function Equation
Function Application
	Express can contain function calls 
Function Composition
Aside: Parenthesis

Type Variables

# List & Sequences

# List Comprehensions
Allows creation of lists based on existing lists, similar to set notation in math
Basic Syntax
`[ expression | qualifier1, qualifier2, ..., qualifierN ]
`
expression
- The value that will be included in the resulting list
qualifiers
- Conditions or generators 
- Usually consists of `let` bindings and guards

## Simple Example
`squares = [x^2 | x <- [1..10]]`
In this example:

- **`x <- [1..10]`** is the qualifier, which generates values of `x` from the list of numbers from `1` to `10`.
- **`x^2`** is the expression that calculates the square of `x`.
- The result is a list of squares: `[1, 4, 9, 16, 25, 36, 49, 64, 81, 100]`.

## Multiple Qualifiers
`pairs = [(x,y) | x <- [1,2,3], y <- [4,5,6]]`
In this case:

- The expression generates pairs of `(x, y)` where `x` takes values from `[1, 2, 3]` and `y` takes values from `[4, 5, 6]`.
- The resulting list will be: `[(1,4), (1,5), (1,6), (2,4), (2,5), (2,6), (3,4), (3,5), (3,6)]`.

## Adding Filters
`evenSquares = [x^2 | x <- [1..10], even x]`

In this example:

- The filter `even x` ensures that only even numbers are squared.
- The result will be: `[4, 16, 36, 64, 100]`.

## Combining Filters & Multiple Qualifiers
`validPairs = [(x, y) | x <- [1..3], y <- [1..3], x /= y]`

Here:

- The expression generates pairs `(x, y)` where `x` and `y` are different.
- The resulting list will be: `[(1,2), (1,3), (2,1), (2,3), (3,1), (3,2)]`.

## Using `let` Bindings in Comprehensions
`complexComputation = [let y = x^2 in (x, y) | x <- [1..5]]`

In this example:

- The variable `y` is defined as `x^2` within the list comprehension.
- The resulting list will be: `[(1,1), (2,4), (3,9), (4,16), (5,25)]`.

## List Comprehensions VS Functions
List comprehensions can be thought of as a concise way to apply transformations and filters to lists. However, you can often achieve similar results using higher-order functions like `map`, `filter`, or `foldr`.

For example, the list comprehension
`doubledEvens = [2 * x | x <- [1..10], even x]`

Can also be expressed using `map` and `filter`
`doubledEvens = map (*2) (filter even [1..10])`




## Guards
# References

