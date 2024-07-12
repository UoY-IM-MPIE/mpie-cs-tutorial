# Introducing C#

In this module we'll be using the C# (pronounced C Sharp) language to write code that controls the Unity Engine. Please don't feel daunted about having to learn a new programming language at this stage in your degree. C# is actually very similar to JavaScript, so similar that sometimes you can even copy and paste JavaScript into C# and it will just work. This is because they are both have a syntax that is based on the C programming language. 
However, there are some differences you need to be aware of. This set of execises aims to guide you through these differences, so you'll be able to begin writing C# quickly in the first practical classes of the module.

## Dynamic vs. Static Typing

One of the main differences between C# and JavaScipt is that it is statically typed. This means that you have to explicitley say what type of data a variable stores when you declare it. You might remember that in JavaScript you declared varaiables like this:

```javascript
let myNumberVariable = 5
let myStringVariable = "Hello World"
```

In C# you have to declare the type of the variable like this:

```csharp
int myNumberVariable = 5;
string myStringVariable = "Hello World";
```

Look at these two pieces of code, can you notice the difference? In JavaScript code you just use the `let` keyword to declare a variable, and it works out what type of data is stored automatically based on the value you assign to it. However, in C# you have to use a keyord like `int` or `string` to specifically say which type of data the variable will store.

The following table shows some of the some common data types in C#:

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

## Strong vs. Weak Typing

JavaScript is a weakly-typed language. This means you can actually change the type of a variable on the fly after you've declared it. For example, you can do this in JavaScript:

```javascript
let myVariable = 3
myVariable += " is a magic number"
```

This code would work in JavaScript, but it wouldn't work in C#. In C# you have to be very explicit about the types of data you are working with. This can be a bit annoying at first, but it actually makes your code more robust and less error-prone.

The following C# code has been written by a programme who doesn't realise that the language is strongly-typed. Can you fix the error?

<iframe width="100%" height="475" src="https://dotnetfiddle.net/Widget/uspBno" frameborder="0"></iframe>

```csharp
int myVariable = 3;
myVariable = myVariable + " is a magic number";
Console.WriteLine(myVariable);
```

Open this code in an online C# compiler by clicking this link: [https://dotnetfiddle.net/pmYsBm](https://dotnetfiddle.net/pmYsBm). Can you get it to run without errors?




