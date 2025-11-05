2024-10-12 10:36

Status:

Tags: [[Functional Programming]]

# FP Functions & List Lab

### **Functions Section**

1. **max2 :: Int -> Int -> Int**  
    **Problem**: Write a function that takes two integers and returns the maximum value.  
    **Solution**:
    
    `max2 :: Int -> Int -> Int 
    `max2 x y = if x > y then x else y`
    
    **Explanation**:  
    This function compares two integers `x` and `y`. It returns `x` if it is greater than `y`, otherwise it returns `y`. It's a simple conditional statement using `if-else`.
    
2. **max3 :: Int -> Int -> Int -> Int**  
    **Problem**: Write a function that returns the maximum of three numbers, using `max2`.  
    **Solution**:
    
    `max3 :: Int -> Int -> Int -> Int `
    `max3 x y z = max x $ max y z`
    or
    `max3 x y z = max x (max y z)`
    
    **Explanation**:  
    This function finds the maximum of three integers. It first compares `y` and `z` using `max`, and then compares the result with `x`. This solution relies on the built-in `max` function, which has the same logic as `max2`. The $ sign is a low precedence operator which makes everything to the right of it get evaluated first which avoids the use of brackets
    
3. **f :: (Int -> String) -> (String -> Bool) -> (Int -> Bool)**  
    **Problem**: Write a function that composes two functions, one converting an `Int` to `String` and another converting `String` to `Bool`.  
    **Solution**:
    
    
    `f :: (Int -> String) -> (String -> Bool) -> (Int -> Bool) 
    `f f1 f2 = \i -> f2 (f1 i)`
    
    **Explanation**:  
    The function `f` takes two functions `f1` and `f2` as arguments. `f1` converts an `Int` to `String`, and `f2` converts a `String` to `Bool`. The function `f` returns a function that takes an `Int` (denoted by `i`), applies `f1` to it, and then applies `f2` to the result.
    
4. **g :: (Int -> Bool) -> (Bool -> String) -> Int -> String**  
    **Problem**: Write a function that takes two functions, one converting `Int` to `Bool` and another converting `Bool` to `String`, and returns the composed result as `String`.  
    **Solution**:
    
    
    `g :: (Int -> Bool) -> (Bool -> String) -> Int -> String g f1 f2 x = f2 $ f1 x`
    
    **Explanation**:  
    The function `g` takes two functions, `f1` and `f2`. `f1` takes an `Int` and returns a `Bool`, and `f2` takes a `Bool` and returns a `String`. The function `g` applies `f1` to the integer input `x`, and then applies `f2` to the result of `f1`.
    
5. **twice :: (Int -> Int) -> Int -> Int**  
    **Problem**: Write a function that applies a given function twice to an integer.  
    **Solution**:
    
    
    `twice :: (Int -> Int) -> Int -> Int twice f x = f (f x)`
    
    **Explanation**:  
    The function `twice` takes a function `f` and an integer `x`. It applies `f` to `x`, then applies `f` again to the result of the first application. This results in `f(f(x))`.
    
6. **force :: Float -> Float -> Float -> Float**  
    **Problem**: Write a function that calculates gravitational force given two masses and a distance.  
    **Solution**:
    
    
    `force :: Float -> Float -> Float -> Float force m1 m2 d = (g * m1 * m2) / (d ^ 2)     where g = 6.67 * (10 ^^ (-11))`
    
    **Explanation**:  
    This function calculates the gravitational force using the formula F=G⋅m1⋅m2d2F = \frac{G \cdot m_1 \cdot m_2}{d^2}F=d2G⋅m1​⋅m2​​, where `G` is the gravitational constant 6.67×10−116.67 \times 10^{-11}6.67×10−11. The constant `G` is defined using `where`, and the function returns the force based on the provided masses `m1`, `m2`, and the distance `d`.
    

### **List Comprehensions Section**

1. **Divisible by 3**  
    **Problem**: Calculate numbers between 1 and 30 that are divisible by 3 using a list comprehension.  
    **Solution**:
    
    
    ``divByThree :: [Int] divByThree = [ x | x <- [1..30], x `mod` 3 == 0 ]``
    
    **Explanation**:  
    This function uses a list comprehension to generate a list of numbers `x` between 1 and 30 that are divisible by 3. It checks if `x` modulo 3 equals 0 using the condition `x` mod `3 == 0`.
    
2. **triangles :: Int -> [Int]**  
    **Problem**: Calculate the first `n` triangular numbers using a list comprehension.  
    **Solution**:
    
    ``triangles :: Int -> [Int] triangles n = [ (x * (x + 1)) `div` 2 | x <- [1..n] ]``
    
    **Explanation**:  
    This function calculates the first `n` triangular numbers. A triangular number is calculated by the formula x⋅(x+1)2\frac{x \cdot (x + 1)}{2}2x⋅(x+1)​. The list comprehension generates these numbers for each `x` from 1 to `n`.
    
3. **primes :: Int -> [Int]**  
    **Problem**: Write a function that returns a list of prime numbers up to `n`.  
    **Solution**:
    
    ``primes :: Int -> [Int] primes n = [ x | x <- [1..n], isPrime x ]     where         divisors x = [ y | y <- [2..(x - 1)], x `mod` y == 0 ]         isPrime x = length (divisors x) == 0``
    
    **Explanation**:  
    This function generates a list of prime numbers up to `n` using trial division. It checks if a number `x` has no divisors between 2 and `x-1`, which makes it prime. If the number of divisors is 0, the number is prime.
    
4. **flatten :: [[a]] -> [a]**  
    **Problem**: Flatten a nested list using a list comprehension.  
    **Solution**:
    
    `flatten :: [[a]] -> [a] flatten xs = [ y | x <- xs, y <- x ]`
    
    **Explanation**:  
    This function takes a nested list of lists `xs` and flattens it into a single list. It uses a list comprehension with two generators: the outer generator loops over each sublist `x` in `xs`, and the inner generator loops over each element `y` in `x`, collecting all elements into a single list.
    

### **Stretch Exercise**

**isbnCheck :: [Int] -> String**  
**Problem**: Write a function that calculates the check digit for an ISBN-10.  
**Solution**:

``isbnCheck :: [Int] -> String isbnCheck digits = if digit == 10 then "X" else (show digit)     where         coefficients = reverse [2..10]         pairs = zipWith (*) coefficients digits         summed = sum pairs         digit = 11 - (summed `mod` 11)``

**Explanation**:  
This function calculates the check digit for an ISBN-10 number. It multiplies each of the first 9 digits by a decreasing coefficient from 10 to 2, sums the results, and computes the check digit using the formula 11−(summedmod  11)11 - (summed \mod 11)11−(summedmod11). If the check digit is 10, it returns "X", otherwise, it returns the digit as a string.
# References

