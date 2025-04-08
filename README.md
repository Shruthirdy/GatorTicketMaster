# Delphi Interpreter - Project 2

## Overview

This project is a continuation and extension of Project 1, where we initially implemented an interpreter for a subset of the Delphi (Object Pascal) language using ANTLR4 and Java.

In **Project 2**, we enhance the language support by introducing critical language features such as loops, scoping, user-defined procedures and functions, loop constructs, and control flow mechanisms like `break` and `continue`. This interpreter builds upon the grammar and visitor-based AST evaluation logic developed in Project 1.

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

### New in Project 2

#### Looping Constructs
- `while-do` loops  
- `for-do` loops

#### Control Flow
- `break` and `continue` support 

#### Procedures & Functions
- User-defined procedures  
- User-defined functions  
- Recursive procedures/functions  
- Local variables within procedures and functions

#### Scoping Rules
- **Static scoping** implemented:
  - New blocks (e.g., `begin...end`, `while`, `for`, etc.) create new scopes  
  - Procedure/function bodies create new scopes  
  - Variable resolution follows chain of visible scopes

#### BONUS Features
- **Constant Propagation**:
  - Expressions using only constants are precomputed at compile-time  

- **Formal Parameter Passing**:
  - Procedures and functions can declare and receive parameters  
  - Correct scoping of parameters is handled internally

---

## ▶️ How to Run

### ✅ Requirements

- Java 11 or higher  
- ANTLR 4.9.2  
- Bash terminal (for Unix/Mac) or Command Prompt (Windows)

### 🔧 Compilation and Execution and Testing

```bash
# From the root of the project directory (from antlr_plp folder)
java -jar lib/antlr-4.9.2-complete.jar -visitor delphi.g4 -o src
javac -cp .:lib/antlr-4.9.2-complete.jar src/*.java
java -cp .:lib/antlr-4.9.2-complete.jar:src src/DelphiInterpreter.java test/<testfilename>.pas
```

---

## 🧪 Test Suite

A total of **27 test files** have been created to verify all features implemented in both Project 1 and Project 2.

Each test covers specific language functionality:

| Test File                          | Description                                                                 |
|-----------------------------------|-----------------------------------------------------------------------------|
| test1_BasicVariableAssignment.pas | Basic Variable Assignment Test: Tests a simple integer assignment and output. |
| test2_LocalVariableDeclaration.pas| Local Variable Declaration Test: Uses a block-scoped variable declaration and prints its value. |
| test3_ArithmeticExpressionEvaluation.pas| Arithmetic Expression Evaluation Test: Evaluates an arithmetic expression and outputs the result. |
| test4_ConditionalStatementTest.pas              | Conditional Statement (If-Else) Test: Verifies if–else behavior by comparing a variable’s value. |
| test5_InputOutputTest.pas           | Input/Output Test: Reads an integer from the user and prints it.            |
| test6_ClassInstantiationNumericReference.pas     | Class Instantiation Test (Numeric Reference): Creates an object using a class and prints its numeric reference. |
| test7_ClassInstantiationObjectReference.pas     | Class Instantiation Test (Object Reference Type): Declares the object variable with the class type. |
| test8_InterfaceDeclarationRegistration.pas   | Interface Declaration Registration Test: Registers an interface and prints a simple value. |
| test9_MinimalInterfaceDeclaration.pas    | Minimal Interface Declaration Test: Tests a basic interface declaration.    |
| test10_ClassLifecycleTest.pas     | Class Lifecycle Test: Constructor, public/private field access, and destructor. |
| test11_ParameterizedConstructorFieldUpdate.pas | Parameterized Constructor and Field Update Test: Uses a parameter and a method to update fields. |
| test12_PrimitiveDataTypesTest.pas     | Primitive Data Types Test: Declares and prints Integer, String, and Boolean variables. |
| test13_SimpleClass.pas     | Simple Class Test (Animal Class): Creates an Animal object and displays details. |
| test14_ConstructorsDestructors.pas| Vehicle Lifecycle and Display Test: Constructor, destructor, and method display. |
| test15_InheritanceOverriding.pas        | Inheritance Test: Method overriding in a base and derived class.            |
| test16_InterfaceImplementationTest.pas| Interface Implementation Test: Tests interface in two classes (Fan and Light). |
| test17_PublicFieldManipulation.pas| Public Field Manipulation Test: Sets and shows a public field.              |
| test18_PrivateFieldEncapsulation.pas| Encapsulation Test: Private field accessed via public methods.             |
| test19_PrivateAccessViolationTest.pas | Encapsulation and Access Violation Test: Attempts to access private fields externally. |
| test20_WhileLoop.pas| While Loop Test: Evaluates a while loop with a decrementing counter. |
| test21_ForLoopTest.pas            | For Loop (Ascending and Descending) Test: Runs loops in both directions.    |
| test22_LoopControlBreakContinue.pas      | Loop Control (Break/Continue) Test: Exercises break/continue in nested loops. |
| test23_ProceduresFunctionsTest.pas| Procedures, Functions, and Recursion Test: Includes recursion and parameter passing. |
| test24_RecursiveParameterTest.pas | Mixed Procedures and Recursive Calls Test: Combines recursive procedures and functions. |
| test25_ScopeTest.pas              | Variable Scoping and Nested Scope Test: Tests global/local scoping and shadowing. |
| test26_ConstantPropagation.pas    | Compile-Time Constant Expression Test: Tests constant folding.              |
| test27_ParameterPassingTest.pas   | Parameter Passing Test: Verifies parameter handling in procedures/functions. |

✅ **All test outputs are verified and match expected behavior.**
