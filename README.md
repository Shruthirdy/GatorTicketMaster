# PLP_Julia Interpreter

## Team Members
- **Yaswanth Attaluri** - UFID: 10136560  
- **Shruthi Yaramada** - UFID: 26497222

## Introduction
This project extends a Pascal/Delphi interpreter in Julia to include object-oriented features (classes, constructors, destructors, inheritance, interfaces, etc.). Below is an overview of the repository structure, instructions on how to run the interpreter, and brief notes on included tests.

---

## Project Structure

    PLP_JULIA/
    ├── src/
    │   ├── abstract_syntax_tree.jl
    │   ├── delphi_interpreter.jl
    │   ├── lexer.jl
    │   └── parser.jl
    └── test/
        ├── classes_objects_feature.pas
        ├── constructor_feature.pas
        ├── debug1_simple_var_assign.pas
        ├── debug2_inline_var.pas
        ├── debug3_arith_eval.pas
        ├── debug4_if_else.pas
        ├── debug5_input_output.pas
        ├── debug6_obj_inst.pas
        ├── debug7_class_inst.pas
        ├── debug8_interf_decl.pas
        ├── debug9_class_method.pas
        ├── debug10_uses_Clause.pas
        ├── debug11_simple_interface.pas
        ├── debug12_class_life_cycle.pas
        ├── debug13_param_bind.pas
        ├── debug14_primitive_type.pas
        ├── debug15_simple_obj_instance.pas
        ├── debug16_construct_destruct.pas
        ├── debug17_inher_override.pas
        ├── debug18_interface.pas
        ├── debug19_access_modifier.pas
        ├── debug20_par_child.pas
        ├── destructor_feature.pas
        ├── encapsulation_feature.pas
        ├── inheritance_feature.pas
        ├── interface_feature.pas
        ├── polymorphism_feature.pas

### Files in `src/`

- **abstract_syntax_tree.jl**  
  Defines the AST (Abstract Syntax Tree) node types for the language constructs.

- **delphi_interpreter.jl**  
  The main interpreter module. Sets up global environments, loads the lexer and parser, and interprets the generated AST.

- **lexer.jl**  
  Responsible for tokenizing source code, handling whitespace, comments, operators, keywords, etc.

- **parser.jl**  
  Parses the token stream into an AST. Supports class/interface definitions, control structures, variable declarations, expressions, and more.

### Files in `test/`

Multiple `.pas` test files cover various features, including:
- **classes_objects_feature.pas** 
  - Demonstrates basic class creation with a constructor and a method.  
  - Instantiates a `Person` object and calls its `Greet` method to print details.  
  - Verifies object instantiation and method invocation.
- **constructor_feature.pas** / **destructor_feature.pas**  
  Tests the constructor functionality by printing messages during object creation.  
  Initializes a `Book` object with given parameters and displays its details.  
  Focuses solely on verifying constructor behavior and field initialization.
- **debug1_simple_var_assign.pas**  
  Basic variable assignment and output.
- **debug2_inline_var.pas**  
  Inline variable declaration and assignment.
- **debug3_arith_eval.pas**  
  Arithmetic expressions.
- **debug4_if_else.pas**  
  If-else conditionals.
- **debug5_input_output.pas**  
  ReadLn and WriteLn usage.
- **debug6_obj_inst.pas**  
  Object instantiation and dictionary representation.
- **debug7_class_inst.pas**  
  Minimal class definition test.
- **debug8_interf_decl.pas**  
  Interface registration demonstration.
- **debug9_class_method.pas**  
  Class method registration and usage.
- **debug10_uses_Clause.pas**  
  Another class instantiation test.
- **debug11_simple_interface.pas**  
  Simple interface definition test.
- **debug12_class_life_cycle.pas**  
  Shows constructor and destructor calls.
- **debug13_param_bind.pas**  
  Method parameter binding.
- **debug14_primitive_type.pas**  
  Demonstrates integer, string, boolean usage.
- **debug15_simple_obj_instance.pas**  
  Displays instance data.
- **debug16_construct_destruct.pas**  
  Another constructor/destructor example.
- **debug17_inher_override.pas**  
  Simple inheritance example.
- **debug18_interface.pas**  
  Interface feature demonstration (with warnings for interface inheritance).
- **debug19_access_modifier.pas**  
  Shows public/private usage (not strictly enforced).
- **debug20_par_child.pas**  
  Another parent/child inheritance scenario.
- **destructor_feature.pas**  
  Shows destructor functionality by printing messages when an object is freed.  
  Creates a `Computer` object, runs a simple method, and then calls `Free` to trigger cleanup.  
  Validates that destructors correctly access and display object field values.
- **encapsulation_feature.pas**  
  Demonstrates encapsulation by using private fields accessed only via public methods.  
  Implements a `BankAccount` class with deposit, withdrawal, and a getter method for balance.  
  Ensures that field access is controlled and manipulated through public interfaces.
- **inheritance_feature.pas**  
  Illustrates simple inheritance where `Circle` inherits from `Shape`.  
  The derived class extends functionality by adding a new field and overriding a method.  
  Verifies that method overriding and field inheritance work as expected.
- **interface_feature.pas**  
  Tests interface registration and implementation by defining `IPrintable`.  
  Implements the interface in a `Printer` class and calls its method via an interface reference.  
  Confirms that interfaces are recognized and their methods can be invoked properly.
- **polymorphism_feature.pas**  
  Demonstrates polymorphism by having a derived class (`Dog`) override a method from its base class (`Animal`).  
  Creates instances of both `Animal` and `Dog` and calls the `Speak` method.  
  Validates that the correct (overridden) method is executed based on the object's actual type.

---

## How to Run

1. **Install Julia**  
   Download and install [Julia](https://julialang.org/downloads/) if you haven't already.

2. **Navigate to `src/`**  
   In a terminal, change to the `src` directory of this project.

3. **Run the Interpreter**  
   Use the following command, replacing `<test_file>.pas` with the path to a test file in the `test/` directory:
   ```bash
   julia delphi_interpreter.jl ../test/<test_file>.pas
   ```

    For example:
    ```bash
    julia delphi_interpreter.jl ../test/debug1_simple_var_assign.pas
    ```
### Observe Output
The interpreter will parse and execute the specified .pas file, printing any output, including object dictionaries if applicable.

## Features

- **Classes and Objects:**  
  Define classes with fields and methods, instantiate objects, and call methods or access fields.

- **Constructors and Destructors:**  
  Demonstrate object lifecycle by running initialization and cleanup code.

- **Inheritance and Polymorphism:**  
  Support single inheritance and method overriding. Polymorphism is tested in some files by calling overridden methods on derived classes.

- **Encapsulation:**  
  Supports private fields and public methods to enforce data hiding and controlled access.

- **Interfaces:**  
  Classes can implement interfaces, though inheritance from interfaces shows a warning and is skipped.

- **Expressions and Control Flow:**  
  Handle variable declarations, assignments, arithmetic expressions, conditionals (if-else), loops (while), and more.

- **Input/Output:**  
  ReadLn for input and WriteLn for output.

