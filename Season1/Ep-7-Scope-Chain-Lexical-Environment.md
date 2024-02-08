# Episode 7: The Scope Chain, Scope & Lexical Environment

## Scope
- Scope in Javascript is directly related to Lexical Environment.
- Scope is where we can access a specific variable or a function in our code.
- Scope directly depends on the lexical environment.
- Whenever an execution context is created a lexical environment is created.

## Lexical Environment
- Local memory along with the lexical environment of the parent where Lexical means hierarchy or in sequence.

```
lexical environment = local memory + lexical environment of parent
```

## CASE 1 :
```
function a() {
 console.log(b); // 10
 // Instead of printing undefined it prints 10, So somehow this a function could access
the variable b outside the function scope.
}
var b = 10;
a();
```

## CASE 1 - Output:
```
10
```

## CASE 2:
```
// CASE 2
function a() {
 c();
 function c() {
 console.log(b); // 10
 }
}
var b = 10;
a();
```

## CASE 2 - Output:
```
10
```

## CASE 3:
```
// CASE 3
function a() {
 c();
 function c() {
 var b = 100;
 console.log(b); // 100
 }
}
var b = 10;
a();
```

## CASE 3 - Output:
```
100
```

## CASE 4:
```
// CASE 4
function a() {
 var b = 10;
 c();
 function c() {
 console.log(b); // 10
 }
}
a();
console.log(b); // Error, Not Defined
```

## CASE 4 - Output:

```
10
Uncaught ReferenceError: b is not defined
```

Let's try to understand the output in each of the cases above

## Case 1:
- function a can access variable b from the Global scope.

## Case 2:
- 10 is printed. This shows that even within a nested function, a global scope variable can be accessed.

## Case 3:
- 100 is printed, indicating that a local variable with the same name takes precedence over a global variable.

## Case 4:
- A function can access a global variable, but the global execution context cannot access any local variable.

To summarize the above points in terms of execution context:
```
Call Stack:

call_stack = [GEC, a(), c()]
Memory Sections of Each Execution Context:

c() Execution Context:

c() = [[lexical environment pointer pointing to a()]]
a() Execution Context:

a() = [b:10, c:{}, [lexical environment pointer pointing to GEC]]
Global Execution Context (GEC):

GEC = [a:{}, [lexical environment pointer pointing to null]]
```

![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/b6a5b00d-f10c-415e-a468-ec2c1ff56518)
![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/fd5ba364-ccbb-4259-9baa-9d0dd3f8391e)

## Example 1:
```
function a(){
  var b = 10;
  c();
  function c(){
    console.log(b);
  }
}
a();
console.log(b);
```

## Explanation:
- To print console.log(b). It's first checked inside c()'s local memory.
- It's not available there. So, now checked inside the lexical environment of the parent of c() i.e a()
- THe 'b' variable is available. So, it prints 'b' value i.e. 10 in the console.
- Imagine, 'b' is not inside a(), then it's checked inside the lexical environment of a() i.e. Global Execution/Global Scope.
   But if it's not there as well. So, now checked inside the lexical environment of GEC i.e. its parent which has nothing. So, null is printed.
   
![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/dd8b285e-ac45-4cf7-b5f4-d2bde7ad35d3)
![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/dfba3f68-8b2d-4a46-866f-8b24d734b77e)
![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/edce938b-5d23-419b-a6dd-e56905581a6a)
![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/1376b8f7-31c7-4333-93e2-ec3e6d093449)

## Output 1:
```
10
Uncaught ReferenceError: b is not defined at <anonymous>:10:15
```

- So, Lexical Environment = local memory + lexical env of its parent. Hence, Lexical Environement is the local
memory along with the lexical environment of its parent
- `Lexical`: In hierarchy, In order
- Whenever an Execution Context is created, a Lexical environment(LE) is also created and is referenced in the local Execution Context(in memory space).
- The process of going one by one to parent and checking for values is called scope chain or Lexcial environment chain

## Scope Chain
- The whole chain of lexical environment for finding variables is called Scope Chain.
- The way of finding variables in c(), a(), Global Execution context is known as Scope Chain.
- Scope Chain is nothing but checking for variables in a different lexical environment.

## Example:
```
function a() {
 function c() {
 // logic here
 }
 c(); // c is lexically inside a
} // a is lexically inside global execution
```

- Lexical or Static scope refers to the accessibility of variables, functions and object based on physical location in source code

```
Global {
 Outer {
 Inner
 }
}
// Inner is surrounded by lexical scope of Outer
```
- `TLDR` - An inner function can access variables which are in outer functions even if inner function is nested deep. In
any other case, a function can't access variables not in its scope

![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/60c77c4e-bfb6-4889-a7c0-cd0a0f1a5b27)

## In browser - lexical environment of c
```
  Local => local memory
  Closure (a) => Lexical environment of parent i.e a()
  Global => Lexical environment of a()'s parent i.e., Global Execution Context
  
  The above whole chain is called Scope Chain.
```
[Watch Demo on YouTube](https://youtu.be/uH-tVP8MUs8?si=z_7YPc3OLw4mCmWL)
