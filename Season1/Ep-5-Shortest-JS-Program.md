# Episode 5: Shortest JS Program

- An empty JS file is a shortest program. Even if there's nothing in the file, but still it creates a Global Execution Context and also a window global object created by JavaScript engine.
- JS Engine also creates "this" keyword.
- Global object incase of browser is known as window.

## What's window?
1. A window is a global object along with a global execution context, this variable is also created whenever a JS code runs.
2. In the case of browsers, the JS engine creates a window(names will differ as per device) object.

<pre>
   this === window
</pre>

## Global Scope
- Any code that's in the JavaScript program but not inside any particular function is called Global Space.
- Global Space's variables and functions are attached to the global object that's window. We can access them like

### Example 1:

<pre>
  var a = 10;
  function b(){
    var x = 10;
  }
  console.log(window.a); //10
  console.log(a); //10
  console.log(x);
  
  window.b()

  console.log(this.a);//10
</pre>

### Output 1:
<pre>
    10
    10
    Uncaught ReferenceError: x is not defined at <anonymous>:7:15
</pre>

## Note
<pre>
  window.a
  or
  this.a
  or
  a

  above all are referencing to the same memory in the Global Execution Context.
</pre>

  ![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/acdd3d3f-5632-4778-b886-5b15031157cd)

  ![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/0c19ffaa-d0d7-4787-baac-5f9a7f942f68)
