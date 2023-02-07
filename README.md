# How-does-the-JavaScript-engine-work? 👋🎥

Have you ever asked yourself “how does this all work behind the scenes?”.It's actually quite fascinating! 😯

I know I have,Having a deep understanding of certain concepts allows us to understand code in a much better way.. 💬

![image](https://user-images.githubusercontent.com/24325914/217118750-038bd7e9-6c29-4890-9d80-ec95db0d137f.png)



##### Don’t worry if you don’t understand any of this yet, at the end of the article you’ll understand every step of this diagram.😊

Let’s go!

## What is JavaScript Engine❓

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


## What is JavaScript Parser❓

![image](https://user-images.githubusercontent.com/24325914/217226365-1a8bdd84-ec25-4000-bf10-5cc3b3e93bfa.png)

### 2-Parser
The first thing the engine does upon executing your code is check the code using the parser.
The parser knows JS syntax and rules, and its job is to go through the code `line by line` and check if the syntax of the code is correct.


If the parser comes across an error ⛔, it stops running and sends out an error. If the code is valid, the parser generates something that’s called an Abstract Syntax Tree (or AST for short).

## What is JavaScript Abstract Syntax Tree (AST)❓

![image](https://user-images.githubusercontent.com/24325914/217226457-93a9d90e-1d3a-42c2-945a-9da9afb6bb22.png)

### 3-Abstract Syntax Tree (AST)
AST is a data structure, which is not unique to JS but actually used by a lot of other languages (some of them are Java, C#, Ruby, Python).

An AST is simply a tree representation of your code, and the main reason the engine creates an AST instead of compiling directly to a `machine code` is that it’s easier to convert to machine code🧑🏼‍💻 when you have the code inside a tree data structure.

## What is JavaScript Interpreter❓

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
 
 ## What is JavaScript Compiler❓

![image](https://user-images.githubusercontent.com/24325914/217235471-23c60edb-1165-448d-b705-b26003d51283.png)

### 2-Compiler
The compiler’s job is to take the IR which the interpreter created, which is in our case Bytecode, and transform it into a machine code using `JIT`
with certain optimizations.⚒
 
compiler instantly translates all code into machine code before executing it.

----------------------------------------------------------------------------------------------------------------------------------------

# How JavaScript Code Gets Executed ❓

When the JavaScript engine scans a script file, it makes an environment called the `Execution Context` that handles the entire transformation and execution of the code.

### There are two phases of JavaScript execution context:

* Creation phase: In this phase, the JavaScript engine creates the execution context and sets up the script's environment. It determines the values of variables and functions and sets up the scope chain for the execution context.

* Execution phase: In this phase, the JavaScript engine executes the code in the execution context. It processes any statements or expressions in the script and evaluates any function calls.

![image](https://user-images.githubusercontent.com/24325914/217263642-d4d30692-16b3-4ead-ae22-a044499874a3.png)

Everything in JS happens inside this execution context. It is divided into two components. One is memory and the other is code. 
It is important to remember that these phases and components are applicable to both global and functional execution contexts.

#### Creation Phase

There are two types of execution contexts:  `global` and `function` .
 The global execution context is created when a JavaScript script first starts to run, and it represents the global scope in JavaScript.
 A function execution context is created whenever a function is called, representing the function's local scope.
 
 At the very beginning, the JavaScript engine executes the entire source code, creates a global execution context, and then does the following things:

1-Creates a global object that is window in the browser and global in NodeJs.

2-Sets up a memory for storing variables and functions.

3-Stores the variables with values as `undefined` and function `references`. [Hoisting](https://www.freecodecamp.org/news/what-is-hoisting-in-javascript/)

#### Execution Phase

Now, in this phase, it starts going through the entire code line by line from top to bottom.


 ` Creation Phase
In the creation phase, the Execution Context is first associated with an Execution Context Object (ECO). The Execution Context Object stores a lot of important data which the code in the Execution Context uses during its run-time.`

The creation phase occurs in 3 stages, during which the properties of the Execution Context Object are defined and set. These stages are:

* Creation of the Variable Object (VO)
* Creation of the Scope Chain
* Setting the value of the this keyword
 
 ## Creation of the Variable Object (VO)
 
 The Variable Object (VO) is an object-like container created within an Execution Context. It stores the variables and function declarations defined within that Execution Context.
 
 ### Global Execution Context (GEC)
> Whenever the JavaScript engine receives a script file, it first creates a default Execution Context known as the Global Execution Context (GEC).
The GEC is the base/default Execution Context where all JavaScript code that is not inside of a function gets executed.
 
 ![image](https://user-images.githubusercontent.com/24325914/217250856-113ad942-126d-47cf-bb8a-27d6b19eb857.png)
 
 > Put the `name` variable and `first`, `second` and `third` fnctions( ) are in the `Global` Execution Context 
 > 
 ![image](https://user-images.githubusercontent.com/24325914/217253584-34cde5a3-b3e9-4c61-9028-ef32afdd7b74.png)
 
 
 ### Function Execution Context (FEC)
> Whenever a function is called, the JavaScript engine creates a different type of Execution Context known as a Function Execution Context (FEC) and put this new Function Execution Context to the top of the Global Execution Context within the GEC to evaluate and execute the code within that function.

> Calling the `first` function( ) with a new  Function Execution Context 

 ![image](https://user-images.githubusercontent.com/24325914/217255279-f8f96385-9a66-4a08-9b31-152b4195139b.png)
 
 > Calling the `second` function( ) with a new  Function Execution Context 
 
 ![image](https://user-images.githubusercontent.com/24325914/217255842-3d804beb-c696-4716-8c7f-5178bb98d032.png)
 
  > Calling the `third` function( ) with a new  Function Execution Context 
 
 ![image](https://user-images.githubusercontent.com/24325914/217258964-c4642515-e5db-494d-a47f-f61bb5834a7e.png)

 
 > After executing `all` the three functions( ) the execution stack will be empty again ! 😄
 
 ![image](https://user-images.githubusercontent.com/24325914/217258589-45531255-d42f-44e9-9dae-7e3b1a71a66d.png)
  
 
## Conclusion
In conclusion, JavaScript execution context is a crucial part of understanding how JavaScript works behind the scenes. It determines the environment in which code is executed and what variables and functions are available to use.

The creation phase includes creating the global and function execution contexts, creating the scope chain, and allocating memories for the variables and functions. During the execution phase, the JavaScript engine executes the code line by line. This includes evaluating and executing statements.

I hope you found this tutorial helpful and informative.😊






 













