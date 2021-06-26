
# DEFINE GOALS OF SUCCESS

1. Be able to read jQuery source code and able to under stand what is happening.
2. Complete and understand of writing our own library.

## CONCEPTUAL ASIDE - SYNTAX PARSERS, EXECUTION CONTEXTS AND LEXICAL ENVIRONMENTS

**Syntax Parser** a program that reads your code and determines what it does and if its grammar/syntax is valid.

When you write JavaScript it isn't directly telling computer what to do. You're writing code, but then someone else built programs that convert your JS into something that computer can understand. Those programs are called compilers or interpreters.

**Compilers**  go character by character and translate your code into a set of instructions. Important to understand is that during that process programmers who wrote that compiler can choose to do extra stuff. Your code is not what actually is given to a computer but a translation of it.

**Lexical environment** - where something sits physically in the code you write and what surrounds it. In JavaScript where you write something is important.

example for lexical environment can be -  

1. inside function
2. outside function

**Execution context** - a wrapper to help manage the code that is running. There are lots of lexical environments, areas of the code that you look at physically, but which one is currently running is managed via execution contexts. Execution context contains your running code, but it can also contain things beyond what you've written in your code. Because remember that your code is being translated by a syntax parser.

## CONCEPTUAL ASIDE - NAME-VALUE PAIRS and OBJECTS

**Name value pair**  - a name which maps to a unique value. The name may be defined more than once, but can only have one value in any given execution context.

**Object**  - is a collection of name value pairs.

## THE GLOBAL ENVIRONMENT AND THE GLOBAL OBJECT

**Global execution context** - the base execution context. It creates global object and special variable called `this`. In a browser `this` global object is `window`.

**NOTE: In javascript Global means not inside a function**

[![Bv-5-Zv5c-Ts-00-28-00.png](https://i.postimg.cc/rwZwHNcq/Bv-5-Zv5c-Ts-00-28-00.png)](https://postimg.cc/Yvg7GghP)

[![Bv-5-Zv5c-Ts-00-32-35.png](https://i.postimg.cc/m2JHz4zY/Bv-5-Zv5c-Ts-00-32-35.png)](https://postimg.cc/6yV3gDhq)

[![Bv-5-Zv5c-Ts-00-36-22.png](https://i.postimg.cc/k4q41P8b/Bv-5-Zv5c-Ts-00-36-22.png)](https://postimg.cc/zL28vMxz)

## THE EXECUTION CONTEXT - CREATION AND 'HOISTING'

**Hoisting** - because of the way JS works, you can write in your code a call to a function before an actual function and it will execute without any errors.

```javascript
b();

function b() {
console.log('This works!');
}
```

When parser runs through code it recognizes where you created variables and functions and it sets up memory space for them. So before your code begins to be executed, JS engine has already set aside memory space for all the variables and functions you created. When the code begins to execute line by line it can access it.

However, for variables JS engine puts a placeholder `undefined`, because it doesn't know what it's value will ultimately end up being until it starts executing that line of code.

```javascript
console.log(a);

var a = 'Hello World!';
```

## EXECUTION CONTEXT IS CREATED IN TWO PHASES

1. CREATION PHASE
2. EXECUTION PHASE

[![Bv-5-Zv5c-Ts-00-43-03.png](https://i.postimg.cc/W3T9Bgs1/Bv-5-Zv5c-Ts-00-43-03.png)](https://postimg.cc/sBH9SBBk)

## CONCEPTUAL ASIDE - JAVASCRIPT AND UNDEFINED

`undefined` - is a special value, a keyword that JavaScript sets up to all variables during a creation phase of execution context.

`undefined` in javascript means that the value of the variable in never set/initialized.

## THE EXECUTION CONTEXT - CODE EXECUTION

In the execution phase JS engine runs your code line by line.

## CONCEPTUAL ASIDE - SINGLE THREADED , SYNCRONOUS EXECUTION

**Single threaded** - JavaScript is a single threaded, synchronous language. That means one command execution at a time. Maybe not under the hood of the browser but from our perspective as programmers it is single threaded.

**Synchronous execution** - means one at a time and in order that it appears.

## FUNCTION INVOCATION AND THE EXECUTION STACK

**Invocation** - running or calling a function by using parenthesis ().

**Execution Stack** - every time you invoke a function a new execution context is created for that function and is put on top of execution stack.

[![image.png](https://i.postimg.cc/kXP2DHfz/image.png)](https://postimg.cc/t7DqMB0N)
