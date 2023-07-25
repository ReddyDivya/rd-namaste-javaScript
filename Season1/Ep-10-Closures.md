# Episode 10: Closures

- The Closure is a function bundled together with its parent's lexical environment.
<pre>
  Closure = function + lexical Scope of its parents
</pre>

### Example 1:

<pre>
  function x()
  {
    var a = 7;
    function y()
    {
       //We can access y() function's parent lexical environment i.e we can access 'a' variable of x()
       console.log(a); //7
    }//y

    y();
  }//x

  x();
</pre>

### Output 1:

<pre>
  7
</pre>

The function y() is forming a closure with parent's lexical environment i.e x()

## Return a function
A function returns another function but they still maintain the lexical scope.

### Example 2:

<pre>
  function x()
  {
    var a = 7;
    function y()
    {
       //We can access y() function's parent lexical environment i.e we can access 'a' variable of x()
       console.log(a); //7
    }//y

    return y; //returning a y()
  }//x

  var z = x();
  console.log(z);
  z(); //7 - Though everything is removed from the call stack, y() remembers its lexical scope i.e. remembers the memory of an 'a' variable.
</pre>

### Another way of writing the Example 2:
<pre>
  function x()
  {
    //lexical scope of y()
    var a = 7; 
    return function y(){
      console.log(a);
    }
  }//x

  var z = x();
  console.log(z);
  z(); //'z' remembers 'a' value because of closure
</pre>

### Output 2:

<pre>
  ƒ y()
    {
       //We can access y() function's parent lexical environment i.e we can access 'a' variable of x()
       console.log(a); //7
    }

  7
</pre>

### Example 3:

<pre>
  function x(){
    //lexical scope of y()
    var a = 7; 
    function y(){
      console.log(a);
    }
    a = 100; //reassigned 'a' variable
    return y;
  }//x

  var z = x();
  console.log(z);
  z();
</pre>

### Output 3:
<pre>
  ƒ y(){
      console.log(a);
    }
  
  100
</pre>

Because of the closure, 'z' is referring to 'a' memory which is reassigned with 100 before returning the y().

### Example 4:

<pre>
  function z(){
    var b = 900;
    function x(){
      var a = 7;
      function y()
      {
        console.log(a,b); //'a' is a lexical scope of y() and 'b' is a lexical scope of x()
      }//y
      y();
    }//x
    x();
  }//z

  z();
</pre>

- y() forms a closure along with the 'a' variable which is its parent's lexical environment and with the variable 'b' which is its parent's parent lexical scope.
- 'a' and 'b' variables are retained though they are removed from the call stack.

## Conclusion
Closure is a powerful concept because this remembers values even when they aren't in the call stack. This makes JavaScript very powerful.
