# The Programming Languages Zoo

The Programming Languages Zoo, or *PL Zoo* for short, is a collection of implementations
of miniature programming languages which demonstrates various techniques used in
implementation of programming languages. It is a good starting point for those who would
like to implement their own programming language, or just learn how it is done.

See the [PL Zoo website](http://plzoo.andrej.com/) for further information, including
installation instructions.

# SDF Project 2: Modifying MiniML Language to Handle Exceptions
**By Akshat Banzal, Atul Boyal**

## Overview
This project involves extending the MiniML language to handle exceptions, with a specific focus on handling division by zero errors and general exception handling. We have implemented functionality for division, a `try {}` with `with {}` block for exception handling, and a custom `DivisionByZero` exception.

## Features
- **Division Operation**: The MiniML language now supports division, and handles division by zero using a custom exception.
- **Try-Catch Block**: Introduced a `try {}` block which can catch exceptions raised within the block, and handle them using the `with {}` block.
- **DivisionByZero Exception**: A specific exception that is raised when a division by zero occurs, allowing for proper handling of this error scenario.
- **Generic Exception Handling**: Added support for handling generic exceptions in a similar way, making the language more robust and fault-tolerant.

## Language Modifications
- **Lexer Changes**: Modified the lexer to recognize new syntax for `try {}` and `with {}`.
- **Parser Changes**: The parser was extended to include exception handling constructs (`try-catch` blocks) and ensure that exceptions can be raised and caught correctly.
- **Abstract Machine**: Updated the abstract machine to support exception handling. We added mechanisms to raise and handle exceptions during execution.
- **Type Checker**: The type checker was modified to ensure that the `try-catch` blocks and exceptions are correctly typed within the MiniML language.

  
## Example Usage
### Division with Exception Handling:
```ml
let divide = fun (x, y) -> try { x / y } with (DivisionByZero) { 0 }
