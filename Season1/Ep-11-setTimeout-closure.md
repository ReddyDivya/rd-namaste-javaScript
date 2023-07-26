# Episode 11: setTimeout + Closures Interview Question

## setTimeout
- It takes callback function stores it in some place and attaches the timer to it and JS engine proceeds its code.

## Closure
<pre>
  Closure = function's local memory + lexical environment
</pre>

### Example 1:
<pre>
  function x(){
    var i = 1;
    setTimeout(function(){
      console.log(i);
    }, 3000)
    console.log("Namaste JS");
  }
  x();
</pre>

![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/2d1b1c23-8b18-4fe1-947d-15d2569c073b)

### Output 1:
<pre>
  Namaste JS
  1
</pre>

### Code Explanation
1) setTimeOut takes the callback function stores it some place and attaches the timer to it and JS Engine proceeds its code.
That's the reason "Namaste JS" printed first, later 'i' value.
2) If the timer is done, JS takes the function code and puts it in the call stack and runs again 3000 milliseconds as per above code.

### Example 2:
<pre>
  function x(){
    for(var i=1; i<=5; i++){
      setTimeout(function(){
        console.log(i);
      }, i*1000);
    }
    console.log("Namaste JS");
  }
  x();
</pre>

### Output 2:
<pre>
  Namaste JS
  6
  6
  6
  6
  6
</pre>

### Code Explanation
1) JS Engine is referring to 'i' memory not value.
2) JS doesn't wait for anything, it will run the loop again and again and prints only 6.
3) 
###
