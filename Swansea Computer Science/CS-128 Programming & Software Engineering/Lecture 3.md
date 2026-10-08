#CS128 

#### Notes

```java
int volumeInGallons = 5;
```
This is a fixed value.

```java
Scanner in = new.Scanner(System.in);
int volumeInGallons = in.nextIn();
```
*This uses 'magic words'*

*By importing Scanner, it's creating something that you can use to read data from the keyboard.*
This allows Java to read input from the keyboard.

```java
Scanner in = new.Scanner(System.in);
int volumeInGallons = in.nextIn();
					  ^^^^^^^^^^^^
```
*in.nextIn();* essentially tells Java to go away, and read data from whatever gets typed.

because the value has been specified as an integer, it's going to read whatever the user types in and try and read it as an integer (a whole number)

there's also next double, which is the same, except it'll try and read the input as a double integer (or a real number / decimal number)

now **volumeInGallons** is no longer a fixed-value.

### IMPORTANT TO REMEMBER!

Java is a strongly, statically typed language.

If you are defining variables as specific data types,
then you must follow this through.

You cannot define a variable as an integer, read input from a user as a string, and then try and set this variable's value to this input.

Java would throw an incompatible types error.

![[Screenshot 2026-10-08 at 19.32.26.png]]

This is called backtrace.
This is Java showing you what went wrong, and where.
The number at the end (9) is the line of code where it threw an error.
You can then read all the different exceptions that java's thrown to essentially trace your steps back in the code to see what's causing the issue.

**BIDMAS**
Java follows BIDMAS.
Arithmetic operations will be followed in the same order as BIDMAS.
- Brackets
- Indices
- Division
- Multiplication
- Addition
- Subtraction

![[Screenshot 2026-10-08 at 22.25.50.png]]

You **must** also specify the data type when doing arithmetic.
```java
double divideDouble = 5/4; // returns 1.25
int divideInt = 5/4; // returns 1
// this is because in the first statement, you're dividing with doubles
// in the second statement, you're diving integers

int divideInt = 5 % 4; // this is the remainder operator.

int counter;
counter++; // adds + 1
counter--; // takes away 1

// you can also do operations like...
counter *= 5;
counter += 5;
counter -= 5;

// other types of data...
String aString = "A string of words";
char aChar = "Another string of words.";
boolean trueOrFalse = false;
```