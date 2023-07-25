# Episode 8: let and const in JS (Temporal Dead Zone)

## let & const 
- **let & const** declaration are hoisted. We can also say, **let** is in the **Temporal Dead Zone** for the time being.
- These variables are not attached to a window object because they reside in a different memory space.
- We can access let and const variables after initializing values to those variables.

## Let's see the difference between **var** and **let**
### Example 1 - using var:
<pre>
  let a = 10;
  console.log(a);//10
  var b = 100;
  console.log(window.b);//100
  console.log(this.b);//100

  //let variables are not attached to window object
  console.log(window.a);//undefined
  console.log(this.a);//undefined
</pre>

### Output 1:
<pre>
  10
  100
  100
</pre>

For **var** variables are created in memory inside a Global Scope.

### Example 2 - using let:
<pre>
  console.log(a);
  let a = 10;
  var b = 100;
</pre>

![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/4ec157f9-2516-44a5-8c7d-9ec69d0bbdc3)

### Output 2:
<pre>
  Uncaught ReferenceError: a is not defined at <anonymous>:1:13
</pre>

### Code Explanation:
- We can't access 'a' variable before initialization since it's a **let** datatype.
- We can access 'b' variable before initialization(Hoisting) since it's a **var** datatype. Where it's attached to the Global Scope or Global Object.
- For **let** and **const** variables are created memory called Hoisting but stored in a different memory space other than global and we can't access those variables, memory space without initializing them.

## Temporal Dead Zone
- When **let** & **const** are hoisted till any value is assigned to them those variables are  allocated memory in the temporal Dead Zone.
- Whenever we're trying to access a variable from the temporal dead zone it gives a reference error. These can be accessed only after initialization.
- when we're trying to access a variable that is not in the scope, then we'll get a reference error.

### Example 3:
<pre>
  console.log(a);
  let a = 10;
  var b = 100;
</pre>

### Output 3:
<pre>
  Uncaught ReferenceError: a is not defined at <anonymous>:1:13
</pre>

### We can't access let variables with **this** keyword
![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/aad1f6e5-0958-42ef-8734-e6256efa38ec)

### We cannot re-declare let variables
![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/474ab42e-ba78-42a5-b318-96b1fb81e7e9)

## Case: let and let
- redeclaring for let returns a syntax error and doesn't let the JS engine run anything.
  
### Example 4:
<pre>
  console.log("JavaScript");
  let a = 10;
  let a = 100; //redeclaring for let returns a syntax error and doesn't let the JS engine run anything.
</pre>

### Output 4:
<pre>
  Uncaught SyntaxError: Identifier 'a' has already been declared
</pre>

## Case: let and var
- redeclaring for let returns a syntax error and doesn't let the JS engine run anything.
  
### Example 5:
<pre>
  console.log("JS");
  let a = 10;
  var a = 100; //redeclaring for let returns a syntax error and doesn't let the JS engine run anything.
</pre>

### Output 5:
<pre>
  Uncaught SyntaxError: Identifier 'a' has already been declared
</pre>

## Case: var and var
- In the case of var it works well.
  
### Example 6:
<pre>
  console.log("JS");
  let a = 10;
  var b = 100;
  var b = 1000;
  console.log(b);
</pre>

### Output 6:
<pre>
  JS
  1000
</pre>

## Case: const(more strict)

### SyntaxError
1) Syntactically incorrect.
2) No duplicate declarations.

### Example 7:
<pre>
  let a = 10;
  const b;
  b = 1000;
  console.log(b);
</pre>

### Output 7:
<pre>
  Uncaught SyntaxError: Missing initializer in const declaration
</pre>
- The code doesn't run the code. JS engine upfront the syntax error Missing initializer in const declaration.

### TypeError
- Declaration and initialization should happen together. If it doesn't happen it will return Type Error.

### Example 8:
<pre>
  const b = 100;
  b = 1000;
</pre>

### Output 8:
<pre>
  Uncaught TypeError: Assignment to constant variable at <anonymous>:2:5
</pre>

### ReferrenceError
- When the JS engine tries to access variables inside the memory space and we can't access it Then, it gives a reference error.
## Preference
- **const**
- **let** (temporal dead zone)
- **var** (don't use it now, use it consciously)

### Example 9:
<pre>
  console.log(a);//ReferenceError
  let a = 1900;//'a' is in the temporal dead zone
</pre>

### Output 9:
<pre>
  Uncaught ReferenceError: a is not defined at <anonymous>:1:13
</pre>

### Example 10:
<pre>
  console.log(x);//ReferenceError
</pre>

### Output 10:
<pre>
  Uncaught ReferenceError: x is not defined at <anonymous>:1:13
</pre>
- 'x' is some random variable that gives ReferenceError.

## How to avoid errors in the temporal dead zone?
- We can avoid errors in the temporal dead zone by always declaring and initializations on the top of the scope.
- While moving declarations and initializations on the top we are shrinking the Temporal Dead Zone. So, that nothing happens(errors) before initializations.
