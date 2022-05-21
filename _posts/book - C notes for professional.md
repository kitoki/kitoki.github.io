

stackoverflow : tag : [C language](https://stackoverflow.com/questions/tagged/c?tab=Votes) sort by Votes, [C language](https://stackoverflow.com/questions/tagged/c?tab=Frequent) sort by frequent, [malloc](https://stackoverflow.com/questions/tagged/malloc?tab=Votes), undefined [behavior](https://stackoverflow.com/questions/tagged/undefined-behavior), unspecified [behavior](https://stackoverflow.com/questions/tagged/unspecified-behavior), implementation [defined](https://stackoverflow.com/questions/tagged/implementation-defined-behavior) behavior, buffer-[overflow](https://stackoverflow.com/questions/tagged/buffer-overflow), [pointer](https://stackoverflow.com/questions/tagged/pointers), segmentation [fault](https://stackoverflow.com/questions/tagged/segmentation-fault), size[of](https://stackoverflow.com/questions/tagged/sizeof), standard [compliance](https://stackoverflow.com/questions/tagged/standards-compliance), [performance](https://stackoverflow.com/questions/tagged/performance), [optimization](https://stackoverflow.com/questions/tagged/optimization), bitwise [operator](https://stackoverflow.com/questions/tagged/bitwise-operators), header-[files](https://stackoverflow.com/questions/tagged/header-files), [operator](https://stackoverflow.com/questions/tagged/operators), fault [tolerance](https://stackoverflow.com/questions/tagged/fault-tolerance), [memory](https://stackoverflow.com/questions/tagged/memory), memory [leaks](https://stackoverflow.com/questions/tagged/memory-leaks), [caching](https://stackoverflow.com/questions/tagged/caching), cpu [cache](https://stackoverflow.com/questions/tagged/cpu-cache)

# **Contents**

* [chapter 1](https://github.com/kitoki/kitoki.github.io/blob/main/_posts/book%20-%20C%20notes%20for%20professional.md#chapter-1-getting-started-with-c-language-arrow_up): getting started with C language
* [chapter 2](https://github.com/kitoki/kitoki.github.io/blob/main/_posts/book%20-%20C%20notes%20for%20professional.md#chapter-2-comments-arrow_up): comments
* [chapter 3](https://github.com/kitoki/kitoki.github.io/blob/main/_posts/book%20-%20C%20notes%20for%20professional.md#chapter-3-data-types-arrow_up): data types
* [chapter 4](https://github.com/kitoki/kitoki.github.io/blob/main/_posts/book%20-%20C%20notes%20for%20professional.md#chapter-4-operators-arrow_up): operators
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

# **chapter 1: getting started with C language** [:arrow_up:](https://github.com/kitoki/kitoki.github.io/blob/main/_posts/book%20-%20C%20notes%20for%20professional.md#contents)

> [Section 1.1](https://github.com/kitoki/kitoki.github.io/blob/main/_posts/book%20-%20C%20notes%20for%20professional.md#section-11-hello-world-arrow_up): Hello World  
[Section 1.2](https://github.com/kitoki/kitoki.github.io/blob/main/_posts/book%20-%20C%20notes%20for%20professional.md#section-12-original-hello-world-in-kr-c-arrow_up): Original "Hello, World!" in K&R C

> #### Section 1.1: Hello World [:arrow_up:](https://github.com/kitoki/kitoki.github.io/blob/main/_posts/book%20-%20C%20notes%20for%20professional.md#chapter-1-getting-started-with-c-language-arrow_up)
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

> #### Section 1.2: Original "Hello, World!" in K&R C [:arrow_up:](https://github.com/kitoki/kitoki.github.io/blob/main/_posts/book%20-%20C%20notes%20for%20professional.md#chapter-1-getting-started-with-c-language-arrow_up)
```c
#Version = K&R
#include <stdio.h>
main()
{
 printf("hello, world\n");
}
```

>---

# **Chapter 2: Comments** [:arrow_up:](https://github.com/kitoki/kitoki.github.io/blob/main/_posts/book%20-%20C%20notes%20for%20professional.md#contents)

> [Section 2.1](https://github.com/kitoki/kitoki.github.io/blob/main/_posts/book%20-%20C%20notes%20for%20professional.md#section-21-commenting-using-the-preprocessor-arrow_up): Commenting using the preprocessor  
[Section 2.2](https://github.com/kitoki/kitoki.github.io/blob/main/_posts/book%20-%20C%20notes%20for%20professional.md#section-22---delimited-comments-arrow_up): /* */ delimited comments  
[Section 2.3](https://github.com/kitoki/kitoki.github.io/blob/main/_posts/book%20-%20C%20notes%20for%20professional.md#section-23--delimited-comments-arrow_up): // delimited comments  
[Section 2.4](https://github.com/kitoki/kitoki.github.io/blob/main/_posts/book%20-%20C%20notes%20for%20professional.md#section-24-possible-pitfall-due-to-trigraphs-arrow_up): Possible pitfall due to trigraphs  


> #### Section 2.1: Commenting using the preprocessor [:arrow_up:](https://github.com/kitoki/kitoki.github.io/blob/main/_posts/book%20-%20C%20notes%20for%20professional.md#chapter-2-comments-arrow_up)
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

> #### Section 2.2: /* */ delimited comments [:arrow_up:](https://github.com/kitoki/kitoki.github.io/blob/main/_posts/book%20-%20C%20notes%20for%20professional.md#chapter-2-comments-arrow_up)
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

> #### Section 2.3: // delimited comments [:arrow_up:](https://github.com/kitoki/kitoki.github.io/blob/main/_posts/book%20-%20C%20notes%20for%20professional.md#chapter-2-comments-arrow_up)
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

> #### Section 2.4: Possible pitfall due to trigraphs [:arrow_up:](https://github.com/kitoki/kitoki.github.io/blob/main/_posts/book%20-%20C%20notes%20for%20professional.md#chapter-2-comments-arrow_up)
```c
int x = 20; // Why did I do this??/

int foo = 20; // Start at 20 ??/
int bar = 0;

// The following will cause a compilation error (undeclared variable 'bar')
// because 'int bar = 0;' is part of the comment on the preceding line
bar += foo;
```

>---

# **Chapter 3: Data Types** [:arrow_up:](https://github.com/kitoki/kitoki.github.io/blob/main/_posts/book%20-%20C%20notes%20for%20professional.md#contents)

> [Section 3.1](https://github.com/kitoki/kitoki.github.io/blob/main/_posts/book%20-%20C%20notes%20for%20professional.md#section-31-interpreting-declarations-arrow_up): Interpreting Declarations  
[Section 3.2](https://github.com/kitoki/kitoki.github.io/blob/main/_posts/book%20-%20C%20notes%20for%20professional.md#section-32-fixed-width-integer-types-since-c99-arrow_up): Fixed Width Integer Types (since C99)  
[Section 3.3](https://github.com/kitoki/kitoki.github.io/blob/main/_posts/book%20-%20C%20notes%20for%20professional.md#section-33-integer-types-and-constants-arrow_up): Integer types and constants  
[Section 3.4](https://github.com/kitoki/kitoki.github.io/blob/main/_posts/book%20-%20C%20notes%20for%20professional.md#section-34-floating-point-constants-arrow_up): Floating Point Constants  
[Section 3.5](https://github.com/kitoki/kitoki.github.io/blob/main/_posts/book%20-%20C%20notes%20for%20professional.md#section-35-string-literals-arrow_up): String Literals  


> #### Section 3.1: Interpreting Declarations [:arrow_up:](https://github.com/kitoki/kitoki.github.io/blob/main/_posts/book%20-%20C%20notes%20for%20professional.md#chapter-3-data-types-arrow_up)
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

> #### Section 3.2: Fixed Width Integer Types (since C99) [:arrow_up:](https://github.com/kitoki/kitoki.github.io/blob/main/_posts/book%20-%20C%20notes%20for%20professional.md#chapter-3-data-types-arrow_up)

The header `<stdint.h>` provides several fixed-width integer type definitions. These types are optional and only provided if the platform has an integer type of the corresponding width, and if the corresponding signed type has a two's complement representation of negative values.

```c
/* commonly used types include */
uint32_t u32 = 32; /* exactly 32-bits wide */
uint8_t u8 = 255; /* exactly 8-bits wide */
int64_t i64 = -65 /* exactly 64 bit in two's complement representation */
```

> #### Section 3.3: Integer types and constants [:arrow_up:](https://github.com/kitoki/kitoki.github.io/blob/main/_posts/book%20-%20C%20notes%20for%20professional.md#chapter-3-data-types-arrow_up)
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

> #### Section 3.4: Floating Point Constants [:arrow_up:](https://github.com/kitoki/kitoki.github.io/blob/main/_posts/book%20-%20C%20notes%20for%20professional.md#chapter-3-data-types-arrow_up)
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
Floating point arithmetic is implementation defined. However, most modern platforms (arm, x86, x86_64, MIPS) use [IEEE 754](https://en.wikipedia.org/wiki/IEEE_754) floating point operations.  
C also has `three optional complex floating point` types that are derived from the above.

> #### Section 3.5: String Literals [:arrow_up:](https://github.com/kitoki/kitoki.github.io/blob/main/_posts/book%20-%20C%20notes%20for%20professional.md#chapter-3-data-types-arrow_up)

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

# **Chapter 4: Operators** [:arrow_up:](https://github.com/kitoki/kitoki.github.io/blob/main/_posts/book%20-%20C%20notes%20for%20professional.md#contents)

> [Section 4.1](https://github.com/kitoki/kitoki.github.io/blob/main/_posts/book%20-%20C%20notes%20for%20professional.md#section-41-relational-operators-arrow_up): Relational Operators  
[Section 4.2](https://github.com/kitoki/kitoki.github.io/blob/main/_posts/book%20-%20C%20notes%20for%20professional.md#section-42-conditional-operatorternary-operator-arrow_up): Conditional Operator/Ternary Operator  
[Section 4.3](https://github.com/kitoki/kitoki.github.io/blob/main/_posts/book%20-%20C%20notes%20for%20professional.md#section-43-bitwise-operators-arrow_up): Bitwise Operators  
[Section 4.4](https://github.com/kitoki/kitoki.github.io/blob/main/_posts/book%20-%20C%20notes%20for%20professional.md#section-44-short-circuit-behavior-of-logical-operators-arrow_up): Short circuit behavior of logical operators  
Section 4.5: Comma Operator
Section 4.6: Arithmetic Operators
Section 4.7: Access Operators
Section 4.8: sizeof Operator
Section 4.9: Cast Operator
Section 4.10: Function Call Operator
Section 4.11: Increment / Decrement
Section 4.12: Assignment Operators
Section 4.13: Logical Operators
Section 4.14: Pointer Arithmetic


C has many powerful operators. Many C operators are `binary` operators, which means they have `two operands`. For example, in `a / b`, `/` is a binary operator that accepts two operands (a, b). There are some unary operators which take one operand (for example: `~, ++`), and only one ternary operator `? :`.

> #### Section 4.1: Relational Operators [:arrow_up:](https://github.com/kitoki/kitoki.github.io/blob/main/_posts/book%20-%20C%20notes%20for%20professional.md#chapter-4-operators-arrow_up)

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

Not operator "`!`" : `!someVal`  
the opposite "`==`" : `someVal == 0`  

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

> #### Section 4.2: Conditional Operator/Ternary Operator [:arrow_up:](https://github.com/kitoki/kitoki.github.io/blob/main/_posts/book%20-%20C%20notes%20for%20professional.md#chapter-4-operators-arrow_up)

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

> #### Section 4.3: Bitwise Operators [:arrow_up:](https://github.com/kitoki/kitoki.github.io/blob/main/_posts/book%20-%20C%20notes%20for%20professional.md#chapter-4-operators-arrow_up)

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

> #### Section 4.4: Short circuit behavior of logical operators [:arrow_up:](https://github.com/kitoki/kitoki.github.io/blob/main/_posts/book%20-%20C%20notes%20for%20professional.md#chapter-4-operators-arrow_up)

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

> #### Section 4.5: Comma Operator [:arrow_up:](https://github.com/kitoki/kitoki.github.io/blob/main/_posts/book%20-%20C%20notes%20for%20professional.md#chapter-4-operators-arrow_up)

Evaluates its left operand, discards the resulting value, and then evaluates its rights operand and result yields the value of its `rightmost` operand.

```c
int x = 42, y = 42;
printf("%i\n", (x *= 2, y)); /* Outputs "42". */
```
The comma operator introduces a sequence point between its operands.  
Note that the comma used in functions calls that separate arguments `is NOT` the comma operator, rather it's called a separator which is different from the comma operator. Hence, it `doesn't have` the properties of the comma operator.

```c
printf("%i\n", (x *= 2, y)); /* Outputs "42". */
/*           ^        ^ this is a comma operator */
/*           this is a separator */
```
The comma operator is often used in the `initialization section` as well as in the `updating section` of a for loop. For example:

```c
for(k = 1; k < 10; printf("\%d\\n", k), k += 2); /*outputs the odd numbers below 9/*

/* outputs sum to first 9 natural numbers */
for(sumk = 1, k = 1; k < 10; k++, sumk += k)
 printf("\%5d\%5d\\n", k, sumk);
```

> #### Section 4.6: Arithmetic Operators [:arrow_up:](https://github.com/kitoki/kitoki.github.io/blob/main/_posts/book%20-%20C%20notes%20for%20professional.md#chapter-4-operators-arrow_up)

Addition Operator
```c
#include <stdio.h>

int main(void)
{
 int a = 5;
 int b = 7;
 int c = a + b; /* c now holds the value 12 */
 
 printf("%d + %d = %d",a,b,c); /* will output "5 + 7 = 12" */
 
 return 0;
}

```

Subtraction Operator

```c
#include <stdio.h>

int main(void)
{
 int a = 10;
 int b = 7;
 int c = a - b; /* c now holds the value 3 */
 printf("%d - %d = %d",a,b,c); /* will output "10 - 7 = 3" */

 return 0;
}

```

Multiplication Operator
```c
#include <stdio.h>

int main(void)
{
 int a = 5;
 int b = 7;
 int c = a * b; /* c now holds the value 35 */
 printf("%d * %d = %d",a,b,c); /* will output "5 * 7 = 35" */

 return 0;
}

```

Division Operator
```c
#include <stdio.h>

int main (void)
{
 int a = 19 / 2 ; /* a holds value 9 */
 int b = 18 / 2 ; /* b holds value 9 */
 int c = 255 / 2; /* c holds value 127 */
 int d = 44 / 4 ; /* d holds value 11 */
 
 double e = 19 / 2.0 ; /* e holds value 9.5 */
 double f = 18.0 / 2 ; /* f holds value 9.0 */
 double g = 255 / 2.0; /* g holds value 127.5 */
 double h = 45.0 / 4 ; /* h holds value 11.25 */
 
 printf("19 / 2 = %d\n", a); /* Will output "19 / 2 = 9" */
 printf("18 / 2 = %d\n", b); /* Will output "18 / 2 = 9" */
 printf("255 / 2 = %d\n", c); /* Will output "255 / 2 = 127" */
 printf("44 / 4 = %d\n", d); /* Will output "44 / 4 = 11" */
 printf("19 / 2.0 = %g\n", e); /* Will output "19 / 2.0 = 9.5" */
 printf("18.0 / 2 = %g\n", f); /* Will output "18.0 / 2 = 9" */
 printf("255 / 2.0 = %g\n", g); /* Will output "255 / 2.0 = 127.5" */
 printf("45.0 / 4 = %g\n", h); /* Will output "45.0 / 4 = 11.25" */
 
 return 0;
}
```
Modulo Operator
```c
#include <stdio.h>

int main (void) {
 int a = 25 % 2; /* a holds value 1 */
 int b = 24 % 2; /* b holds value 0 */
 int c = 155 % 5; /* c holds value 0 */
 int d = 49 % 25; /* d holds value 24 */
 
 printf("25 % 2 = %d\n", a); /* Will output "25 % 2 = 1" */
 printf("24 % 2 = %d\n", b); /* Will output "24 % 2 = 0" */
 printf("155 % 5 = %d\n", c); /* Will output "155 % 5 = 0" */
 printf("49 % 25 = %d\n", d); /* Will output "49 % 25 = 24" */
 
 return 0;
}

```

Increment / Decrement Operators

```c
#include <stdio.h>

int main(void)
{
 int a = 1;
 int b = 4;
 int c = 1;
 int d = 4;

 a++;
 printf("a = %d\n",a);                /* Will output "a = 2" */
 b--;
 printf("b = %d\n",b);                /* Will output "b = 3" */

 if (++c > 1) {                       /* c is incremented by 1 before being compared in the condition */
 printf("This will print\n");         /* This is printed */
 } else {
 printf("This will never print\n");   /* This is not printed */
 }

 if (d-- < 4) {                       /* d is decremented after being compared */
 printf("This will never print\n");   /* This is not printed */
 } else {
 printf("This will print\n");         /* This is printed */
 }
}
```

> #### Section 4.7: Access Operators [:arrow_up:](https://github.com/kitoki/kitoki.github.io/blob/main/_posts/book%20-%20C%20notes%20for%20professional.md#chapter-4-operators-arrow_up)

The member access operators (dot `.` and arrow `->`) are used to access a member of a struct.  

> Member of object
```c
struct MyStruct
{
 int x;
 int y;
};

struct MyStruct myObject;
myObject.x = 42;
myObject.y = 123;

printf(".x = %i, .y = %i\n", myObject.x, myObject.y);   /* Outputs ".x = 42, .y = 123". */

```

> Member of pointed-to object

Syntactic sugar for dereferencing followed by member access. Effectively, an expression of the form `x->y` is shorthand for `(*x).y` — but the arrow operator is much clearer, especially if the structure pointers are nested.

```c
struct MyStruct
{
 int x;
 int y;
};

struct MyStruct myObject;
struct MyStruct *p = &myObject;

p->x = 42;
p->y = 123;

printf(".x = %i, .y = %i\n", p->x, p->y);               /* Outputs ".x = 42, .y = 123". */
printf(".x = %i, .y = %i\n", myObject.x, myObject.y);   /* Also outputs ".x = 42, .y = 123". */
```

> Address-of

The unary & operator is the address of operator. It evaluates the given expression, where the resulting object must be an lvalue. Then, it evaluates into an object whose type is a pointer to the resulting object's type, and contains the address of the resulting object.

```c
int x = 3;
int *p = &x;

printf("%p = %p\n", （void *)&x, (void *)p); /* Outputs "A = A", for some implementation-defined A.
*/
```

> Dereference

The unary `*` operator dereferences a pointer. It evaluates into the lvalue resulting from dereferencing the pointer that results from evaluating the given expression.

```c
int x = 42;
int *p = &x;
printf("x = %d, *p = %d\n", x, *p); /* Outputs "x = 42, *p = 42". */

*p = 123;
printf("x = %d, *p = %d\n", x, *p); /* Outputs "x = 123, *p = 123". */
```

> Indexing

Indexing is syntactic sugar for pointer addition followed by dereferencing. Effectively, an expression of the form `a[i]` is equivalent to `*(a + i)` — but the explicit subscript notation is preferred.

```c
int arr[] = { 1, 2, 3, 4, 5 };
printf("arr[2] = %i\n", arr[2]);  /* Outputs "arr[2] = 3". */
```

> Interchangeability of indexing

Adding a pointer to an integer is a commutative operation (i.e. the order of the operands does not change the result) so pointer `+` integer `==` integer `+` pointer.  
A consequence of this is that arr[3] and 3[arr] are equivalent.  
`printf("3[arr] = %i\n", 3[arr]); /* Outputs "3[arr] = 4". */`  
Usage of an expression `3[arr]` instead of `arr[3]` is generally not recommended, as it affects code readability. It tends to be a popular in obfuscated programming `contests`.

> #### Section 4.8: sizeof Operator [:arrow_up:](https://github.com/kitoki/kitoki.github.io/blob/main/_posts/book%20-%20C%20notes%20for%20professional.md#chapter-4-operators-arrow_up)

> With a type as operand

```c
printf("%zu\n", sizeof(int)); /* Valid, outputs the size of an int object, which is platformdependent. */
printf("%zu\n", sizeof int); /* Invalid, types as arguments need to be surrounded by parentheses! */
```
> With an expression as operand

Evaluates into the size in bytes, of type `size_t`, of objects of the type of the given expression. The expression itself is not evaluated. Parentheses are `not required`; however, because the given expression must be `unary`, it's considered `best practice` to always use them.

```c
char ch = 'a';
printf("%zu\n", sizeof(ch)); /* Valid, will output the size of a char object, which is always 1 for
all platforms. */
printf("%zu\n", sizeof ch); /* Valid, will output the size of a char object, which is always 1 for
all platforms. */
```

> #### Section 4.9: Cast Operator [:arrow_up:](https://github.com/kitoki/kitoki.github.io/blob/main/_posts/book%20-%20C%20notes%20for%20professional.md#chapter-4-operators-arrow_up)

```c
int x = 3;
int y = 4;
printf("%f\n", (double)x / y); /* Outputs "0.750000". */
```

> #### Section 4.10: Function Call Operator [:arrow_up:](https://github.com/kitoki/kitoki.github.io/blob/main/_posts/book%20-%20C%20notes%20for%20professional.md#chapter-4-operators-arrow_up)

The first operand must be a `function pointer` (a `function designator` is also acceptable because it will be converted to a pointer to the function), identifying the function to call, and all other operands, if any, are collectively known as the `function call's arguments`. Evaluates into the return value resulting from calling the appropriate function with the respective arguments.

```c
int myFunction(int x, int y)
{
 return x * 2 + y;
}

int (*fn)(int, int) = &myFunction;
int x = 42;
int y = 123;

printf("(*fn)(%i, %i) = %i\n", x, y, (*fn)(x, y)); /* Outputs "fn(42, 123) = 207". */
printf("fn(%i, %i) = %i\n", x, y, fn(x, y)); /* Another form: you don't need to dereference explicitly */
```

> #### Section 4.11: Increment / Decrement [:arrow_up:](https://github.com/kitoki/kitoki.github.io/blob/main/_posts/book%20-%20C%20notes%20for%20professional.md#chapter-4-operators-arrow_up)

```c
int a = 1;
int b = 1;
int tmp = 0;

tmp = ++a;    /* increments a by one, and returns new value; a == 2, tmp == 2 */
tmp = a++;    /* increments a by one, but returns old value; a == 3, tmp == 2 */
tmp = --b;    /* decrements b by one, and returns new value; b == 0, tmp == 0 */
tmp = b--;    /* decrements b by one, but returns old value; b == -1, tmp == 0 */

```

Note that arithmetic operations do not introduce [sequence points](http://c-faq.com/expr/seqpoints.html), so certain expressions with `++` or `--` operators may introduce undefined behaviour.

> #### Section 4.12: Assignment Operators [:arrow_up:](https://github.com/kitoki/kitoki.github.io/blob/main/_posts/book%20-%20C%20notes%20for%20professional.md#chapter-4-operators-arrow_up)

```c
int x = 5;      /* Variable x holds the value 5. Returns 5. */
char y = 'c';   /* Variable y holds the value 99. Returns 99
                 * (as the character 'c' is represented in the ASCII table with 99).
                 */

float z = 1.5;          /* variable z holds the value 1.5. Returns 1.5. */
char const* s = "foo";  /* Variable s holds the address of the first character of the string 'foo'.*/
```
Several arithmetical operations have a compound assignment operator.
```c
a += b  /* equal to: a = a + b */
a -= b  /* equal to: a = a - b */
a *= b  /* equal to: a = a * b */
a /= b  /* equal to: a = a / b */
a %= b  /* equal to: a = a % b */
a &= b  /* equal to: a = a & b */
a |= b  /* equal to: a = a | b */
a ^= b  /* equal to: a = a ^ b */
a <<= b /* equal to: a = a << b */
a >>= b /* equal to: a = a >> b */
```
One important feature of these compound assignments is that the expression on the left hand side (a) is only `evaluated once`. E.g if p is a pointer `*p += 27;`, dereferences p only once, whereas the following does so twice. `*p = *p + 27`  

It should also be noted that the result of an assignment such as `a = b` is what is known as an `rvalue`. Thus, the assignment actually has a value which can then be assigned to another variable. This allows the chaining of assignments `to set multiple variables` in a `single statement`.  

This `rvalue` can be used in the controlling expressions of `if statements` (or `loops` or `switch statements`) that guard some code on the result of `another expression` or `function call`. For example:

```c
char *buffer;
if ((buffer = malloc(1024)) != NULL)
{
  /* do something with buffer */
  free(buffer);
}
else
{
  /* report allocation failure */
}
```
Because of this, care must be taken` to avoid a common typo` which can lead to mysterious bugs.

```c
int a = 2;
/* ... */
if (a = 1)
 /* Delete all files on my hard drive */

```
This will have disastrous results, as `a = 1` will always evaluate to `1` and thus the controlling expression of the `if statement` will always be `true` (read more about this `common pitfall` here). The author almost certainly meant to use the equality operator (`==`) as shown below:
```c
int a = 2;
/* ... */
if (a == 1)
 /* Delete all files on my hard drive */
```

> Operator Associativity
```c
int a, b = 1, c = 2;
a = b = c;
```

This assigns `c to b`, which returns `b`, which is than assigned to `a`. This happens because all assignment-operators have right associativity, that means the rightmost operation in the expression is evaluated `first`, and proceeds from `right to left`.

> #### Section 4.13: Logical Operators [:arrow_up:](https://github.com/kitoki/kitoki.github.io/blob/main/_posts/book%20-%20C%20notes%20for%20professional.md#chapter-4-operators-arrow_up)

> Logical AND
```c
0 && 0 /* Returns 0. */
0 && 1 /* Returns 0. */
2 && 0 /* Returns 0. */
2 && 3 /* Returns 1. */
```
> Logical OR
```c
0 || 0 /* Returns 0. */
0 || 1 /* Returns 1. */
2 || 0 /* Returns 1. */
2 || 3 /* Returns 1. */
```
> Logical NOT

Performs a logical negation. The logical `NOT` operator is of `type int`. The `NOT` operator checks if at least one bit is equal to 1, if so it returns `0`. Else it returns `1`;
```c
!1 /* Returns 0. */
!5 /* Returns 0. */
!0 /* Returns 1. */
```

> Short-Circuit Evaluation

There are some crucial properties common to both `&&` and `||`:
- the left-hand operand (LHS) is fully evaluated before the right-hand operand (RHS) is evaluated at all,
- there is a sequence point between the evaluation of the left-hand operand and the right-hand operand,
- and, most importantly, the right-hand operand is not evaluated at all if the result of the left-hand operand determines the overall result.

This means that:
- if the LHS evaluates to 'true' (non-zero), the RHS of `||` will not be evaluated (because the result of 'true OR anything' is 'true'),
- if the LHS evaluates to 'false' (zero), the RHS of `&&` will not be evaluated (because the result of 'false AND anything' is 'false').

This is important as it permits you to write code such as:
```c
const char *name_for_value(int value)
{
 static const char *names[] = { "zero", "one", "two", "three", };
 enum { NUM_NAMES = sizeof(names) / sizeof(names[0]) };
 return (value >= 0 && value < NUM_NAMES) ? names[value] : "infinity";
}
```
If a negative value is passed to the function, the `value >= 0` term evaluates to false and the `value < NUM_NAMES` term is not evaluated.

> #### Section 4.14: Pointer Arithmetic [:arrow_up:](https://github.com/kitoki/kitoki.github.io/blob/main/_posts/book%20-%20C%20notes%20for%20professional.md#chapter-4-operators-arrow_up)

> Pointer addition

Given a pointer and a scalar `type N`, evaluates into a pointer to the `Nth` element of the pointed-to type that directly succeeds the pointed-to object in memory.

```c
int arr[] = {1, 2, 3, 4, 5};
printf("*(arr + 3) = %i\n", *(arr + 3));    /* Outputs "4", arr's fourth element. */
```
It does not matter if the pointer is used as the `operand value` or the `scalar value`. This means that things such as `3 + arr` are valid. If `arr[k]` is the `k+1` member of an array, then `arr+k` is a pointer to `arr[k]`. In other words, `arr` or `arr+0` is a pointer to `arr[0]`, `arr+1` is a pointer to `arr[2]`, and so on. In general, `*(arr+k)` is same as `arr[k]`.  

Unlike the usual arithmetic, addition of `1` to a pointer to an `int` will add `4 bytes` to the current `address value`. As array names are constant pointers, `+` is the only operator we can use to access the members of an array via pointer notation using the `array name`. However, by defining a pointer to an array, we can get more flexibility to process the data in an array. For example, we can print the members of an array as follows:

```c
#include<stdio.h>
static const size_t N = 5

int main()
{
  size_t k = 0;
  int arr[] = {1, 2, 3, 4, 5};
 
  for(k = 0; k < N; k++)
  {
    printf("\n\t%d", *(arr + k));
  }
 
  return 0;
}
```
By defining a pointer to the array, the above program is equivalent to the following:

```c
#include<stdio.h>

static const size_t N = 5

int main()
{
 size_t k = 0;
 int arr[] = {1, 2, 3, 4, 5};
 int *ptr = arr; /* or int *ptr = &arr[0]; */

 for(k = 0; k < N; k++)
 {
   printf("\n\t%d", ptr[k]);
   /* or printf("\n\t%d", *(ptr + k)); */
   /* or printf("\n\t%d", *ptr++); */
 }
 
 return 0;
}

```
See that the members of the array `arr` are accessed using the operators `+` and `++`. The other operators that can be used with the pointer `ptr` are `-` and `--`.

> Pointer subtraction

Given two pointers to the same type, evaluates into an object of type `ptrdiff_t` that holds the scalar value that must be added to the second pointer in order to obtain the value of the first pointer.

```c
int arr[] = {1, 2, 3, 4, 5};
int *p = &arr[2];
int *q = &arr[3];
ptrdiff_t diff = q - p;

printf("q - p = %ti\n", diff); /* Outputs "1". */
printf("*(p + (q - p)) = %d\n", *(p + diff)); /* Outputs "4". */
```

> Section 4.15: _Alignof [:arrow_up:](https://github.com/kitoki/kitoki.github.io/blob/main/_posts/book%20-%20C%20notes%20for%20professional.md#chapter-4-operators-arrow_up)

Queries the alignment requirement for the specified type. The alignment requirement is a positive integral power of 2 representing the number of bytes between which two objects of the type may be allocated. In C, the alignment requirement is measured in `size_t`.  

The type name may not be an incomplete type nor a function type. If an array is used as the type, the type of the array element is used.  

This operator is often accessed through the convenience macro `alignof` from `<stdalign.h>`.

```c
int main(void)
{
 printf("Alignment of char = %zu\n", alignof(char));
 printf("Alignment of max_align_t = %zu\n", alignof(max_align_t));
 printf("alignof(float[10]) = %zu\n", alignof(float[10]));
 printf("alignof(struct{char c; int n;}) = %zu\n",
      alignof(struct {char c; int n;}));
}
```
Possible Output:
```c
Alignment of char = 1
Alignment of max_align_t = 16
alignof(float[10]) = 4
alignof(struct{char c; int n;}) = 4
```
http://en.cppreference.com/w/c/language/_Alignof











