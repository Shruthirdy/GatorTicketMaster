# Type Inference in Prolog

## Introduction

This project is about building a **type inference system** in **SWI-Prolog**, inspired by the way **OCaml** infers types. The system automatically deduces the types of function inputs, outputs, and variables in expressions, just like OCaml does during compilation.

For example, in OCaml, if you define:

```ocaml
let add x y = x + y
```

The compiler infers its type as `int -> int -> int`, meaning it takes two integers and returns an integer.

## Features Implemented

### 1. Built-in Functions
We've defined basic arithmetic and conversion functions using the `fType/2` predicate, such as:

```prolog
fType(iplus, [int, int, int]).
fType(fplus, [float, float, float]).
fType(fToInt, [float, int]).
fType(iToFloat, [int, float]).
fType(print, [_, unit]).
```

### 2. Type Inference for Different Statements
The system can infer types for various types of statements, including:

- **Global Variable Definitions**: `global_define(x, int, 3)` (similar to `let x = 3` in OCaml)
- **Global Function Definitions**: Functions with explicit type signatures.
- **Expressions**: Type checking for standalone expressions.
- **If-Else Expressions**: Ensuring the condition is `bool` and both branches have the same type.
- **Local Variables (`let-in` Expressions)**: Allows introducing variables within expressions.
- **For Loops**: Handles iteration over integer ranges.
- **Code Blocks**: Supports sequences of statements with `infer_code_block/2` and `infer_code/2`.

### 3. Advanced Features

- **Sum Types**: Represented via `sum/2`.
- **Tuple Types**: Represented via `tuple/2`.
- **Tuple Unpacking**: Handled with `let_in` and `tuple` constructs.
- **Pattern Matching**: Implemented using `match/2` and `pattern/2`.

### 4. Testing
A comprehensive test suite (`typeInf.plt`) is included, covering:

✅ Arithmetic and type conversions  
✅ Variable and function definitions  
✅ Control flow (if-else, loops, `let-in`)  
✅ Error handling (type mismatches, argument count errors, undefined functions)  
✅ Advanced features (sum types, tuples, pattern matching)  

## How to Run the Code

### 1. Start SWI-Prolog

```bash
swipl
```

### 2. Load the Prolog File

```prolog
?- [typeInf].
```

### 3. Run Tests
#### Run All Tests:
```prolog
?- consult("typeInf.pl"), consult("typeInf.plt").
?- run_tests(typeInf).
```

#### Run a Specific Test:
```prolog
?- consult("typeInf.plt"), run_tests(typeInf:<testname>).
```

## Project Structure

📂 **`type_inference.pl`** – Core implementation of the type inference system.  
📂 **`typeInf.plt`** – Unit tests to validate type inference behavior.  

This project brings Prolog’s logical reasoning capabilities into type inference, making it a great learning experience in both functional and logic programming. 🚀 Happy coding!
