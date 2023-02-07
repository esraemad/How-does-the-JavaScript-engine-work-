# How-does-the-JavaScript-engine-work? 👋🎥

Have you ever asked yourself “how does this all work behind the scenes?”. I know I have.
Having a deep understanding of certain concepts allows us to understand code in a much better way.. 💬

![image](https://user-images.githubusercontent.com/24325914/217118750-038bd7e9-6c29-4890-9d80-ec95db0d137f.png)



##### Don’t worry if you don’t understand any of this yet, at the end of the article you’ll understand every step of this diagram.😊

Let’s go!

## What is JavaScript Engine?

![image](https://user-images.githubusercontent.com/24325914/217225843-68715b2d-78e2-4567-9ef3-cb958baa6394.png)

### 1-Engine
The JavaScript Engine is an open-source computer program whose responsibility is to execute/run JavaScript.There are a lot of steps involved in executing the JavaScript Engine, but essentially executing `JavaScript` code is what an engine does. All modern browsers have their own version of the JavaScript Engine. But `Google's V8` Engine is the most popular JavaScript Engine. 

When you write code in JS, you write it in human-readable syntax, with alphabets and numbers. As mentioned, a machine can not understand this type of code. 🥴
This is why each environment has an engine.
In general, the engine’s job is to take that code and transform it into machine code which can eventually be run by the computer processor.

## What are the components of JavaScript Engine?

### The engine consists of `two` main elements:

![image](https://user-images.githubusercontent.com/24325914/217122494-d9d1dff9-b767-4206-b586-c30db58dd817.png)

#### Memory Heap
Heap is a large unstructured data structure that stores all the dynamic data like function definitions, objects, arrays, etc. The memory heap is where the memory allocation happens, it is a location in memory where memory may be allocated at random access.Individual data elements distributed on the heap are typically released in ways that are asynchronous from one another. 

#### Call Stack 
The Call stack is a data structure that functions on the Last In First Out  (LIFO) 🏃🏻‍♀️ principle. The call stack stores the execution context or code for each function. It is defined as an object which stores local variables, functions, and objects of the codes and how would they appear on the screen. Primitive values like int, bool, etc are stored inside the call stack. While function definitions and objects are not stored inside the call stack, they are stored inside the memory heap. The call stack just has the reference or memory address of where these function definitions and objects are stored and would appear on the search engine.


## What is JavaScript Parser?

![image](https://user-images.githubusercontent.com/24325914/217226365-1a8bdd84-ec25-4000-bf10-5cc3b3e93bfa.png)

### 2-Parser
The first thing the engine does upon executing your code is check the code using the parser.
The parser knows JS syntax and rules, and its job is to go through the code `line by line` and check if the syntax of the code is correct.


If the parser comes across an error ⛔, it stops running and sends out an error. If the code is valid, the parser generates something that’s called an Abstract Syntax Tree (or AST for short).

## What is JavaScript Abstract Syntax Tree (AST)?

![image](https://user-images.githubusercontent.com/24325914/217226457-93a9d90e-1d3a-42c2-945a-9da9afb6bb22.png)

### 3-Abstract Syntax Tree (AST)
AST is a data structure, which is not unique to JS but actually used by a lot of other languages (some of them are Java, C#, Ruby, Python).

An AST is simply a tree representation of your code, and the main reason the engine creates an AST instead of compiling directly to a `machine code` is that it’s easier to convert to machine code🧑🏼‍💻 when you have the code inside a tree data structure.

## What is JavaScript Interpreter?

![image](https://user-images.githubusercontent.com/24325914/217228332-dac08e54-6476-4f82-a364-126d53b35835.png)

### 4-Interpreter
The Interpreter’s job is to take the AST that has been created and transform it into an Intermediate Representation of the code `(IR)/Bytecode`, it translates your code and executes it line-by-line

 -An `IR` is a data structure or code which represents the source code. Its role is to be an intermediate step between code that’s written in an abstract language such as JS and machine code.
 
 > But Why do we need to have an IR?
 
> Why not just compile straight to machine code.

![image](https://user-images.githubusercontent.com/24325914/217235950-0da57889-09ad-42b6-abac-e0ee3b7ad9e3.png)

 > There are 2 primary reasons why Engines use IR as an intermediate step between high-level code and machine code:🤞
 
  1-Mobility : when code gets compiled to machine code, it needs to match the hardware that it’s run on.Machine code written for an Intel processor and machine code       written for an ARM processor will be different.
  
  2- Optimizations : it’s easier to run optimizations with IR compared to machine code,
   this is true both from code optimizations point of view and hardware optimizations.
 
 ## What is JavaScript Compiler?

![image](https://user-images.githubusercontent.com/24325914/217235471-23c60edb-1165-448d-b705-b26003d51283.png)

### 2-Compiler
The compiler’s job is to take the IR which the interpreter created, which is in our case Bytecode, and transform it into a machine code using `JIT`
with certain optimizations.
 
compiler instantly translates all code into machine code before executing it.
 











