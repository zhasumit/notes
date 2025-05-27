C++ is a high-level, general-purpose programming language created by Bjarne Stroustrup in 1979 as an extension of the C language. It was designed to add object-oriented programming (OOP) features to C, making it possible to create more structured and reusable code while retaining the power and efficiency of the original language.

**Key Features of C++:**

- Supports multiple programming paradigms: procedural, object-oriented, and generic programming.
    
- Offers direct control over system resources and memory management, which is essential for developing high-performance applications.
    
- Statically typed and compiled, ensuring type safety and efficient execution.
    
- Highly portable, making it suitable for cross-platform development.
    
- Includes a rich standard library and the Standard Template Library (STL), providing data structures, algorithms, and utilities.





## Hello world 
```cpp
#include <iostream>
using namespace std;
int main()
{
    cout << "Hello World";
    return 0;
}
```

`#include <iostream>`:  **preprocessor directive** that tells the compiler to include the Input/Output stream library. like `std::cin` and `std::cout`

`using namespace std`:  **use names in the `std` (standard) namespace** without prefixing them with `std::` every time. So instead of writing `std::cout`, you can just write `cout`.

`int main()`: main entry point of program in c++.
`{}`: contains the scope of the function starts just after the function declaration.

`cout<<"Hello world"`: `cout` is the **character output stream**, and `<<` is the **stream insertion operator** that sends the string to the output. prints **"Hello World"** to the console.

`return 0`: This ends the `main` function and **returns 0 to the operating system**, which usually signals that the program executed successfully.

`;` is used to end every line in the code.





## Basic sum
> Consider the preprocessor, namespace and the main function always include i will only write the relevant code for the logic to prevail put the wrapper around the logic yourself.

#### wrapper
```cpp
#include<iostream>
using namespace std;
int main(){

	// your logic code goes here

	return 0;
}
```





## Input and output stream

```cpp
string name;
cout << "May i know your name? :";

cin >> name;
cout << "Hi" << name << endl;
```

`cin >> variableName`
- Takes some input from the stream (terminal).
- quits taking input, on the basis of whitespaces.

`cout << "Hi" << varaibleName << endl;`
- `"Hi"` is a string contatinated with `variableName` which is also a string by definition
- `VaraibleName` can be used after following 2 steps 
	- declaration: declare what kind of value are you trying to use
		- example: `int`, `float`, `string`, `char`
		- for more range check, [[variables with different modifiers]]
	- initialization: to give value is to (initialize)
- `endl`: denotes end of line so the cursor in the terminal moves to the next line

- `<<` and `>>` can be appended as many times as possible 
- eg: `cin >> a >> b >> c` : takes 3 variables separated by some whitespace (space, tab, or newline).


#### `getline()`
- Reads an **entire line of input**, including spaces, until a newline (`\n`) is found.
- Useful for reading full sentences or names with spaces.
```cpp
	cout << "May I know your name : ";
    getline(cin, name);

    cout << "Welcome " << name << endl;
```


**difference between `cin` and `getline()`**
##### `cin`: Reads **input only until it encounters whitespace** (space, tab, or newline).
```cpp
string name;
cin >> name;
```
**Input:** `John Doe`  
**Stored in `name`:** `John`  
(Due to the space, `Doe` is not captured.)


##### `getline()`: Reads an **entire line** , including spaces, until a newline `\n`.
```cpp
string name;
getline(cin, name);
```
**Input:** `John Doe`  
**Stored in `name`:** `John Doe`  
(All words in the line are captured.)





### Math problems

#### Area of triangle 
```cpp
float b, h;
cout << "Enter the base and height of the traingle : ";
cin >> b >> h;
cout << "Area = " << (b * h) / 2;
```

- b, h : denote the base and height of the triangle
- `cout` shows something on the screen 
- `cin` takes the value from the stream (terminal) to the program
- `cout` then again concatenate string and the calculation done on spot


#### Sum of n natural numbers
```cpp
int n, sum = 0;
cout << "Enter the number of terms : ";
cin >> n;
cout << "Sum of " << n << "natural numbers = " << (n * (n + 1)) / 2 << endl;
```


#### Quadratic equations
(not necessary info): The roots (also called solutions or zeros) of a quadratic equation are the values of xx that satisfy the equation, i.e., make the equation equal to zero. 
So we find where does the parabola cut the grid and makes the x = 0
There is a formula for that 
$$
x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}
$$
$$
D = b^2 - 4ac
$$

| Discriminant (DD)       | Nature of Roots               |
| ----------------------- | ----------------------------- |
| D>0                     | Two real and distinct roots   |
| D=0                     | Two real and equal roots      |
| D<0                     | Two complex (conjugate) roots |
| D>0, perfect square     | Rational roots                |
| D>0, not perfect square | Irrational roots              |

```cpp
float x1, x2, a, b, c;
cout << "Enter values of a, b and c : ";
float D = sqrt((b * b) - (4 * a * c));
x1 = -b + D / (2 * a);
x2 = -b + D / (2 * a);
if (D < 0)
	cout << "Imaginary roots ";
if (D > 0)
	cout << "TWO distinct REAL roots " << x1 << ",  " << x2;
if (D == 0)
	cout << "ONE REAL root " << x1 << ",  " << x2;
```


- `a`, `b`, `c`: are the values that are in the formula 
- `x1`, `x2`: roots of the quadratic equation, where `x == 0`
- `D` as the formula above is calculated using the `sqrt((b*b) - (4ac))` 
- then roots are calculated and on the basis of `D` as in above table, roots are given


#### Area and perimeter of circle
```cpp
float r, area, circumference;

cout << "Enter the radius of the circle : ";
cin >> r;

area = 3.1415f * r * r;
circumference = 2 * 3.1415f * r;

cout << "Area of O : " << area << endl;
cout << "Circumference of O : " << circumference << endl;
```

- first the `r` radius, `area`, `circumference` is declared, `r` is taken from input stream.
- area and circumference is calculated as per laws of circle.
- The streamed out using `cout` and concatenated using `<<` operator.


#### simple Interest 
$$
SI = \frac{P \cdot R \cdot T}{100}
$$
```cpp
    float principal, rate, time, simpleInterest;

    cout << "Enter Principal (P): ";
    cin >> principal;

    cout << "Enter Rate of Interest (R): ";
    cin >> rate;

    cout << "Enter Time in years (T): ";
    cin >> time;

    simpleInterest = (principal * rate * time) / 100;

    cout << "Simple Interest = " << simpleInterest << endl;
```


#### Cylinder surface areas

```cpp
float r, h;
cout << "Enter th radius and height of the cylinder : ";
cin >> r >> h;

float Barea = 3.1415f * r * r;
cout << "Base area : " << Barea;

float LSA = 2 * 3.1415f * r * h;
cout << "Lateral surface area : " << LSA;

float TSA = (2 * 3.1415f * r) * (r + h);
cout << "Total surface area : " << TSA;

float volume = 3.1415f * r * r * h;
cout << "Volume : " << volume;
```


#### Net salary
Write a program to calculate the net salary should take following as input
1. Basic salary
2. Percentage of allowance
3. Percentage of deductions
Net salary = (Basic salary) + (Basic salary * percentage of allowance) - (Basic salary *percentage of deductions)

```cpp
float base, allow, deduce;

cout << "Enter the base salary : ";
cin >> base;

cout << "Enter the percentage allowance : ";
cin >> allow;

cout << "Enter the percentage deductions : ";
cin >> deduce;

float netSalary = base + (base * (allow / 100)) - (base * (deduce / 100));
cout << "Net salary : " << netSalary;
```





## Compound Assignment Operators
|Operator|Example|Equivalent To|Description|
|---|---|---|---|
|`+=`|x += y;|x = x + y;|Adds and assigns|
|`-=`|x -= y;|x = x - y;|Subtracts and assigns|
|`*=`|x *= y;|x = x * y;|Multiplies and assigns|
|`/=`|x /= y;|x = x / y;|Divides and assigns|
|`%=`|x %= y;|x = x % y;|Modulus and assigns|
|`&=`|x &= y;|x = x & y;|Bitwise AND and assigns|
|`|=`|x|= y;|
|`^=`|x ^= y;|x = x ^ y;|Bitwise XOR and assigns|
|`<<=`|x <<= y;|x = x << y;|Left shift and assigns|
|`>>=`|x >>= y;|x = x >> y;|Right shift and assigns|

focus on `+`, `-`, `*`, `/`, `%`, rest others are bit manipulation operators (to be discussed later)

```cpp
int a = 10;
int b = 3;
cout << "Initial values: a = " << a << ", b = " << b << endl;

a += b; // a = a + b
cout << "After a += b, a = " << a << endl;

a -= b; // a = a - b
cout << "After a -= b, a = " << a << endl;

a *= b; // a = a * b
cout << "After a *= b, a = " << a << endl;

a /= b; // a = a / b
cout << "After a /= b, a = " << a << endl;

a %= b; // a = a % b
cout << "After a %= b, a = " << a << endl;
```


#### Bitwise compound operator

```cpp
int a = 10;
int b = 3;
a &= b; // a = a & b
cout << "After a &= b, a = " << a << endl;

a |= b; // a = a | b
cout << "After a |= b, a = " << a << endl;

a ^= b; // a = a ^ b
cout << "After a ^= b, a = " << a << endl;

a <<= 1; // a = a << 1
cout << "After a <<= 1, a = " << a << endl;

a >>= 1; // a = a >> 1
cout << "After a >>= 1, a = " << a << endl;
```




## Increment Decrement operator `++`, `--`
```cpp
int i = 5;

cout << i << "\n";
cout << "++i : " << ++i << "\n"; // 6
cout << "i++ : " << i++ << "\n"; // 6
cout << "i-- : " << i-- << "\n"; // 7
cout << "--i : " << --i << "\n"; // 5
```

- `++`, `--` works in two ways, pre-processing, post-processing 
- `variable++`, `variable--`, `++variable`, `--variable`
- `i++`: i becomes `i+1` in next line, `i--`: i becomes `i-1` in next line
- `++i`; i becomes `i+1` on same spot, `--i`: i becomes `i-1` on same spot




## Overflow 

**Overflow in C++** happens when a value exceeds the range that can be stored in a given data type. check the [[variables with different modifiers]] file for the range of different variables.

eg: normal `char` is of range -128 to 127 so if pushed beyond boundaries then the values are overflowing or under-flowing and the norms break and the values go to the other extreme of the range it can contain.

```cpp
char x = 127, y = -128;

cout << "x : " << (int)x << "\n++x: " << (int)++x << endl;
cout << "y : " << (int)y << "\n--y: " << (int)--y << endl;
```

- `char x = 127;`
    - `x` is at the **maximum** value for a signed `char`.
        
- `++x` → `x = 128`, but **signed char only goes to 127**.
    - This causes **signed overflow** → undefined behavior.
    - On most systems, it **wraps around** to **-128**. (other extreme)
        
- `char y = -128;`
    - `y` is at the **minimum** value for a signed `char`.
        
- `--y` → `y = -129`, but the minimum for signed char is -128.
    - This causes **signed underflow** → undefined behavior.
    - On most systems, it **wraps around** to **127**. (other extreme)




## Bitwise operator

Bitwise operators in C++ are special operators that perform operations directly on the binary (bit-level) representations of integers. 
They allow you to manipulate individual bits within an integer variable, making them useful for low-level programming, optimizing performance, and tasks like graphics, cryptography, and device control

| Operator | Name                     | Function/Description                                                                                   | Example (a = 5, b = 9)                                     |
| -------- | ------------------------ | ------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------- |
| `&`      | Bitwise AND              | Sets each bit to 1 if both corresponding bits are 1.                                                   | a & b = 1                                                  |
| `        | `                        | Bitwise OR                                                                                             | Sets each bit to 1 if at least one corresponding bit is 1. |
| `^`      | Bitwise XOR              | Sets each bit to 1 if only one of the corresponding bits is 1 (not both).                              | a ^ b = 12                                                 |
| `~`      | Bitwise NOT (Complement) | Inverts all the bits (1 becomes 0, 0 becomes 1).                                                       | ~a = -6                                                    |
| `<<`     | Left Shift               | Shifts all bits to the left by a specified number of positions (adds zeros on the right).              | b << 1 = 18                                                |
| `>>`     | Right Shift              | Shifts all bits to the right by a specified number of positions (adds zeros or sign bits on the left). | b >> 1 = 4                                                 |
#### Core operations of the operator
- **Bitwise AND (`&`)**: Compares each bit of two numbers. The result bit is 1 only if both bits are 1.

- **Bitwise OR (`|`)**: Compares each bit and sets the result bit to 1 if either bit is 1.
    
- **Bitwise XOR (`^`)**: Sets the result bit to 1 if the bits are different.
    
- **Bitwise NOT (`~`)**: Flips all bits in the number (unary operator, works on a single operand).
    
- **Left Shift (`<<`)**: Moves all bits to the left, filling with zeros on the right; effectively multiplies by 2n2n.
    
- **Right Shift (`>>`)**: Moves all bits to the right, filling with zeros (for unsigned) or sign bits (for signed); effectively divides by 2^n




#### Converting number into the Negative number
Two's complement 
- Makes the number negative for representation in computer
- step 1: find 1's complement: flip all the bits
- step 2: add 1 to the ones complement

Eg: `y` is 7 and i want it represented in negative how?
`NOT (~)` Helps in flipping the bits of the digit

### Different bit wise operators
### `~y`
```
y -> 00000111
~y = 11111000

y -> 00000111
	+       1
~y = 00001000 = -8(decimal)
```

### `x & y`
```
BOTH bits should be one

11 -> 00001011
7  -> 00000111
x&y = 00000011
```

### `x | y`
```
ANY ONE bit should be one

11 -> 00001011
7  -> 00000111
x|y = 00001111
```

### `x ^ y`
```
Exclusive: 01 10 gives 1, 00 11 gives 0 (should be different)

11 -> 00001011
7  -> 00000111
x^y = 00001100
```

### `x << y`
```
shifts bit to left by y positions

11   = 00001011
x<<1 = 00010110 => 11*(2^1) = 22(Decimal)
```

### `x >> y`
```
shifts bit to right by y positions

11   = 00001011
x>>1 = 00000010 => 11/(2^2) = 2(Decimal)
```


```cpp
int x = 11, y = 7;

cout << "x = " << x << "\ty = " << y << endl;
cout << "~y     = " << ~y << endl;
cout << "x & y  = " << (x & y) << endl;
cout << "x | y  = " << (x | y) << endl;
cout << "x ^ y  = " << (x ^ y) << endl;
cout << "x << 1 = " << (x << 1) << endl;
cout << "x >> 2 = " << (x >> 2) << endl;
```

```
Output (as per explanations)

x = 11 y = 7
~y = -8
x & y = 3
x | y = 15
x ^ y = 12
x << 1 = 22
x >> 2 = 2
```



























































