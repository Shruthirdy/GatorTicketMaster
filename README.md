# Delphi Interpreter - Project 2

## Overview

This project is a continuation and extension of Project 1, where we initially implemented an interpreter for a subset of the Delphi (Object Pascal) language using ANTLR4 and Java.

In **Project 2**, we enhance the language support by introducing critical language features such as scoping, user-defined procedures and functions, loop constructs, and control flow mechanisms like `break` and `continue`. This interpreter builds upon the grammar and visitor-based AST evaluation logic developed in Project 1.

---

## 🔧 Features Implemented

### ✅ From Project 1

- Class and Object Declarations  
- Constructors and Destructors  
- Public and Private Fields (Encapsulation)  
- Method Declarations and Calls  
- Object Instantiation and Field Access  
- Input/Output (`ReadLn`, `WriteLn`) support  
- **Bonus (from Project 1):**
  - Inheritance Support  
  - Interface Declaration & Implementation

---

### 🆕 New in Project 2

#### 🔁 Looping Constructs
- `while-do` loops  
- `for-do` loops (both ascending and descending)

#### 🧵 Control Flow
- `break` and `continue` support within loops

#### 🧠 Procedures & Functions
- User-defined procedures  
- User-defined functions  
- Recursive procedures/functions  
- Local variables within procedures and functions

#### 📦 Scoping Rules
- **Static scoping** implemented:
  - New blocks (e.g., `begin...end`, `while`, `for`, etc.) create new scopes  
  - Procedure/function bodies create new scopes  
  - Variable resolution follows chain of visible scopes

#### 🧮 BONUS Features
- **Constant Propagation**:
  - Expressions using only constants are precomputed at compile-time  
  - Example: `a := 2 * (3 + 4)` is reduced to `a := 14` during AST construction

- **Formal Parameter Passing**:
  - Procedures and functions can declare and receive parameters  
  - Correct scoping of parameters is handled internally

---

## ▶️ How to Run

### ✅ Requirements

- Java 11 or higher  
- ANTLR 4.9.2  
- Bash terminal (for Unix/Mac) or Command Prompt (Windows)

### 🔧 Compilation

```bash
# From the root of the project directory
javac -cp .:lib/antlr-4.9.2-complete.jar src/*.java
```

> 🪟 **Note for Windows:** Replace `:` with `;` in the classpath.

### ▶️ Execution

```bash
# Example: Running a test file
java -cp .:lib/antlr-4.9.2-complete.jar:src src.DelphiInterpreter test/test10_ClassLifecycleTest.pas
```

---

## 🧪 Test Suite

A total of **27 test files** have been created to verify all features implemented in both Project 1 and Project 2.

Each test covers specific language functionality:

| Test File                          | Covers                                           |
|-----------------------------------|--------------------------------------------------|
| test1_BasicVariableAssignment.pas | Global variable assignment                       |
| test2_LocalVariableDeclaration.pas| Local vars inside blocks                         |
| test5_ReadLnWriteLn.pas           | Input/output handling                            |
| test10_ClassLifecycleTest.pas     | Object creation, constructor/destructor lifecycle|
| test13_SimpleClassDetails.pas     | Field access and printing within class methods   |
| test14_ConstructorsDestructors.pas| Constructor and destructor with multiple instances|
| test15_InheritanceTest.pas        | Method overriding and inherited calls            |
| test16_InterfaceImplementation.pas| Multiple interface implementation                |
| test20_WhileLoopDecreasingTest.pas| While loop and decrementing                      |
| test21_ForLoopTest.pas            | Ascending and descending for-loops              |
| test22_BreakContinueTest.pas      | `break` and `continue` within nested loops       |
| test23_ProceduresFunctionsTest.pas| Recursive procedures/functions                   |
| test24_RecursiveParameterTest.pas | Recursive functions and parameter passing        |
| test25_ScopeTest.pas              | Variable visibility in nested scopes             |
| test26_ConstantPropagation.pas    | **Bonus**: constant folding                      |
| test27_ParameterPassingTest.pas   | **Bonus**: formal parameter handling             |

✅ **All test outputs are verified and match expected behavior.**
