# Type Inference in Prolog

## Introduction

The goal of this assignment is to implement a type inference algorithm in **SWI-Prolog** that mimics (in a simpler form) the one used by **OCaml**. The type inference system deduces the types of inputs and outputs of functions, as well as the types of variables used in expressions, much like OCaml infers types when compiling code.

For example, in OCaml, the function:

```ocaml
let add x y = x + y
```

has the type: `int -> int -> int` (i.e., it takes two integers and returns an integer).

The mechanism used to implement type inference is called **unification**. For more details, see:
- [Unification on Wikipedia](https://en.wikipedia.org/wiki/Unification_(computer_science))
- [Prolog Unification Slides](#)

## What Is Implemented

### 1. Basic Functions
Built-in functions (e.g., `iplus`, `fplus`, `fToInt`, `iToFloat`, `print`) are defined using the predicate `fType/2`.
For instance:

```prolog
fType(iplus, [int, int, int]).
fType(fplus, [float, float, float]).
fType(fToInt, [float, int]).
fType(iToFloat, [int, float]).
fType(print, [_, unit]).
```

### 2. Statement Types
The type inference system supports several kinds of statements:

#### Global Variable Definitions
Defined using the `global_define/3` construct (e.g., `global_define(x, int, 3)` corresponds to OCaml’s `let x = 3`).

#### Global Function Definitions
Functions are represented with their type signature in the global environment.

#### Expression Statements
Expressions are allowed as statements; their type is inferred accordingly.

#### If-Else Expressions
The type of an if-else expression is inferred by ensuring the condition is of type `bool` and both branches share the same type.

#### Local Variables ("let in" Expressions)
The `let_in/4` construct introduces local variables and infers the type of the resulting expression.

#### For Loops
The `for_loop/4` construct handles loop statements with an integer loop variable.

#### Code Blocks
Code blocks (sequences of statements) are handled by the predicates `infer_code_block/2` and `infer_code/2`.

### 3. Bonus Features

#### Sum Types
Supported via the `sum/2` type constructor.

#### Tuple Types
Supported via the `tuple/2` type constructor.

#### Tuple Unpacking
Handled via `let_in` and `tuple` constructs.

#### Match Statements
Implemented using the `match/2` and `pattern/2` constructs to allow pattern matching on expressions.

### 4. Testing
A comprehensive suite of unit tests (located in the `typeInf.plt` file) is provided using SWI-Prolog’s `plunit` framework. These tests cover more than 20 cases, including:

- Basic type inference for arithmetic and conversion operations.
- Global variable and function definitions.
- Control flow constructs (if-else, for loops, let-in).
- Error cases (type mismatches, incorrect argument counts, undefined functions).
- Bonus features (sum types, tuple types, match expressions).

## Running the Code

### A) Starting SWI-Prolog

**On Linux:**
```bash
swipl
```

**On Windows:**
```bash
swipl.exe
```

### B) Loading Your Code
Load the Prolog source file (e.g., `type_inference.pl`):

```prolog
?- [type_inference].
```

### C) Interacting with the System
You can ask questions like:

```prolog
?- infer_expr(iplus(X, Y), T).
```

This might output something like:

```ini
X = Y, Y = T, T = int.
```

### D) Tracing Execution
To trace execution for debugging, enter:

```prolog
?- trace.
?- infer_expr(iplus(X, Y), T).
```

Press "h" to see available options, and "a" to abort if needed.
Stop tracing with:

```prolog
?- notrace.
```

### E) Running Unit Tests
#### Run All Tests:
```prolog
?- consult("typeInf.plt"), run_tests().
```

#### Run a Specific Test:
```prolog
?- consult("typeInf.plt"), run_tests(typeInf:testname).
```

#### Run a Specific Test with Tracing:
```prolog
?- trace, consult("typeInf.plt"), run_tests(typeInf:testname).
```

#### Reload Tests After Changes:
```prolog
?- load_test_files([]).
```

## Project Structure

- **`type_inference.pl`**
  Contains the implementation of the type inference system. It includes predicates for inferring types of expressions, statements, code blocks, built-in functions, and global definitions.
- **`typeInf.plt`**
  Contains the unit tests for the project. This file tests various components of the type inference system to ensure correctness.

## Conclusion

This project implements a simplified OCaml-style type inference system in Prolog. It supports basic arithmetic, variable definitions, control structures, and bonus features like sum and tuple types along with pattern matching. The comprehensive test suite ensures that all components behave as expected.

**Happy coding!** 🎉
