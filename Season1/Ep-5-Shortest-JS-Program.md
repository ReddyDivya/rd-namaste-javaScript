# Episode 5: Shortest JS Program, window & this keyword

## Shortest JS Program:
- The shortest JavaScript program is an empty file. Even though it seems like there's nothing happening, the JavaScript engine still does some important things behind the scenes.

##  Global Execution Context (GEC):
- When the JavaScript engine runs any code, it creates the Global Execution Context. This context includes memory space and the execution context.

##  'window' Object:
- The JavaScript engine also creates something called 'window'. It's an object that holds lots of functions and variables.
These functions and variables can be accessed from anywhere in the program.
- A window is a global object along with a global execution context, this variable is also created whenever a JS code runs.
- In the case of browsers, the JS engine creates a window(names will differ as per device) object.

```
this === window
```

## 'this' Keyword:
- The JavaScript engine also creates a special variable called 'this', which points to the 'window' object at the global level.
So, along with the Global Execution Context, a global object ('window') and a 'this' variable are created.

## Different Engine Names:
- In different JavaScript engines, like browsers or Node.js, the name of the global object might change. In browsers, it's called 'window', but in Node.js, it's called something else.
At the global level, this === window.

## Variables in Global Scope:
- If we create any variable in the global scope (outside of any function), those variables are attached to the global object.
- Any code that's in the JavaScript program but not inside any particular function is called Global Space.
- Global Space's variables and functions are attached to the global object that's window. We can access them like

![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/acdd3d3f-5632-4778-b886-5b15031157cd)

![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/0c19ffaa-d0d7-4787-baac-5f9a7f942f68)

## Example 1:

```
var a = 10;
function b(){
 var x = 10;
}
console.log(window.a); //10
console.log(a); //10 - even if we don't mention the window but still points to the global scope.

window.b();

console.log(this.a);//10
console.log(x);
```

## Output 1:
```
 10
 10
 10
 Uncaught ReferenceError: x is not defined at <anonymous>:7:15
```

## Note
```
  window.a
  or
  this.a
  or
  a

  above all are referencing to the same memory in the Global Execution Context.
```

[Watch Demo on YouTube](https://youtu.be/gSDncyuGw0s?si=RxpHAn-U4tPVO1EB)
