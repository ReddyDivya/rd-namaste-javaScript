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

## Preference
- **const**
- **let** (temporal dead zone)
- **var** (don't use it now, use it consciously)

## How to avoid a temporal dead zone?
- We can avoid this by putting all declarations on top of the scope.
