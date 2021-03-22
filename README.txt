Student1: Jinhao Zhang  Email: jzh160@ur.rochester.edu
Student2: Mohammed Ibrahim Khan  Email: mkhan26@ur.rochester.edu

WRITEUP

The translator.ml is source code for Assignment 3: Translation of CSC 456.

The goal of this project was to write a program in Ocaml which takes in a program written in the ECG language and outputs a compilable C program. First, a set of mutually recursive methods walks a parse tree created by the provided parser. The parse tree and AST data structures are both grammar-specific, however, the parse tree can be easily adapted for a different grammar for use in the parser generator. After the AST is created, it is traversed by a set of mutually recursive translate functions, which translate the AST in a valid C program.


CODE EXECUTION

All the code and running-test is in the same file:
    "translator.ml"

How to run the files:
For translator.ml
1. Type "ocaml" in the command line to get into ocaml interpreter, then
2. #load "str.cma";;       ----- load the str library
3. #use "translator.ml";;  ----- interpret the code
4. main();;                ----- run the main function

Then it will create four C files from translation of testing cases.
Which are:
1. primes.c        - get the prime numbers
2. sum_ave.c       - get sum and average
3. undef.c         - undefined function
4. zero_div.c      - Divide by zero

Compile and run the C files to get an output.


FEATURES

1. Only support integer version for C files after we saw if we support real numbers, the  output is as follows:
2.000000
3.000000
5.000000
7.000000
11.000000
13.000000
17.000000
19.000000
23.000000
29.000000
Which is incompatible with the output on the website, so we changed it back to integer.
2. We have implemented divided by zero part for c code, so it'll raise an error when we try to divide some value by zero.
3. We did not succeed in implementing the warning when it has dynamic errors.
4. We check the error in the translate_s function.