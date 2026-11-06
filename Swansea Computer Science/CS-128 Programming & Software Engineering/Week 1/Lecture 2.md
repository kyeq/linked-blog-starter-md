#CS128
#### Code, must be...
- ready on time
- in-budget (cost as much as you said)
- be easily maintainable and changeable
- work ✅

it goes from being art, to engineering, you must worry about:
- quality control
- standards
- testing
- software engineering 
- maintainability

**Budgeting** 💰
typically, around 50% of the budget goes into testing.

#### What this module is about...
- Programming
- Testing (systematically)
- Software Engineering

**Programming is like cooking**
- Data = ingredients
- Program = recipe
- *The tricky part: you write the recipe!*

Programming is very collaborative.
- You must produce readable code.
- You must produce maintainable code.

**Programming language: Java**
> Java is a compiled language.
  *This means that it generates executable code from source code.*
  *It can scan whole programs for errors when compiled*

Java is strongly and statically typed.
Java is an object-orientated language.

- Procedural – historically, this was the mainstream language for many years
- Functional – you don't have any loops or assignments
- Logic – you essentially don't tell the machine what to do, you just give it data and questions
- Object-Orientated – procedural + 'objects' and 'classes'

**Abstraction**

> [!NOTE] Abstraction
> "Pick the kettle up, take the lid off, fill it with water, plug it in, turn it on, and wait for the water to boil" – adding more detail, rather than "boil the kettle"

> 💡 suggestion: start off in labs on Friday – use basic tools – once comfortable, move on.
> don't just stick to the basics. 
> ==**READ CHAPTER 0 AND CHAPTER 1**==

> Try your best to try new software and different methods.
> Don't just stick to just what you know.


#### Java
>Java is for running things.
>Java-c is for compiling it.

**Use Java version 25**
*Ensure that you also have Java-c (compiler)*

You need a decent text-editor.
*Recommended to use Notepad++.*

**Code Example**
> You MUST write the class as the exact name as the file.
> It's best practice to stick to exactly the same.

- Start it with a capital, do not put an underscore, nor a space. 

```java
public class HelloWorld {
	public static void main(String[] args) {
		System.out.println("Hello World"); 
	}
}	
```

> This is a straight-line / sequential program

- First you must compile your program:
	- `javac HelloWorld.java`

- It will then output another file... "HelloWorld.class"

- You can then run your file...
	- `java HelloWorld`

**Code Example with Data**

> Example #1
```java
public class HelloWorld {
	public static void main(String[] args) {
		String text;
		text = "Hello World";
		System.out.println(text); 
		text = "Hi there";
		System.out.println(text);
		
		int value = 5;
		value = value + 1;
	}
}	
```

>Example #2
```java
/*
Program to convert gallons to litres
*/
public class VolumeConverter {
	public static void main(String[] args) {
		int volumeInGallons = 5; //start with lower case, others capitalised
		
		System.out.println(volumeInGallons
		+ " in litres is " + volumeInGallons * 1.456);
	}
}	
```