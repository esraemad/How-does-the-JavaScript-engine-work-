# How-does-the-JavaScript-engine-work? 👋🎥

Have you ever asked yourself “how does this all work behind the scenes?”. I know I have.
Having a deep understanding of certain concepts allows us to understand code in a much better way.. 💬

![image](https://user-images.githubusercontent.com/24325914/217118750-038bd7e9-6c29-4890-9d80-ec95db0d137f.png)





##### Don’t worry if you don’t understand any of this yet, at the end of the article you’ll understand every step of this diagram.😊

Let’s go!

## What is JavaScript Engine?

The JavaScript Engine is an open-source computer program whose responsibility is to execute/run JavaScript.There are a lot of steps involved in executing the JavaScript Engine, but essentially executing `JavaScript` code is what an engine does. All modern browsers have their own version of the JavaScript Engine. But Google's V8 Engine is the most popular JavaScript Engine. 

When you write code in JS, you write it in human-readable syntax, with alphabets and numbers. As mentioned, a machine can not understand this type of code. 🥴
This is why each environment has an engine.
In general, the engine’s job is to take that code and transform it into machine code which can eventually be run by the computer processor.

## What are the components of JavaScript Engine?

### The engine consists of `two` main elements:

![image](https://user-images.githubusercontent.com/24325914/217122494-d9d1dff9-b767-4206-b586-c30db58dd817.png)

#### Memory Heap
Heap is a large unstructured data structure that stores all the dynamic data like function definitions, objects, arrays, etc. The memory heap is where the memory allocation happens, it is a location in memory where memory may be allocated at random access.Individual data elements distributed on the heap are typically released in ways that are asynchronous from one another. 

### Call Stack 
The Call stack is a data structure that functions on the Last In First Out  (LIFO) 🏃🏻‍♀️ principle. The call stack stores the execution context or code for each function. It is defined as an object which stores local variables, functions, and objects of the codes and how would they appear on the screen. Primitive values like int, bool, etc are stored inside the call stack. While function definitions and objects are not stored inside the call stack, they are stored inside the memory heap. The call stack just has the reference or memory address of where these function definitions and objects are stored and would appear on the search engine.





