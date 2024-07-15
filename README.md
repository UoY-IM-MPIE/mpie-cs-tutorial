# Introducing C# (compared to p5.js / JavaScript)

In this module we'll be using the C# (pronounced C Sharp) language to write code that controls the Unity Engine. Please don't feel daunted about having to learn a new programming language at this stage in your degree. C# is actually very similar to JavaScript, so similar that sometimes you can even copy and paste JavaScript into C# and it will just work. This is because they are both have a syntax that is based on the C programming language. 
However, there are some differences you need to be aware of. This set of exercises aims to guide you through these differences, so you'll be able to begin writing C# quickly in the first practical classes of the module.

## Dynamic vs. Static Typing

One of the main differences between C# and JavaScript is that it is statically typed. This means that you have to explicitly say what type of data a variable stores when you declare it. You might remember that in JavaScript you declared variables like this:

```javascript
let myNumberVariable = 5
let myStringVariable = "Hello World"
```

In C# you have to declare the type of the variable like this:

```csharp
int myNumberVariable = 5;
string myStringVariable = "Hello World";
```

Look at these two pieces of code, can you notice the difference? In JavaScript code you just use the `let` keyword to declare a variable, and it works out what type of data is stored automatically based on the value you assign to it. However, in C# you have to use a keyword like `int` or `string` to specifically say which type of data the variable will store.

The following table shows some common data types in C#:

| Keyword | Description                                  |
|---------|----------------------------------------------|
| int     | An integer (i.e. whole) number               |
| float   | A floating point (i.e. decimal point) number |
| string  | A sequence of characters                     |
| bool    | A boolean value (true or false)              |

Can you convert the following JavaScript code into C#?

```javascript
let maximum = 10
let word = "Hello"

for(let i = 0; i < maximum; i++) 
{
    print(word)
}
```

Open this code in an online C# compiler by clicking this link: [https://dotnetfiddle.net/BGW114](https://dotnetfiddle.net/BGW114). Can you get it to run without errors? 

As well as changing the `let` keywords to the appropriate types, you'll also need to:
- Add a semicolon `;` to the end of each line (this is how C# knows that a line of code has ended)
- Change the `print` function to `Console.WriteLine` (this is how you print to the console in C#)

You'll notice in this code that a `for` loop is just the same in C# as it is in JavaScript. `while` loops and `if` statements are also the same, along with many other aspects of the language's syntax. Can you edit the code so that it only prints the word hello when `i` is even?

## Implicit Typing ##

In C# you can use the `var` keyword to declare a variable without specifying its type. The compiler will automatically work out the type of the variable based on the value you assign to it. For example, you could write the above code in C# without explicitly declaring the type of the variables like this:

```csharp
var maximum = 10;
var word = "Hello";

for(var i = 0; i < maximum; i++) 
{
    Console.WriteLine(word);
}
```
It is totally fine to use this language feature when writing C#, and often it can make your code more readable. However, the language style guide states that you should only use `var` when the type of the variable is obvious from the value you assign to it. For instance, in the above example it's pretty clear which variables are integers and which are strings. However, in the following snippet it isn't clear what the type of the variable `theThing` is, so in this case it would be preferable to explicitly declare the type of the variable:

```csharp
var theThing = GetTheThing();
```

## Strong vs. Weak Typing

JavaScript is a weakly-typed language. This means you can actually change the type of a variable on the fly after you've declared it. For example, you can do this in JavaScript:

```javascript
let myVariable = 3
myVariable = myVariable + " is a magic number"
```

This code would work in JavaScript, but it wouldn't work in C#. In C# you have to be very explicit about the types of data you are working with. If you declare a variable as an integer, for example, you can't change it later. That variable will be an integer forever. If you want then store a string that has a sentence with that integer in it (as in the above example) you need to make a new string variable as well. This can be a bit annoying at first, but it actually makes your code more robust and less error-prone.

The following C# code has been written by a programmer who doesn't realise that the language is strongly-typed. Can you fix the error?

```csharp
int myVariable = 3;
myVariable = myVariable + " is a magic number";
Console.WriteLine(myVariable);
```
Open this code in an online C# compiler by clicking this link: [https://dotnetfiddle.net/pmYsBm](https://dotnetfiddle.net/pmYsBm). Can you get it to run without errors?

## Function Return Types

In C# you have to explicitly say what type of data a function returns. This is different from JavaScript, where you can just return a value from a function without saying what type of data it is. For example, in JavaScript you might write a function like this:

```javascript
function getMyName() 
{
    return "Sarah";
}
```

This function returns a `string`. In C# you have to explicitly specify this by putting the type of the return value before the function name, instead of the keyword `function` that you have in JavaScript. For example:

```csharp
string GetMyName() 
{
    return "Sarah";
}
```

Can you convert the following JavaScript code so that it works in C# by specifying the function return types (and changing the print statement)?

```javascript
function getMyAge() 
{
    return 21;
}

function getMyName() 
{
    return "Sarah";
}

print(getMyName() + " is " + getMyAge() + " years old");
```

Load it up in the online C# compiler by clicking this link: [https://dotnetfiddle.net/qJIEBP](https://dotnetfiddle.net/qJIEBP). Can you get it to run without errors?

You might be wondering what keyword to use if a function doesn't return anything. In these cases, you use the `void` keyword, like this:

```csharp
void PrintTheTruth() 
{
    Console.WriteLine("The Interactive Media BSc is the best");
}
```

## Function Parameter Types

In C# you also have to specify the types of the parameters that a function takes (you might have noticed a pattern by now!). This is different from JavaScript, where you can just pass any type of data into a function without specifying what type it is. For example, in JavaScript you might write a function like this:

```javascript
function addTwoNumbers(a, b) 
{
    return a + b;
}
```
In C# you have to specify the types of the parameters by putting a type keyword before each one, like this:

```csharp
int AddTwoNumbers(int a, int b) 
{
    return a + b;
}
```

The following function has been written by a programmer who doesn't know that you need to specify the types of parameters in C#. Can you fix it?

```csharp
void PrintWordThisManyTimes(word, times) 
{
    for(var i = 0; i < times; i++) 
    {
        Console.WriteLine(word);
    }
}
```
Load the code up in the online C# compiler by clicking this link: [https://dotnetfiddle.net/qoCGOc](https://dotnetfiddle.net/qoCGOc). Can you get it to run without errors?

## Classes in C# vs. JavaScript

We can declare classes in C# in quite a similar way to JavaScript. However, there are some important differences. In JavaScript, you might write a class like this:

```javascript
class Money
{
    #amount = 0;
    
    constructor(amount) 
    {
        this.#amount = amount;
    }

    getAmount() 
    {
        return this.#amount;
    }
}
```

In C# you would write the same class as this:

```csharp
class Money
{
    private int amount = 0;
    
    public Money(int amount) 
    {
        this.amount = amount;
    }

    public int GetAmount() 
    {
        return amount;
    }
}
```

You might notice the following differences, in addition to those we've already seen in the earlier sections:
- In JavaScript, you add a `#` symbol before a variable to specify that it should only be visible in the class. In C# you use the `private` keyword if you want it to be hidden and `public` if you want it to be visible.
- In JavaScript, you use the `constructor` keyword to define the constructor of the class. In C# you use the name of the class itself.
- In C# you don't always have to use the `this` keyword to refer to class variables. You can just use the variable name on its own. The only time you need to use `this` is when you have a local variable with the same name as a class variable, such as in the example's constructor.

Can you convert the following JavaScript class, so it will compile as valid C#?

```javascript
class Person
{
    #name = "";
    #age = 0;
    
    constructor(name, age) 
    {
        this.#name = name;
        this.#age = age;
    }

    getName() 
    {
        return this.#name;
    }

    getAge() 
    {
        return this.#age;
    }
}
```

Load the code up in the online C# compiler by clicking this link: [https://dotnetfiddle.net/wt9m9t](https://dotnetfiddle.net/wt9m9t). Can you get it to compile without errors?

## Conclusion and Optional Extra Practice

I hope that this introduction has shown you that C# is not that different from JavaScript, and that you will be able quickly get up to speed with the language. There are of course other differences not covered here. However, we will learn about these differences while using Unity in practicals as the module progresses. If you see anything that confuses you, just stick up your hand and ask us for help!

If you'd like to practice C# further, why not log onto [https://leetcode.com/](https://leetcode.com/) and try some of the C# problems there? This is a great resource for improving your coding and preparing yourself for the kinds of exercises that are commonly set in technical job interviews too.
