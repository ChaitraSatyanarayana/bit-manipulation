CMPE 220 Spring 2018– System Software
Instructor: Dr. Hungwen Li
Lab 1
Introduction:
The purpose of this assignment is to become more familiar with bit-level representations of integers and floating point numbers.
Objectives:
Implement simple logical, two's complement, and floating point functions, but using a highly restricted subset of C. For example, they might be asked to compute the absolute value of a number using only bit-level operations and straight-line code.
The only file you will be modifying and turning in is bits.c. 1 The bits.c file contains a skeleton for each of the 15 programming puzzles. Your assignment is to complete any 5 function skeleton using only straightline code for the integer puzzles (i.e., no loops or conditionals) and a limited number of C arithmetic and logical operators. Specifically, you are only allowed to use the following eight operators: ! ˜ & ˆ | + << >> A few of the functions further restrict this list. Also, you are not allowed to use any constants longer than 8 bits. See the comments in bits.c for detailed rules and a discussion of the desired coding style.

Your Guide:
1.	Bit Manipulations
Table 1 describes a set of functions that manipulate and test sets of bits. The “Rating” field gives the difficulty rating (the number of points) for the puzzle, and the “Max ops” field gives the maximum number of operators you are allowed to use to implement each function. See the comments in bits.c for more details on the desired behavior of the functions. You may also refer to the test functions in tests.c. These are used as reference functions to express the correct behavior of your functions, although they don’t satisfy the coding rules for your functions.
 
2.	Two’s complement Arithmetic
Table 2 describes a set of functions that make use of the two’s complement representation of integers. Again, refer to the comments in bits.c and the reference versions in tests.c for more information.
 
3.	Floating-point Operations
For this part of the assignment, you will implement some common single-precision floating-point operations. In this section, you are allowed to use standard control structures (conditionals, loops), and you may use both int and unsigned data types, including arbitrary unsigned and integer constants. You may not use any unions, structs, or arrays. Most significantly, you may not use any floating point data types, operations, or constants. Instead, any floating-point operand will be passed to the function as having type unsigned, and any returned floating-point value will be of type unsigned. Your code should perform the bit manipulations that implement the specified floating point operations. Table 3 describes a set of functions that operate on the bit-level representations of floating-point numbers. Refer to the comments in bits.c and the reference versions in tests.c for more information.
Functions float_neg and float_twice must handle the full range of possible argument values, including not-a-number (NaN) and infinity. The IEEE standard does not specify precisely how to handle NaN’s, and the IA32 behavior is a bit obscure. We will follow a convention that for any function returning a NaN value, it will return the one with bit representation 0x7FC00000. The included program fshow helps you understand the structure of floating point numbers. To compile fshow, switch to the handout directory and type: unix> make You can use fshow to see what an arbitrary pattern represents as a floating-point number: unix> ./fshow 2080374784 Floating point value 2.658455992e+36 Bit Representation 0x7c000000, sign = 0, exponent = f8, fraction = 000000 Normalized. 1.0000000000 X 2ˆ(121)
You can also give fshow hexadecimal and floating point values, and it will decipher their bit structure.

 
