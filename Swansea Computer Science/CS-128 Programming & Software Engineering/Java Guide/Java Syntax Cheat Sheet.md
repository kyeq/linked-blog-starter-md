---
tags: [CS128, java-guide]
---
#CS128 #java-guide

# Java Syntax Cheat Sheet
> [!tip] Every chapter's **SYNTAX QUICKGUIDE** from the CS-128 notes, in one place. For *why* things work, follow the link to the full chapter.

## Chapter 01 - Java Basics
*Full page: [[1.12 SYNTAX QUICKGUIDE]]*

All chapters that introduce any new Java syntax will have one of these sections at the end - they won't explain (much) how things work or what not to do (you'll have to read the notes for that) but they will give you a quick guide to how to write the code introduced in each chapter.

##### 1.12.1. Program Basics

A 'basic' program looks like this - REMEMBER it must be in a file with the same EXACT name as the program:

```java
public class MyProgram {
	public static void main(String[] args) {
		//Your code goes here - note the indenting
	}
}
```

Or if you use the other indenting style, it looks like this:

```java
public class MyProgram
{
	public static void main(String[] args)
        {
		//Your code goes here - note the indenting
	}
}
```

##### 1.12.2 Variables

Declare your variables like this:

```java
type name = value;
```

For example:

```java
String name = "Neal";
```

In this case, the type is String. If you don't know the value you can just write:

```java
String name;
```

but you will have to then assign it later:

```java
name = "Athina";
```

##### 1.12.3 Comments

Put comments in to make your code readable (not too many!). If a comment will fit on one line:

```java
//A one-line comment - on it's own line or a (short!) one on the end of a line of code
```

Longer comments should be like this:

```java
/*This is a longer comment, that will not fit on one line - don't use multiple // comments for these!
Usually, it's a good idea to put a blank line *in front* of a comment that applies to the
code that comes after it - whichever type of comment you use.*/
```

##### 1.12.4 Reading Input

To read input you need to create a Scanner like this ( *remember to import java.util.Scanne* r):

```java
Scanner in = new Scanner(System.in);
```

You can call it what you want - it does not have to be 'in'. To read input you can do things like:

```java
String input = in.nextLine();
```

You can read other kinds of data, not just strings.

## Chapter 02 - Numbers, Arithmetic and String Formatting
*Full page: [[2.12 SYNTAX QUICKGUIDE]]*

##### 2.12.1 Integer Variables and Operations

To declare an integer (whole number) variable in Java:

```java
int foundingOfRome = -753;
```

Note we try to give variables meaningful names - that represent what they mean and NOT what their value is! Like Strings, we can split declarations and assigning values (makes most sense when we don't know the value when we declare them):

```java
int tradFoundingOfRome;
tradFoundingOfRome = -753;
```

**Declare variables when you need them first (or as close as you can)**  - you don't need to put them all at the top of the program.

##### 2.12.2 Arithmetic

As with 'normal' arithmetic, it's brackets first; then division/multiplication; then additions/subtraction.

These are the operators that work on integers in Java:

| **Operator** | **Meaning** |
| --- | --- |
| + | addition |
| - | subtraction |
| * | multiplication |
| / | integer division (e.g. 10/3 == 3, not 3.333...) |
| % | integer remainder (e.g. 10%3 == 1 |
| +=, -=, *=, /=, %= | Shorthand operators -  **a += 5** is the same as  **a = a + 5**  and so on |
| ++, -- | Increment/decrement operators - a++ is the same as a = a + 1, and a-- is the same as a = a - 1 |

##### 2.12.3 Reading Integer from the Keyboard

A Scanner can read integers as well as Strings:

```java
Scanner in = new Scanner(System.in);
int numberOfPlayers = in.nextInt();
```

##### 2.12.4 Constants - Static Final Variables vs Variables Only Set Once

A  **final**  variable in Java is one that is only set once - a  **constant**  in Java is a variable that is  *both*   **static**   *and*   **final**:

```java
import java.util.Scanner;

public class Example {
	/*This is a constant - it is static, final AND outside
	of main */
	static final int SCORE_TO_WIN = 500;

	public static void main(String[] args) {
		Scanner in = new Scanner(System.in);
		System.in.print("Enter the number of players: ");

		/*This is a variable that is only set once - it is NOT
		a constant (it could be different each time the program
		is run)*/
		final int numPlayers = in.nextInt();
	}
}
```

The difference is:

- **Constants**  are the same every time the program runs - they are static, final and declared outside of main.
- **Final variables**  (not static) are variables that may be different between different runs of a program, but do not change - your program will still work if you don't make them final but it is definitely good practice to do so.

The way constants (static final) and 'normal' variables are named is explained in [Section 3.5.](https://canvas.swansea.ac.uk/courses/68227/pages/3-dot-5-identifier-names-very-important)

## Chapter 03 - Types and Names
*Full page: [[3.7 SYNTAX QUICKGUIDE]]*

##### 3.7.1 'Simple' Data Types

The following 'simple' data types are available in Java:

| **Name** | **Represents** | **Notes** |
| --- | --- | --- |
| **int** | integers (whole numbers - positive & negative) | Don't use  **Integer**! - also  **long**  and  **byte**  (but not really needed in this module |
| **double** | real numbers (decimals) | Don't use  **Double**! Don't use  **float**! |
| **boolean** | **true**  and  **false** | Don't use  **Boolean**! |
| **char** | Single characters | Don't use  **Char**! - constant char values represented by one character in  *single* quotes - e.g. 'z' |
| **String** | Sequences ('strings') of characters | Constant  **String**  values represented by sequences in  *double* quotes - e.g. "Kalamata" |

(Technically 'String' is  *not* a 'simple type' - but assume it is for now.

##### 3.7.2 Arithmetic

- You can mix real numbers (double) and integers (int) in arithmetic.
- You can store the results of integer arithmetic in doubles - e.g. double val = 5 * 4; is OK - but you cannot do the reverse - e.g. int val = 5.2 * 3.3; is NOT OK.
- You can 'force' results to be integers by  *casting -* e.g. int val = (int)(5.2 * 3.3); - now OK (but will round  *down* ).
- Unless you force it to be otherwise, division using integers will always be  *integer division -* e.g. 5/4 will be 1 - not 1.25. To force it to be non-integer, do one of: 5.0/4, or 5/4.0, or 5.0/4.0, or (double)5/4 etc.

##### 3.7.3 Comparison Operators

To compare numbers use these operators:

| Operator | Does | Notes |
| --- | --- | --- |
| == | Equality - true if equal, false if not - e.g. 5 == 4 is false | Easy to write = by mistake! |
| != | Inequality - true if not equal, false if equal |  |
| < | Less than |  |
| <= | Less than or equal | NOT =<! |
| > | Greater than |  |
| >= | Greater than or equal | NOT =>! |

You cannot 'chain' comparison operators - e.g. a < b < c is NOT legal (see below how to do this).

##### 3.7.4 Boolean Operators

To combine boolean (true/false) operations, use these operators:

| Operator | Does |  |
| --- | --- | --- |
| **true** | The constant true - always true | Note case! |
| **false** | The constant false - always false | Note case! |
| **!** | Not operator - turns true to false e.g. ! true is false |  |
| **&&** | And operator - true if both true | Don't use one  **&**! In  **a && b**  if  **a**  is  **false**, does not bother checking  **b** |
| **\|\|** | Or operator - true if either true | Don't use one  **\|**! In  **a \|\| b**  if  **a**  is  **true, does not bother checking b** |
| **^** | Exclusive Or - true if ONE is true | So  **a ^ b**  is true if ONE of a or b is true but NOT if they are BOTH true. To switch a boolean from true to false and vice versa, use  **boolVal = !boolVal;**  - NOT  **boolVal ^= true;**  (more obvious to reading programmer). |

##### 3.7.5 Naming Variables

Use the following 'patterns' to name your variables:

| **'Kind' of Variable** | **Naming Pattern** | **Notes** |
| --- | --- | --- |
| 'Ordinary' variable | start lower case, capitalise first letter of any internal words, no _! | For example myVariableName, or itemCost, or item - not MyVariableName, or My_Variable_Name etc. |
| Program name | as above BUT start with capital letter | For example, MyProgramName |
| Constants | All capitals with _ between words | For example, MY_CONSTANT_VALUE - do not confuse with 'ordinary' final variables - this is just for constants |

Variable names should be  *readable* ,  *meaningful* , and should represent what the variable is  *for*  -  *not*  what its  *value*  is (so e.g. int one = 1; is VERY VERY BAD...)

## Chapter 04 - Conditionals
*Full page: [[4.11 SYNTAX QUICKGUIDE]]*

##### 4.11.1 Simple One-Way If

Write like this:

```java
if (condition) {
    code
}
```

Or like this:

```java
if (condition)
{
    code
}
```

NEVER leave out the brackets!

##### 4.11.2 Simple If-Else

Write like this:

```java
if (condition) {
    code
} else  {
    other code
}
```

Or like this:

```java
if (condition)
{
    code
}
else
{
    other code
}
```

##### 4.11.3 Multiway If-Else

Write like this:

```java
if (condition) {
    code
} else if (other condition) {
    other code
}
...
} else {
    code if none of the conditions are true
}
```

Or like this:

```java
if (condition)
{
    code
}
 else if (other condition)
{
    other code
}
...
}
else
{
    code if none of the conditions are true
}
```

##### 4.10.4 Options with If statements

To build up complex decisions using if statements you can do one or more of these, on their own or together.

- Create complex expressions with boolean variables and operators.
- Use nested (one inside another) if statements.
- Use boolean variables to represent complex conditions.

##### 4.11.5 Switch Statements

Switch statements look like this:

```java
switch (daysInMonth) {
      case 28:
         System.out.println("February");
         break;
      case 30:
         System.out.println("April, June, September or November");
         break;
      case 31:
         System.out.println("One of the others");
         break;
      default:
         System.out.println("Error");
}
```

Or like this:

```java
switch (daysInMonth){
      case 28:
         System.out.println("February");
         break;
      case 30:
         System.out.println("April, June, September or November");
         break;
      case 31:
         System.out.println("One of the others");
         break;
      default:
         System.out.println("Error");
}
```

You can put more than one case in front of a fragment of code e.g.:

```java
case "lemon";
case "orange":
case "lime":
    System.out.println("Common citrus fruits");
    break;
```

##### 4.10.6 Switch Expressions

Switch expressions look like this (don't leave out the  **break**  statements or the  **default**!):

```java
String roadColorOnMap = switch(road) {
    case "Motorway" -> "blue";
    case "A road", "B road" -> "green";
    default -> "red";
};
```

Or like this:

##### 4.11.10 Ternary Operators

Use ternary operators like this:

```java
int value = condition ? oneValue : otherValue:
```

## Chapter 05 - Scope
*Full page: [[5.3 SYNTAX QUICKGUIDE]]*

##### 5.3.1 Visibility of Variables

In this code:

```java
int a = 5;
if (condition) {
	int b = 10;
}
//Can, say, print a here but not b
```

the variable  **b**  is only visible inside the brackets in the if statement - but the variable  **a**  is visible both inside and outside. The  *scope* of a variable is the brackets that surround its declaration.

##### 5.3.2 More than one Variable with the Same Name

This is not allowed - one variable declared inside brackets when there is another with the same name outside the brackets.

```java
int a = 5;
if (condition) {
	int a = 10;
}
```

But this  *is* allowed - there are two variables both called  **b**  in this example:

```java
if (condition) {
	int a = 10;
} else {
	int a = 5;
}
```

## Chapter 06 - Loops
*Full page: [[6.11 SYNTAX QUICKGUIDE]]*

##### 6.11.1 For Loops

Use when you need to iterate a  *known* (when the loop starts) number of times.

Write for loops like this:

```java
for(initialisation; condition; loop step) {
	code
}
```

or like this:

```java
for(initialisation; condition; loop step)
{
	code
}
```

It is acceptable to use single letter variables i, j, k etc. as for loop counters only (but if you want to use e.g. count instead that's fine):

```java
for(int i = 0; i < value; i++) {
	code
}
```

##### 6.11.2 While Loops

Use when you need to iterate an  *unknown* (when the loop starts) number of times.

Write while loops like this:

```java
while(condition) {
	code
}
```

or like this:

```java
while(condition)
{
	code
}
```

##### 6.11.3 Do Loops

Use when you need to iterate an  *unknown*  (when the loop starts) number of times -  *but you know it will be at least once.* (Often useful in reading user input for example.)

Write do loops like this:

```java
do {
	code
} while (condition);
```

or like this:

```java
do
{
	code
} while (condition);
```

Note the ; at the end!

##### 6.11.4 Break and Continue

- **Short version** - do NOT use them.
- **Long version**  - CAN be OK in VERY SHORT loops that either need to end early (break) or sometimes need to skip part of the loop (continue - but it's usually better to use if-else etc.) [READ THIS BEFORE USING EITHER BREAK OR CONTINUE.](https://canvas.swansea.ac.uk/courses/68227/pages/6-dot-8-programming-style-and-loops-structured-programming)

## Chapter 07 - Reading Data Safely
*Full page: [[7.4 SYNTAX QUICKGUIDE]]*

##### 7.4.1 Checking that Input is the Correct Type

The way to do this is to use a Scanner - for example, given an  **Scanner**  called  **in**,  **in.hasNextInt()** will return true if the next thing waiting to be read is an integer and false otherwise (there is also e.g.  **in.hasNextDouble()**  etc.)

Do NOT use exception handling ('try-catch') to do this!

##### 7.4.2 Reading Correct Input 'Pattern'

Commonly this needs two nested loops - an inner one to check input is legal; and an outer one to check it is specifically what is required. E.g. to force a user to enter a number between 1 and 10:

```java
Scanner in = new Scanner(System.in);

int inputNum;
do {
	System.out.print("Enter an integer from 1 to 10: ");
	while(!in.hasNextInt()) {
		System.out.println("Not an integer");
		System.out.print("Enter an integer from 1 to 10: ");
		in.nextLine();
	}
	inputNum = in.nextInt();
} while(inputNum < 1 || in
```

Exercise: fix the repeated string in the example above.

##### 7.4.3 Mixing nextLine and nextInt etc.

If you mix calls to  **nextInt()**  and  **nextLine()** you will notice that  **nextLine()**  seems to 'skip' inputs.

- The reason for this is explained in [Section 7.2](https://canvas.swansea.ac.uk/courses/68227/pages/7-dot-2-odd-scanner-behaviour)
- To fix it, put a call to **nextLine()**  after each call to  **nextInt() -**  *there is no need to save the result as it just reads and discards an empty string on the input line left by*  **nextInt().**

## Chapter 08 - Arrays and ArrayLists
*Full page: [[8.12 SYNTAX QUICKGUIDE]]*

##### 8.11.1 Basic Array Syntax

Declare an array like this - this example is an integer array of size 10; replace int and 10 with whatever type/size you need.

```java
int[] someArray = new int[10];
```

To get the length on an array use  **length**  - e.g. in the example above  **someArray.length == 10**. NOTE this is the size of the array not the number of things stored in it!

##### 8.11.2 Looking up Elements in Arrays

Use  **arrayName[index]**  to look up/change an element in an array. E.g. in the example above **someArray[5] = 10;** would set element 5 to 10; then  **int value = someArray[5];**  would set value to the integer stored in element 5 of  **someArray**  (in this case, 10).

The array index (between the [..]) ranges from 0 to length-1 (so in the case of  **someArray**  above, from 0 to 9).

##### 8.11.3 Pre-Populated Arrays

You can create arrays containing data already. For example:

```java
String[] authors = {"Iain M Banks", "Zadie Smith", "Octavia Butler"};
```

is an array of length 3 of strings - where  **authors[0]**  has value Iain M Banks;  **authors[1]** has value Zadie Smith;  **authors[2]** has value Octavia Butler - and  **authors.length == 3**  (remember, indexes run from 0 to length - 1).

##### 8.11.4 ArrayLists

Create an array list like this (which is an array list of Strings).

```java
Arraylist<String> myList = new ArrayList<>();
```

If you want to create an array list of ints, use  **Integer**  (not  **int** ); similarly for e.g. boolean use  **Boolean**  (not  **boolean** ). DO NOT use  **Integer**,  **Boolean**  etc. anywhere else in this module!

##### 8.11.5 ArrayList Operations

These are useful array list operations with examples based on  **myList**  above:

| **Operation** | **Meaning** | **Example** |
| --- | --- | --- |
| listData.get(index) | return the item at location ‘index’ | **String val = myList.get(1); //get element 1 - will crash if there isn't one** |
| listData.add(item) | insert ‘item’ at the end of the list | **myList.add("lemon");** |
| istData.add(index, item) | insert ‘item’ at location ‘index’ | **myList.add(0, "lemon"); //add lemon at location 0 - i.e. at the front of the list** |
| listData.set(index, item) | replace ‘item’ at location ‘index’ | **myList.set(1, "Orange"); //replace element 1 - if there is one (crashes otherwise) - with Orange** |
| listData.size() | return the number of items in the list | **int sizeOfMyList = myList.size(); //sizeOfMyList will contain the number of elements in myList** |
| listData.isEmpty() | returns true if the list is empty | **if (myList.empty()) {... //will execute the body of the if statement if myList contains no data** |
| listData.contains(item) | returns true if ‘item’ is in the list | **if (myList.contains("lemon")){ ..//will execute the body of the if statement if myList contains "lemon"** |
| listData.indexOf(item) | returns the position of the first instance of item in the list (may be more than one) or -1 if it’s not there | **int locationOfLemon = myList.indexOf("lemon");** |
| listData.lastIndexOf(item) | As above but the last instance | **int lastLocationOfLemon = myList.lastIndexOf("lemon");** |
| listData.clear() | Empty the complete list | **myList.clear(); //deletes all data in myList** |
| listData.remove(index) | remove the item at location ‘index’ | **myList.remove(1); //remove element at location 1 - crashes if there isn't one** |
| listData.remove(item) | remove ‘item’ if present – returns true if it was | **if (myList.remove("lemon")) {.. // removes lemon if present, and executes the if statement if it was** |

##### 8.11.6 For-Each Loop

The syntax of the for-each loop is:

```java
for(type name: list) {
	//..code
}
```

where type is the  **type**  of data (e.g. string);  **list**  is an array or array list of  **type**  (e.g. if  **type**  is  **String**  then it must be an array or an array list of  **String**  etc.); and  **name**  is a variable name (made up by you).

For example assuming the array list  **myList**  from above:

```java
for(String element: myList) {
	System.out.println(element);
}
```

prints all the elements in  **myList**  and does the same as (but in a better way than):

```java
for(int i = 0; i < myList.size(); i++) {
	System.out.println(myList.get(i));
}
```

## Chapter 09 - Methods
*Full page: [[9.8 SYNTAX QUICKGUIDE]]*

##### 9.8.1 BEFORE YOU GO ON

If you are reading this  *before* you have done objects and classes (chapters [10](https://canvas.swansea.ac.uk/courses/68227/modules/502608) onwards) you should be putting the keyword  **static**  in front of all these examples.

##### 9.8.2 Method Syntax

The basic syntax of a method is:

```java
returnType name(type argname1, type argname2,...) {
	..code
}
```

where:

returnType is the type of data returned by the method - e.g. String, int, etc. If the method does not return anything this should be the keyword void.

name is the name chosen for the method - the naming style is the same as for variables (i.e. start with lowercase letter).

in the (..) following the name are zero or more  *arguments*

arguments are a pair - type representing the type of the argument (String, int etc.) and name is the name that will be used in the body of the method.

##### 9.8.3 return and void

- Methods that are not void need to return a value of the correct type - e.g. a method String methodName(...) {... must contain at least one statement like: return value; where value is a String (or variable of type String).
- Methods can contain multiple return statements (don't overdo it - it's harder to read).
- Methods that are void do  *not* need a return statement - if they have one it should just be the keyword return; (with no value). There can be multiple return statements (again don't overdo it).

##### 9.8.4 Guidelines for Methods

More or less the same as the list in [section 9.6](https://canvas.swansea.ac.uk/courses/68227/pages/9-dot-6-guidelines-for-methods):

- **Repeated Code**  – if you have repeated code, make it a method (but this is NOT the only reason to have methods!)
- **Single Task**  –  *methods should do one thing* : if your explanation of a method is "it does X and Y" then it should probably be two methods.
- **Keep Small**  – methods should be  *short* : a rule of thumb is a maximum of 25 lines of about 80 columns of text (i.e. fits on the screen) - many good programmers write lots of  *very* short methods.
- **Use Parameters**  – methods that work only with data passed as parameters are easier to understand, more flexible and less prone to errors.
- **Not Too Many Parameters**  – slightly contradicting the above, not  *too* many parameters.
- **Logical Breakdown**  – as you think about the problem you are trying to solve, and break it into parts, you can’t go far wrong if you start by making each logical part a method at least as a starting point.

## Chapter 10 - Classes Part 1
*Full page: [[10.9 SYNTAX QUICKGUIDE]]*

The syntax guide for Chapters 10 and 11 is combined into one at the end of [Chapter 11](https://canvas.swansea.ac.uk/courses/68227/pages/11-dot-10-syntax-quickguide).

## Chapter 11 - Classes Part 2
*Full page: [[11.10 SYNTAX QUICKGUIDE]]*

##### 11.10.1 Basic Class Layout

The basic structure of a class is like this:

```java
import statements here

public class Name {
	constants here e.g.:
	static final int MY_CONSTANT = 5;

	private fields here e.g.:
	private String myField;

	constructors here e.g.:
	public Name(String myParameter) {
		...code
	}

	public methods here e.g.:
	public String myMethod(int myParameter) {
		...code
		return myString;
	}

	private methods here e.g.:
	private int myPrivateMethod(...) {
		..code
		return myInt;
	}
}
```

- Not all of these need to be present (e.g. there may be no private methods).
- The order can be different - but this is quite a good way to do it.

##### 11.10.2 Creating Objects

To create an object of a class do:  **Name myName = new Name(...);** where ... is a list of parameters that match a constructor you have written (in the example above, the constructor has one String so maybe:  **Name myName = new Name("lemon");**

##### 11.10.3 Static vs non-Static

Methods and fields in classes can be static. If you make them static there is only  *one* copy of them - shared between all classes (this is why constants are static). When deciding, ask and answer two questions: is this something that will be the same for  *every* object of a class; or will it be different for each object of a class? E.g. if a class represents a saving account (and so each object is one account) where a maximum amount can be deposited every month, then that maximum amount is the same for all accounts and should be static; but the balance of money in each account will be different, so that should NOT be static.
