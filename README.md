<!---
{
  "id": "61354751-6887-4761-9ef0-ca25d237cf1c",
  "depends_on": [],
  "author": "Stephan Bökelmann",
  "first_used": "2025-05-19",
  "keywords": ["types","identifier","type-system"]
}
--->
# Identifiers, Types and Variables

## 1) Introduction
Programming means naming things and assigning meaning to data. In C, this begins with variables, their types, and the rules for naming them.

Once you've written your first `printf("Hello, World!\n")`, you've already encountered your first function and literal string. The next logical step is understanding **how we name data** and **what kinds of data** we can represent.

Identifiers are the names we give to things in code: variables, functions, constants. But not all names are allowed — they must follow specific rules: they must begin with a letter or underscore, may not clash with reserved keywords, and are case-sensitive.

Types in C describe what kind of data is stored and how many bytes are allocated. Some types are exact (`int`, `char`, `float`) while others vary depending on the system (`long`, `short`). Understanding types is critical not just for memory layout, but for how operations like `+`, `*`, or `==` behave.

A variable is a named storage location — a binding between an identifier and a value of a certain type. Declaring variables and using them correctly is a foundational concept.

> Variables in C are uninitialized by default — using them before assigning a value leads to **undefined behavior**.

An identifier is a name, which referrs to an object. Each identifier comes with a type,which is kind of a set of rules about the object that identifier references, defining how that data is stored, interpreted, which operations are legal and should be implemented by specific `asm` instructions by the compiler. 

You may use the same `+` operator in you code for `int` and `float`. But trying to write down the bit-patterns of two separate `int` and `float` values and the attempt to write down the truth-table will show to you, that even though in high-level-code we mean the same operation - adding them together - the circuits for them need to be implemented completely different. Thus making it neccessary to use different instructions for adding `float` and `int`.


## 2) Tasks
1. **Declare Variables**: Create variables of type `int`, `char`, `float`, and `double`. Assign values to them.
2. **Print Variables**: Use `printf` with the appropriate format specifiers (`%d`, `%c`, `%f`, `%lf`) to print their values. Just run the code for now and checkout the exercise [Format Specifiers](https://github.com/STEMgraph/fa0f19fa-c579-4183-9496-0eaa4251dfd4).
```C
printf("int: %d", intvar);
printf("char: %c", charvar);
printf("float: %f", floatvar);
printf("double: %lf", doublevar);
```
3. **Naming Practice**: Try creating a variable with an illegal name (e.g., `int 2cool;`) and observe the diagnostic message during compilation.
4. **Arithmetic**: Declare two `int` variables and compute their sum, product, and remainder. Print the results.
5. **Type Casting**: Divide an `int` by another `int` and cast the result to `float`. 
```C
float res1 = (float)(a / b);
float res2 = (float) a / b ;
printf("Result 1: %f", res1);
printf("Result 2: %f", res2);
```
6. **Storage Size**: Inspect the sizes of `int`, `char`, `float`, and `double` on your system by using  `sizeof()`?
```C
printf("Size of int: %d", sizeof(a));
```

## 3) Questions
1. What are valid and invalid identifier names in C, and in which stage of the compilation, are these names checked?

a-z, A-z "_" 0-9 <- after the first character:
not allowed: c names like int, count

2. What happens if you use a variable before assigning it a value?

ERROR Message
Won't compile

3. Why does dividing two integers give an integer result?

Operations between two values of the same type stay in that type, unless you explicitly cast.


## 4) Advice
Use `man printf` to explore format specifiers. Try writing small programs that experiment with assigning values and printing results. Don’t just read — test! Seeing how types behave in practice is much more instructive than memorizing rules.

