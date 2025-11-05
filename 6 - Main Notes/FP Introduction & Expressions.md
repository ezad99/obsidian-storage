2024-10-04 07:39

Status: #new

Tags:[[Functional Programming]]

# FP Introduction & Expressions

What is Functional Programming
- Functions are first class
- They are pure functions
- Immutable data
- No/Less side-effects
- Declarative
- Easier to Verify


Haskell
- A general-purpose
- Statically typed
- Purely Functional
	- Functional language with separation between pure and side-effecting code
- Has Type Inference
- Has Lazy Evaluation
	- Performed Computation on Demand
- No Side Effects

GHC
	Run
		`ghc -o hello hello.hs`
	-o hello means the output files with the prefix hello
	Run
		`:l function1.hs`
		This loads a file to be used

Expressions vs Statements
	Statement
		An instruction/computation step
		Doesn't return anything
	Expression
		A term in the language that eventually reduces to a value (e.g. a string, integer)
		Can be contained within a statement
	![[Pasted image 20241004080950.png]]
		Blue represents a statement, Orange represents an expression
	In a Functional Language **EVERYTHING IS AN EXPRESSION**

Types
- Each expression has a type





















# References

