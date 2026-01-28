## Creating Variable and Naming them
- In java Field and Variable are often interchangeable
### Variables - Types
1. Instance Variables (or) Non-static Fields
	- Variables declared without  the `static` keyword. 
	- Therefore, they were unique for every object.
2. Class Variables (or) Static Fields
	- Variables declared with the `static` keyword.
	- Hence, the variables are shared by all the instances
	- Only one copy exists. i.e variables created often with `final` keyword
3. Local Variables 
	- Local Variables are unique in the block of their definition.
	- We can't access the variable outside of its definition.
	- No special keyword is used to assign them.
4. Parameters
	- Variables which where passed to the method are known as parameters.
	- Ex : args in `int main(String[] args)`

> [!note] 
> **Fields** generally refers to the instances and variables
> **Members** refers collectively to all methods, fields and .... of a class


### Naming Variables
- As same as other language I learnt, here in JAVA too they follow a set of rules in naming the variables in which most of the things were common.
- The only thing I find different is we're allowed to use `$` too in the variable name.
- It is good to not use special characters at the beginning of the word which was a good practice.
- `$` is often used by the compiler. Later We'll discuss about this symbol and its use case.
---
## Creating Primitive type Variable

### Primitive Types 
| Type                                    | Size [byte(s)] |
| --------------------------------------- | -------------- |
| `byte` (Used to save memory in array)   | 1              |
| `short`                                 | 2              |
| `int`(Default choice for whole numbers) | 4              |
| `long` (Ends with `L`)                  | 8              |
| `float` (Ends with `f)                  | 4              |
| `double` (Default choice for decimals)  | 8              |
| `boolean` (Flags)                       | 0.125          |
| `char` (Characters)                     | 2              |

> [!note] 
> Java uses 2bytes for storing characters because it stores the character in UTF-16 whereas other languages like C/C++ uses only 1 byte for storing a character.

> [!warning] 
> Never use `float` or `double` for currency.
> Always use `java.math.BigDecimal` to avoid rounding off errors.

### Default Value
- By default java assigns a value if you don't assign a value to it. (Most usually `0` or `false` or `null`)
- Exception :  Unassigned local variable might lead the compiler to raise an error.
### Literals
- A const value which is written directly in the code is known as Literals.
	1. Integer Literals
		- `int` : Written as it is (default)
		- `long` : Add L or l in the end. Mostly use L to avoid confusion with 1 (ONE)
	2. Floating Literals
		- double : written as it is (default)
		- float : Add f or F in the end. (Without f it most probably fail because it'll see it us double)
		- scientific notation : Use `e` or `E` - (e.g., `1.23e2` means $1.23 \times 10^2$)
	3. Character & Literal Literal
		- char : Uses single quotes (`'A'`)
		- String : Uses double quotes (`"Hello"`)
		- Escape Sequences : As same as other languages, followed by `\`
	4. The Underscore Feature (Readability)
		- Underscores `_` are used like commas in English
		- It enhances the readability - (1234_5678_90)
		- Mostly use in-between two numbers or else it might lead to an error.
		- Rules
			1. Start or end of a number (`_52` or `52_`).
			2. Adjacent to a decimal point (`3_.14` or `3._14`).
			3. Before an `F` or `L` suffix (`999_L`).
	
	Code Snippet of these concepts:
	```java
	public class PrimitiveDemo {
// Fields get default values (static included here for main method access)
    static int defaultInt;      // becomes 0
    static boolean defaultBool; // becomes false

    public static void main(String[] args) {
        // 1. Primitive declarations
        byte tinyNum = 100;
        long hugeNum = 9_000_000_000L; 
        // Underscore for readability + L suffix
        float price = 19.99f;          // f suffix is mandatory for floats
        char grade = 'A';              // Single quotes

        // 2. Local Variable Rule
        int localNum;
		// System.out.println(localNum); 
		// ERROR! Local variables must be initialized.

        // 3. Binary & Hex Literals
        int binaryTen = 0b1010; // Binary for 10
        int hexTen    = 0xA;    // Hex for 10

        System.out.println("Defaults: " + defaultInt + ", " + defaultBool);
        System.out.println("Huge Num: " + hugeNum);
    }
}
	```

---
## Creating Arrays

> An array is a container that holds a fixed number variables of same type

### Creating and Using it
- Three Main steps :
	1. Declaration
	2. Allocation
	3. Initialization
1. Declaration : 
	- It is the process of telling the compiler, I have an array of this type.
	```java
	int[] anArray; // Recommended standard syntax
	int anArray[];
	```
2. Allocation
	- We have to allocate memory for the array.
	```java
	anArray = new int[10]; // allocates memory for 10 integers
	```
3. Initialization
	- Here we assign values
	```java
	anArray[0] = 100;
	```

> [!note]
```java
int[] anArray = {100, 200, 300, 400};
// Here all (Declaration + Allocation + Initialization) is done in a statement
```

### Getting the size of the array
- adding the build-in property `.length` to an array will return the length of the array.

### Multi-Dimensional Arrays
- Syntax : `String[][] names;`
```java
String[][] names = {
	{"Mr., "Mrs.", "Ms."},
	{"Smith", "Jones"}
};
```

---
## Using `var` type identifier
- It enables the compiler to itself decide which datatype the given value would be.
- It is a reserved type name that tells the compiler : *"Look at the value on the right side of the equals sign, determine its type, and apply that type to this variable."*
- **Restrictions** : 
	1. **No Fields** - Cannot be used for fields / Instances variables. Because the Scope is broad. `var` is only for **local variables**
	2. **No Parameters** - Cannot be used for method arguments
	3. **Must Initialize** - Because the compiler have to determines its datatype based on the value.
	4. **No nulls** - We know that the datatype is determined using the assigned value. As `null`'s type can't be determined, We have to declare its type.
---
## Using Operators

Operators are tools that manipulate your data(variables).

### Operator Precedence
- Highest : `++`, `--`, and `()`
- Middle : `*`, `/`, `%`
- Low : `+`, `-`
- Lowest : `=`

Types are same as other programming languages except:

### Special Operators
1. `instanceof`
	 - Check if an object is a specific type (class or interace)
	 - `obj instanceof String` returns `true` if `obj` is a String


---
## Expressions, Statements, and Blocks

- An expression is any combination of variables, operators, and method calls that evaluates to a **single value**.

```java
float a = 0.0f;
for(int i = 0 ; i < 10 ; i++)
	a += 0.1f;
System.out.println(a);
```

- Floating-point numbers (`float` and `double`) are **not precise**. They are binary approximations of decimals.
- I thought the answer for the above snippet as `1.0` but the actual answer wasn't that it was somewhat `0.9999999999999`
- A statement is a complete unit of execution. It is roughly equivalent to a sentence in English and must be terminated with a **semicolon (`;`)**.
- A block is a group of zero or more statements enclosed in **braces `{ }`**. Java allows you to use a block anywhere a single statement is allowed.

In short, Expressions are phrases, Statements are sentences and Blocks are paragraphs.

---
## Control Flow

	 Complete yield and other topics.