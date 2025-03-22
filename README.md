# PLP_Julia Interpreter

This project extends a Pascal/Delphi interpreter in Julia to include object-oriented features (classes, constructors, destructors, inheritance, interfaces, etc.). Below is an overview of the repository structure, instructions on how to run the interpreter, and brief notes on included tests and known limitations.

---

## Project Structure

```
PLP_JULIA/
├── src/
│   ├── abstract_syntax_tree.jl
│   ├── delphi_interpreter.jl
│   ├── lexer.jl
│   └── parser.jl
└── test/
    ├── constructor_feature.pas
    ├── destructor_feature.pas
    ├── debug1_simple_var_assign.pas
    ├── debug2_inline_var_assign.pas
    ├── debug3_arith_eval.pas
    ├── debug4_if_else.pas
    ├── debug5_input_output.pas
    ├── debug6_obj_inst.pas
    ├── debug7_minimal_class.pas
    ├── debug8_interface_reg.pas
    ├── debug9_class_method_reg.pas
    ├── debug10_other_class.pas
    ├── debug11_simple_interface.pas
    ├── debug12_class_life_cycle.pas
    ├── debug13_param_bind.pas
    ├── debug14_primitive_types.pas
    ├── debug15_instance_display.pas
    ├── debug16_constructor_destructor.pas
    ├── debug17_inheritance_feature.pas
    ├── debug18_interface_feature.pas
    ├── debug19_access_modifiers.pas
    ├── debug20_par_child.pas
    ├── debug21_poly_inheritance.pas
    ├── debug22_encapsulation.pas
    └── polymorphism_feature.pas
```

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
- **constructor_feature.pas** / **destructor_feature.pas**  
  Demonstrate how constructors and destructors are handled.
- **debug1_simple_var_assign.pas**  
  Basic variable assignment and output.
- **debug2_inline_var_assign.pas**  
  Inline variable declaration and assignment.
- **debug3_arith_eval.pas**  
  Arithmetic expressions.
- **debug4_if_else.pas**  
  If-else conditionals.
- **debug5_input_output.pas**  
  ReadLn and WriteLn usage.
- **debug6_obj_inst.pas**  
  Object instantiation and dictionary representation.
- **debug7_minimal_class.pas**  
  Minimal class definition test.
- **debug8_interface_reg.pas**  
  Interface registration demonstration.
- **debug9_class_method_reg.pas**  
  Class method registration and usage.
- **debug10_other_class.pas**  
  Another class instantiation test.
- **debug11_simple_interface.pas**  
  Simple interface definition test.
- **debug12_class_life_cycle.pas**  
  Shows constructor and destructor calls.
- **debug13_param_bind.pas**  
  Method parameter binding.
- **debug14_primitive_types.pas**  
  Demonstrates integer, string, boolean usage.
- **debug15_instance_display.pas**  
  Displays instance data.
- **debug16_constructor_destructor.pas**  
  Another constructor/destructor example.
- **debug17_inheritance_feature.pas**  
  Simple inheritance example.
- **debug18_interface_feature.pas**  
  Interface feature demonstration (with warnings for interface inheritance).
- **debug19_access_modifiers.pas**  
  Shows public/private usage (not strictly enforced).
- **debug20_par_child.pas**  
  Another parent/child inheritance scenario.
- **debug21_poly_inheritance.pas**  
  Polymorphism with inheritance.
- **debug22_encapsulation.pas**  
  Encapsulation with private fields and public methods.
- **polymorphism_feature.pas**  
  Method overriding and polymorphism example.

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
The interpreter will parse and execute the specified `.pas` file, printing any output, including object dictionaries if applicable.

## Features

### Classes and Objects
- Define classes with fields and methods, instantiate objects, and call methods or access fields.

### Constructors and Destructors
- Demonstrate object lifecycle by running initialization and cleanup code.

### Inheritance and Polymorphism
- Support single inheritance and method overriding. Polymorphism is tested in some files by calling overridden methods on derived classes.

### Interfaces
- Classes can implement interfaces, though inheritance from interfaces shows a warning and is skipped.

### Expressions and Control Flow
- Handle variable declarations, assignments, arithmetic expressions, conditionals (if-else), loops (while), and more.

### Input/Output
- `ReadLn` for input and `WriteLn` for output.

## Known Limitations

### Interface Inheritance Warning
- A warning is printed for classes inheriting from an interface. Parent copying is not performed.

### Access Modifiers (Public/Private)
- The parser recognizes these keywords, but runtime enforcement is not fully implemented.

### Return Value Handling
- Functions must use `result := ...` to return values correctly.

## Conclusion
This repository contains a basic yet extendable Pascal/Delphi interpreter in Julia. It covers object-oriented features such as constructors, destructors, inheritance, and interfaces. The provided test files in the `test/` folder cover a wide range of scenarios, from simple variable assignments to complex inheritance and polymorphism. Feel free to explore or extend the code to support additional features and stricter enforcement of OOP principles.

