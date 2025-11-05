2024-10-17 21:55

Status:

Tags: [[Functional Programming]]

# FP Evaluation Strategies & Polymorphism
# Lazy Evaluation
Only compute what you need to compute
For example
```
def add(x, y):
    return x + y

result = add(5 * 2, 3 + 4)
```
- In python, the arguments `5*2` and `3+4` would be evaluated first regardless if the add function was actually used

## Drawbacks
- Difficult to combine with exception handling since the order of evaluation is unclear
- More difficult to predict
- Runtime memory pressure

## Useful functions for infinite lists
`take :: Int [a] -> [a]`
- selects the first n elements from a list
- Example: `take 10 (cycle [1,2,3,4,5]`
	- Gives `[1,2,3,4,5,1,2,3,4,5]`

`repeat :: a -> [a]`
- produces an infinite list of repeated values

`cycle :: [a] -> [a]`
- produces an infinite list from a finite by appending the list to itself infinitely

`iterate :: (a -> a) -> a -> [a]`
- produces an infinite list of function applications to an initial value

# Parametric Polymorphism
Parametric polymorphism is a core feature of Haskell that allows functions and data types to be written in a **generic** way, so they can operate on any type. 
The term "parametric" refers to the fact that the types are **parameters**, meaning the function or data type doesn't depend on any specific type; instead, it works uniformly with any type.

This is what allows Haskell functions to be **type-agnostic**, meaning they can be reused with many different types without requiring changes.

## How Parametric Polymorphism Works
```
identity :: a -> a
identity x = x
```
#### **Explanation:**

- **Type signature**: `identity :: a -> a` says that the function `identity` takes an argument of any type `a` and returns a value of the same type `a`. The type variable `a` is generic (parametric).
- **Body of the function**: `identity x = x` simply returns the argument it was given, regardless of what type it is.

The key feature here is that `a` can be **any type**. Haskell functions like `identity` can work with any type without needing to know what the specific type is, thanks to parametric polymorphism.

You could call `identity` with different types like:
```
identity 42         -- Result: 42
identity "hello"    -- Result: "hello"
identity True       -- Result: True
```

## Polymorphic Data Types
`data Maybe a = Nothing | Just a`

#### **Explanation:**

- **`Maybe a`**: This defines a type `Maybe` that works for **any type `a`**. The type `Maybe` can either be `Nothing` (representing the absence of a value) or `Just a` (representing the presence of a value of type `a`).
- **Type variable `a`**: The type `a` is a type parameter, meaning `Maybe` can wrap any type.



# Ad-Hoc Polymorphism

# Instances


# References

