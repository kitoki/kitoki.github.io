**Contents**

* chapter 1: getting started with C language
* chapter 2: comments
* chapter 3: data types
* chapter 4: operators
* chapter 5: boolean
* chapter 6: strings
* chapter 7: literals for numbers, characters and strings
* chapter 8: compound literals
* chapter 9: bit-fields
* chapter 10: arrays
* chapter 11: linked lists
* chapter 12: enumerations
* chapter 13: structs
* chapter 14: standard math
* chapter 15: iteration statements/loops:for, while, do-while
* chapter 16: selection statements
* chapter 17: initialization
* chapter 18: declaration vs definition
* chapter 19: command-line arguments
* chapter 20: files and i/o streams
* chapter 21: formatted input/output
* chapter 22: pointer
* chapter 23: sequence points
* chapter 24: function pointers
* chapter 25: function paramaters
* chapter 26: pass 2D-arrays to functions
* chapter 27: error handling
* chapter 28: undefined behavior
* chapter 29: random number generation
* chapter 30: preprocessor and macros
* chapter 31: signal handling
* chapter 32: variable arguments
* chapter 33: assertion
* chapter 34: generic selection
* chapter 35: x-marcos
* chapter 36: aliasing and effetive type
* chapter 37: compilation
* chapter 38: inline assembly
* chapter 39: identifier scope
* chapter 40: implicit and explicit conversions
* chapter 41: type qualifiers
* chapter 42: typedef
* chapter 43: storage classes
* chapter 44: declarations
* chapter 45: structure padding and packing
* chapter 46: memory management
* chapter 47: implementation-defined behavior
* chapter 48: atomics
* chapter 49: jump statements
* chapter 50: create and include header files
* chapter 51: <ctype.h> - character classification & conversion
* chapter 52: side effects
* chapter 53: multi-character character sequence
* chapter 54: constraints
* chapter 55: inlining
* chapter 56: unions
* chapter 57: threads (native)
* chapter 58: multithreading
* chapter 59: interprocess communication (IPC)
* chapter 60: testing frameworks
* chapter 61: valgrind
* chapter 62: common C programming idioms and developer practices
* chapter 63: common pitfalls
* credits
* you may also like

>---

**chapter 1: getting started with C language**

> Section 1.1: Hello World  
Section 1.2: Original "Hello, World!" in K&R C

> #### Section 1.1: Hello World
```c
#include <stdio.h>
int main(void)
{
 puts("Hello, World");
 return 0;
}
```

> compiling using GCC compiler
`gcc hello.c -o hello`  
> compiling with warning options
`gcc -Wall -Wextra -Werror -o hello hello.c`  
> compiling using clang compiler
`clang -Wall -Wextra -Werror -o hello hello.c`  
> compiling using command line windows
`cl hello.c`  

> #### Section 1.2: Original "Hello, World!" in K&R C
```c
#Version = K&R
#include <stdio.h>
main()
{
 printf("hello, world\n");
}
```

>---

**Chapter 2: Comments**

> Section 2.1: Commenting using the preprocessor  
Section 2.2: /* */ delimited comments  
Section 2.3: // delimited comments  
Section 2.4: Possible pitfall due to trigraphs  


> #### Section 2.1: Commenting using the preprocessor
```c
#if 0 /* Starts the "comment", anything from here on is removed by preprocessor */
/* A large amount of code with multi-line comments */
int foo()
{
 /* lots of code */
 ...
 /* ... some comment describing the if statement ... */
 if (someTest) {
 /* some more comments */
 return 1;
 }
 return 0;
}
#endif /* 0 */
/* code from here on is "uncommented" (included in compiled executable) */
```

> #### Section 2.2: /* */ delimited comments
```c
/* this is a comment */

/* this is a
multi-line
comment */

/*
 * this is a
 * multi-line
 * comment
*/
```

```c
/* this comment is on its own line */
if (x && y) { /*this comment is at the end of a line */
 if ((complexCondition1) /* this comment is within a line of code */
 && (complexCondition2)) {
 /* this comment is within an if, on its own line */
 }
}
```

```c
/* outer comment, means this is ignored => /* attempted inner comment */ <= ends the comment, not this one => */
```

> #### Section 2.3: // delimited comments
```c
// this is a comment

// each of these lines are a single-line comment
// note how each must start with
// the double forward-slash

// this comment is on its own line
if (x && y) { // this comment is at the end of a line
 // this comment is within an if, on its own line
}
```

> #### Section 2.4: Possible pitfall due to trigraphs
```c
int x = 20; // Why did I do this??/

int foo = 20; // Start at 20 ??/
int bar = 0;

// The following will cause a compilation error (undeclared variable 'bar')
// because 'int bar = 0;' is part of the comment on the preceding line
bar += foo;
```

>---

**Chapter 3: Data Types**

> Section 3.1: Interpreting Declarations  
Section 3.2: Fixed Width Integer Types (since C99)  
Section 3.3: Integer types and constants  
Section 3.4: Floating Point Constants  
Section 3.5: String Literals  


> #### Section 3.1: Interpreting Declarations
The following set of operators with identical precedence and associativity are reused in declarators, namely:
- the `unary *` "dereference" operator which denotes a pointer;
- the `binary []` "array subscription" operator which denotes an array;
- the `(1+n)-ary ()` "function call" operator which denotes a function;
- the `() grouping parentheses` which override the precedence and associativity of the rest of the listed operators.

The above three operators have the following precedence and associativity:

| Operator | Relative Precedence | Associativity |
| :---     | :---                | :--- |
| [] (array subscription) | 1 | Left-to-right |
| () (function call) | 1 | Left-to-right |
| * (dereference) | 2 | Right-to-left |

| Expression | Interpretation |
| :---       | :---           |
| thing[X]   | an array of size X of... |
| thing(t1, t2, t3) | a function taking t1, t2, t3 and returning... |
|*thing | a pointer to... |

```c
char *names[20];

char (*place)[10];

int fn(long, short);

int *fn(void);

int (*fp)(void);

int arr[5][8];

int **ptr;

int fn(void), *ptr, (*fp)(int), arr[10][20], num;
```

The declared objects in the above example are:
- fn: a function taking `void` and returning `int`;
- ptr: a pointer to an `int`;
- fp: a pointer to a function taking `int` and returning `int`;
- arr: an array of size `10` of an array of size `20` of `int`;
- num: `int`.

```c
/*
 * Subscripting "arr" and dereferencing it yields a "char" result.
 * Particularly: *arr[5] is of type "char".
 */
char *arr[20];
/*
 * Calling "fn" yields an "int" result.
 * Particularly: fn('b') is of type "int".
 */
int fn(char);
/*
 * Dereferencing "fp" and then calling it yields an "int" result.
 * Particularly: (*fp)() is of type "int".
 */
int (*fp)(void);
/*
 * Subscripting "strings" twice and dereferencing it yields a "char" result.
 * Particularly: *strings[5][15] is of type "char"
 */
char *strings[10][20];
```

> #### Section 3.2: Fixed Width Integer Types (since C99)

The header `<stdint.h>` provides several fixed-width integer type definitions. These types are optional and only provided if the platform has an integer type of the corresponding width, and if the corresponding signed type has a two's complement representation of negative values.

```c
/* commonly used types include */
uint32_t u32 = 32; /* exactly 32-bits wide */
uint8_t u8 = 255; /* exactly 8-bits wide */
int64_t i64 = -65 /* exactly 64 bit in two's complement representation */
```

> #### Section 3.3: Integer types and constants
```c
signed char c = 127; /* required to be 1 byte, see remarks for further information. */
signed short int si = 32767; /* required to be at least 16 bits. */
signed int i = 32767; /* required to be at least 16 bits */
signed long int li = 2147483647; /* required to be at least 32 bits. */
signed long long int li = 2147483647; /* required to be at least 64 bits */

unsigned int i = 65535;
unsigned short = 2767;
unsigned char = 255;
```

For all types but `char` the signed version is assumed if the signed or unsigned part is omitted. The type `char` constitutes a third character type, different from `signed char` and `unsigned char` and the `signedness` (or not) depends on the platform.
Different types of integer constants (called literals in C jargon) can be written in different bases, and different width, based on their prefix or suffix.

```c
/* the following variables are initialized to the same value: */
int d = 42; /* decimal constant (base10) */
int o = 052; /* octal constant (base8) */
int x = 0xaf; /* hexadecimal constants (base16) */
int X = 0XAf; /* (letters 'a' through 'f' (case insensitive) represent 10 through 15) */
```

`Decimal constants` are always `signed`. Hexadecimal constants start with `0x` or `0X` and `octal` constants start just with
a `0`. The latter two are `signed` or `unsigned` depending on whether the value fits into the `signed type` or not.

```c
/* suffixes to describe width and signedness : */
long int i = 0x32; /* no suffix represent int, or long int */
unsigned int ui = 65535u; /* u or U represent unsigned int, or long int */
long int li = 65536l; /* l or L represent long int */
```

Without a `suffix` the constant has the first type that fits its value, that is a `decimal constant` that is larger than `INT_MAX` is of type long if possible, or `long long` otherwise.  

The header file `<limits.h>` describes the limits of integers as follows. Their implementation-defined values shall be `equal or greater` in magnitude (absolute value) to those shown below, with the same sign.

| Macro | Type | Value |
| :---  | :--- | :---  |
| CHAR_BIT | smallest object that is not a bit-field (byte) | 8 |
| SCHAR_MIN | signed char | -127 / -(27 - 1) |
| SCHAR_MAX | signed char | +127 / 27 - 1 |
| UCHAR_MAX | unsigned char | 255 / 28 - 1 |
| CHAR_MIN | char | see below |
| CHAR_MAX | char | see below |
| SHRT_MIN | short int | -32767 / -(215 - 1) |
| SHRT_MAX | short int | +32767 / 215 - 1 |
| USHRT_MAX | unsigned short int | 65535 / 216 - 1 |
| INT_MIN | int | -32767 / -(215 - 1) |
| INT_MAX | int | +32767 / 215 - 1 |
| UINT_MAX | unsigned int | 65535 / 216 - 1 |
| LONG_MIN | long int | -2147483647 / -(231 - 1) |
| LONG_MAX | long int | +2147483647 / 231 - 1 |
| ULONG_MAX | unsigned long int | 4294967295 / 232 - 1 |

| Macro | Type | Value |
| :---  | :--- | :---  |
| LLONG_MIN | long long int | -9223372036854775807 / -(263 - 1) |
| LLONG_MAX | long long int | +9223372036854775807 / 263 - 1 |
| ULLONG_MAX | unsigned long long int | 18446744073709551615 / 264 - 1 |

If the value of an object of type `char sign-extends` when used in an expression, the value of `CHAR_MIN` shall be the same as that of `SCHAR_MIN` and the value of `CHAR_MAX` shall be the same as that of `SCHAR_MAX`. If the value of an object of type char does `not sign-extend` when used in an expression, the value of `CHAR_MIN` shall be `0` and the value of `CHAR_MAX` shall be the same as that of `UCHAR_MAX`.  

The C99 standard added a new header, `<stdint.h>`, which contains definitions for fixed width integers. See the fixed width integer example for a more in-depth explanation

> #### Section 3.4: Floating Point Constants
```c
float f = 0.314f; /* suffix f or F denotes type float */
double d = 0.314; /* no suffix denotes double */
long double ld = 0.314l; /* suffix l or L denotes long double */
/* the different parts of a floating point definition are optional */
double x = 1.; /* valid, fractional part is optional */
double y = .1; /* valid, whole-number part is optional */
/* they can also defined in scientific notation */
double sd = 1.2e3; /* decimal fraction 1.2 is scaled by 10^3, that is 1200.0 */
```

The header `<float.h>` defines various limits for floating point operations.  
Floating point arithmetic is implementation defined. However, most modern platforms (arm, x86, x86_64, MIPS) use `IEEE 754` floating point operations.  
C also has `three optional complex floating point` types that are derived from the above.

> #### Section 3.5: String Literals

A string literal in C is a `sequence` of chars, terminated by a literal `zero`.

```c
char* str = "hello, world"; /* string literal */
/* string literals can be used to initialize arrays */
char a1[] = "abc"; /* a1 is char[4] holding {'a','b','c','\0'} */
char a2[4] = "abc"; /* same as a1 */
char a3[3] = "abc"; /* a1 is char[3] holding {'a','b','c'}, missing the '\0' */
```

String literals are `not modifiable` (and in fact may be placed in read-only memory such as .rodata). Attempting to alter their values results in `undefined behaviour`.

```c
char* s = "foobar";
s[0] = 'F'; /* undefined behaviour */
/* it's good practice to denote string literals as such, by using `const` */
char const* s1 = "foobar";
s1[0] = 'F'; /* compiler error! */
```

Multiple string literals are concatenated at `compile time`, which means you can write construct like these.

```c
/* only two narrow or two wide string literals may be concatenated */
char* s = "Hello, " "World";
Version ≥ C99
/* since C99, more than two can be concatenated */
/* concatenation is implementation defined */
char* s1 = "Hello" ", " "World";
/* common usages are concatenations of format strings */
char* fmt = "%" PRId16; /* PRId16 macro since C99 */
```

String literals, same as character constants, `support` different character sets.

```c
/* normal string literal, of type char[] */
char* s1 = "abc";
/* wide character string literal, of type wchar_t[] */
wchar_t* s2 = L"abc";
Version ≥ C11
/* UTF-8 string literal, of type char[] */
char* s3 = u8"abc";
/* 16-bit wide string literal, of type char16_t[] */
char16_t* s4 = u"abc";
/* 32-bit wide string literal, of type char32_t[] */
char32_t* s5 = U"abc";
```

>---

**Chapter 4: Operators**

> Section 4.1: Relational Operators  
Section 4.2: Conditional Operator/Ternary Operator  
Section 4.3: Bitwise Operators  
Section 4.4: Short circuit behavior of logical operators  


C has many powerful operators. Many C operators are `binary` operators, which means they have `two operands`. For example, in `a / b`, `/` is a binary operator that accepts two operands (a, b). There are some unary operators which take one operand (for example: `~, ++`), and only one ternary operator `? :`.

> #### Section 4.1: Relational Operators

Relational operators check if a specific relation between two operands `is true`. The result is evaluated to 1 (which means true) or 0 (which means false). This result is `often used` to affect control flow (via if, while, for), but can also be `stored in variables`.  

Equals "`==`"  
```c
1 == 0; /* evaluates to 0. */
1 == 1; /* evaluates to 1. */
int x = 5;
int y = 5;
int *xptr = &x, *yptr = &y;
xptr == yptr; /* evaluates to 0, the operands hold different location addresses. */
*xptr == *yptr; /* evaluates to 1, the operands point at locations that hold the same value. */
```

Attention: This operator should not be confused with the assignment operator (`=`)!  

Not equals "`!=`"  
```c
1 != 0; /* evaluates to 1. */
1 != 1; /* evaluates to 0. */
int x = 5;
int y = 5;
int *xptr = &x, *yptr = &y;
xptr != yptr; /* evaluates to 1, the operands hold different location addresses. */
*xptr != *yptr; /* evaluates to 0, the operands point at locations that hold the same value. */
```

Not operator "`!`" `!someVal`  
the opposite  
`someVal == 0`  

Greater than "`>`"
```c
5 > 4 /* evaluates to 1. */
4 > 5 /* evaluates to 0. */
4 > 4 /* evaluates to 0. */
```

Less than "`<`"
```c
5 < 4 /* evaluates to 0. */
4 < 5 /* evaluates to 1. */
4 < 4 /* evaluates to 0. */
```

Greater than or equal "`>=`"
```c
5 >= 4 /* evaluates to 1. */
4 >= 5 /* evaluates to 0. */
4 >= 4 /* evaluates to 1. */
```

Less than or equal "`<=`"
```c
5 <= 4 /* evaluates to 0. */
4 <= 5 /* evaluates to 1. */
4 <= 4 /* evaluates to 1. */
```

> #### Section 4.2: Conditional Operator/Ternary Operator

`a = b ? c : d;`  

is equivalent to:

```c
if (b)
 a = c;
else
 a = d;
```

This pseudo-code represents it : `condition ? value_if_true : value_if_false`. Each value can be the result of an evaluated expression.

```c
int x = 5;
int y = 42;
printf("%i, %i\n", 1 ? x : y, 0 ? x : y); /* Outputs "5, 42" */
```

The conditional operator `can be nested`. For example, the following code determines the bigger of three numbers:

```c
big= a > b ? (a > c ? a : c)
           : (b > c ? b : c);
```

The following example writes even integers to one file and odd integers to another file:

```c
#include<stdio.h>
int main()
{
 FILE *even, *odds;
 int n = 10;
 size_t k = 0;
 even = fopen("even.txt", "w");
 odds = fopen("odds.txt", "w");
 for(k = 1; k < n + 1; k++)
 {
 k%2==0 ? fprintf(even, "\t%5d\n", k)
 : fprintf(odds, "\t%5d\n", k);
 }
 fclose(even);
 fclose(odds);
 return 0;
}
```

The conditional operator associates from `right to left`. Consider the following:  

`exp1 ? exp2 : exp3 ? exp4 : exp5`  

As the association is from right to left, the above expression is evaluated as  

`exp1 ? exp2 : ( exp3 ? exp4 : exp5 )`

> #### Section 4.3: Bitwise Operators

Bitwise operators can be used to perform bit level operation on variables.  
Below is a list of all six bitwise operators supported in C:

| Symbol | Operator                       |
| :---   | :---                           |
| &      | bitwise AND                    |
| |      | bitwise inclusive OR           |
| ^      | bitwise exclusive OR (XOR)     |
| ~      | bitwise not (one's complement) |
| <<     | logical left shift             |
| >>     | logical right shift            |

Following program illustrates the use of all bitwise operators:

```c
#include <stdio.h>
int main(void)
{
 unsigned int a = 29; /* 29 = 0001 1101 */
 unsigned int b = 48; /* 48 = 0011 0000 */
 int c = 0;
 c = a & b; /* 32 = 0001 0000 */
 printf("%d & %d = %d\n", a, b, c );
 c = a | b; /* 61 = 0011 1101 */
 printf("%d | %d = %d\n", a, b, c );
 c = a ^ b; /* 45 = 0010 1101 */
 printf("%d ^ %d = %d\n", a, b, c );
 c = ~a; /* -30 = 1110 0010 */
 printf("~%d = %d\n", a, c );
 c = a << 2; /* 116 = 0111 0100 */
 printf("%d << 2 = %d\n", a, c );
 c = a >> 2; /* 7 = 0000 0111 */
 printf("%d >> 2 = %d\n", a, c );
 return 0;
}
```

Bitwise operations with `signed` types should be avoided because the sign bit of such a bit representation has a `particular` meaning. Particular restrictions apply to the `shift` operators:

- `Left shifting a 1 bit into the signed bit` is erroneous and leads to undefined behavior.
- `Right shifting a negative value (with sign bit 1)` is implementation defined and therefore not portable.
- If the value of the `right operand of a shift operator is negative` or is `greater than or equal` to the width of the promoted `left operand`, the behavior is undefined.

> Masking

Masking refers to the process of `extracting the desired bits` from (or transforming the desired bits in) a variable by using logical bitwise operations. The operand (a constant or variable) that is used to perform masking is `called a mask`.  

Masking is used in many different ways:

- To decide the `bit pattern` of an integer variable.
- To copy a `portion` of a given bit pattern to a new variable, while the remainder of the new variable is filled with `0s` (using bitwise `AND`)
- To copy a `portion` of a given bit pattern to a new variable, while the remainder of the new variable is filled with `1s` (using bitwise `OR`).
- To copy a `portion` of a given bit pattern to a new variable, while the remainder of the original bit pattern is `inverted` within the new variable (using bitwise exclusive `OR`).

The following function uses a mask to display the bit pattern of a variable:

```c
#include <limits.h>
void bit_pattern(int u)
{
 int i, x, word;
 unsigned mask = 1;
 word = CHAR_BIT * sizeof(int);
 mask = mask << (word - 1); /* shift 1 to the leftmost position */

 for(i = 1; i <= word; i++)
 {
   x = (u & mask) ? 1 : 0; /* identify the bit */
   printf("%d", x); /* print bit value */
   mask >>= 1; /* shift mask to the right by 1 bit */
 }
}
```

> #### Section 4.4: Short circuit behavior of logical operators

Short circuiting is a functionality that `skips evaluating parts` of a (`if/while/...`) condition when able. In case of a logical operation on `two operands`, the first operand is evaluated (to `true` or `false`) and if there is a verdict (i.e first operand is false when using `&&`, first operand is true when using `||`) the second operand is not evaluated.

```c
#include <stdio.h>
int main(void) {
 int a = 20;
 int b = -5;
 /* here 'b == -5' is not evaluated,
 since a 'a != 20' is false. */
 if (a != 20 && b == -5) {
 printf("I won't be printed!\n");
 }

 return 0;
}
```

```c
#include <stdio.h>
int print(int i) {
 printf("print function %d\n", i);
 return i;
}
int main(void) {
 int a = 20;
 /* here 'print(a)' is not called,
 since a 'a != 20' is false. */
 if (a != 20 && print(a)) {
 printf("I won't be printed!\n");
 }
 /* here 'print(a)' is called,
 since a 'a == 20' is true. */
 if (a == 20 && print(a)) {
 printf("I will be printed!\n");
 }
 return 0;
}
```

```terminal
$ ./a.out
print function 20
I will be printed!
```
Short circuiting is important, when you want `to avoid` evaluating terms that are (computationally) costly. Moreover, it can `heavily affect` the flow of your program like in this case: [Why does this program print "forked!" 4 times?](https://stackoverflow.com/questions/26716255/why-does-this-program-print-forked-4-times)


