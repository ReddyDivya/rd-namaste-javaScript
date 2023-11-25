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
3) It will push that setTimeOut function(all these 5 funs) into call stack.
4) It doesn't wait for the timer to expire. So, it will print Namaste JS and when the timer expire, it's too late and the value of i because the for loop is constantly running(1, 2, 3, 4, 5, 6).
5) So, the i = 6; and when this callback function runs by that time the i=6 in the memory location. So, that's why it prints 6 everytime because all of these callback function are referring to i memory location, the same variable runs 5 times and because the increment of i gone to 6.

### Why is it happening so?
Because for every iteration, it's referring to the same i copy.
Because i  for each and every copy of setTimeOut function is referring to the same spot in memory i.e., iwhich has now become 6 because for loop is continously running by the time the callback function gets a chance to execute by that time i value is changed because of loop to 6 => i=6

So, the problem lies over I

### How to fix the above issue?
A: use **let** in the for loop because let has a block scope that means for each and every loop iteration, then i is a new copy everytime. Eachtime setTimeOut is run callback function has a new copy of i. It's own identity i with it.

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

It makes 5 copies of variable i and they form closure with each and every setTimeOut function
i=1 => setTimeOut + i=1 => closure 1
i=2 => setTimeOut + i=2 => closure 2
i=3 => setTimeOut + i=3 => closure 3
i=4 => setTimeOut + i=4 => closure 4
i=5 => setTimeOut + i=5 => closure 5

Each time its referring to different memory locations which is their individual i => separate copy of i.

### Why isn't working with var and working with let?
A: Because let is a blockscope, it creates a new copy everytime when loop is executed.

### `Imp` Achieve the correct functionality with `var` only?
A: Only closure help us, the issue was the `i` in the setTimeOut was referring to same `i` memory location. We can fix by giving new `i` copy for every loop iteration.
We achieve by closures.

```
function x()
{
  for(var i=1; i<=5; i++)
  {
    //in this close function, we pass i; it creates a new copy of i and fixes issue
    function close(x)
    {
      setTimeOut(function() {
        console.log(x);
      }, x*1000);
    }//close
    close(i);//we are sending new copy of i everytime
  }//for
  console.log("Namaste JS")
}//x;

x();
```

