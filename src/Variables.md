# Variables, Literals & Printing out in C++
There are several types of variables. 
Most of these variables exist across most coding languages
(Java, Python, C, C++, C# etc...) - If you learn them in one 
language they mostly translate to other languages.

---
### What are variables?
Variables are objects that contain values (numbers, text, etc) 
in programs. They let the programmer keep track of certain values -
sometimes unknown values to the programmer, such as user input.

to declare a variable, you'll generally follow this format:

    <data type> [name];
    
Data types tell the compiler what kind of variable you want to
declare. The name is how you reference the variable when you code.
You can name your variables whatever you would like. 

*you are encouraged to name variables according to what they are used
for. If you make a variable to hold the user's name, a good idea for
a name might be `name`. A more confusing name would be `x` or `var`
since you cannot tell what they are on first glance*
---
### Literals
Programming languages allow you to "hardcode" (set values/text from
the program) without the use of variables. These are known as `literals`

You can print literals and variables to the screen similarly. Also
when you `assign` values to variables using the `assignment operator (=)`,
you use literals to tell the computer what values they should store

We'll talk about printing data to the screen soon

---

# Data Types

## Lets start with numbers

There are several different data types for numbers in C++ (and other languages).

### The first of which is `int` or integers

Integers store whole numbers, both positive or negative. You declare them like:

```c++
int x; //declared an integer x;
```

 *Note I would strongly encourage initializing all variables when you declare them.
To initialize, simply assign it a starting value. See below:* 

```c++
int y = 0; //declared an integer y and initialized it to 0
```
By initializing, we ensure that we know exactly what x is when the program run
and we avoid any funky behavior such as the declared variable x having some value
other than what we expect it to have.

the last thing to mention about integers is that they can be signed (regular)
or `unsigned`. unsigned means that the compiler will throw you a warning if you
try to assign a negative value into the variable.
```c++
unsigned int z = 1; //declares and initializes an unsigned integer z to 1.
z = -1; 

```
if we attempt to print out z to the console, we will get a really large number:
4294967295. This is the largest number we can store in an unsigned integer before
it "overflows" - we will talk more about this later.


### Next lets talk about `float`s and `double`s
Floats and doubles contain decimal values (both positive and negative). You declare
them very similarly to how you declare integers. My general rule of always initializing
your variables when you declare them comes into play here:
```c++
float x = 2.5; //declare and initialize a float to the value 2.5;
double y = 2.5; //declare and initialize a double to the value 2.5;
```
the above two lines look identical. So why are there two? The answer comes down to
precision. A float is about half the size of a double, meaning that the float can't
store as large of numbers as a double can. To prove this to you, I will run the following:
```c++
#include <iostream>
#include <limits>
int main() {

    std::cout << "float max: "<< std::numeric_limits<float>::max() << std::endl;
    std::cout << "double max: " << std::numeric_limits<double>::max() << std::endl;

    std::cout << "Program Ending" << std::endl;
    return 0;
}
```
the output will look like:
```
float max: 3.40282e+38
double max: 1.79769e+308
Program Ending
```

In an academic environment, you might not care about or need that much precision
but if you were working at NASA, where they calculate with long decimal places
(think the first 20 decimals of ![pi](https://latex.codecogs.com/svg.image?\pi)!)

##

## [[back to main]](HomePage.md)
