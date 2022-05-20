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

> Section 1.1: Hello World
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

> Section 1.2: Original "Hello, World!" in K&R C
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


> Section 2.1: Commenting using the preprocessor
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

> Section 2.2: /* */ delimited comments
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
/* outer comment, means this is ignored => /* attempted inner comment */ <= ends the comment, not
this one => */
```

> Section 2.3: // delimited comments
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

> Section 2.4: Possible pitfall due to trigraphs
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


> Section 3.1: Interpreting Declarations
The following set of operators with identical precedence and associativity are reused in declarators, namely:
- the unary * "dereference" operator which denotes a pointer;
- the binary [] "array subscription" operator which denotes an array;
- the (1+n)-ary () "function call" operator which denotes a function;
- the () grouping parentheses which override the precedence and associativity of the rest of the listedoperators.

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




