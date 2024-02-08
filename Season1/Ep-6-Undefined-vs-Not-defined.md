# Episode 6: undefined vs not defined in JavaScript

## Undefined
- Undefined is a special keyword, separate memory is created too. It can be assigned with value in the later part of the code.
- Like a placeholder which means a memory is allocated to a variable already.

### Example 1:
<pre>
  console.log(a);//undefined
  var a = 7;
  console.log(a);//7
</pre>

![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/676800aa-16a9-4c48-893c-a3729ad4f72b)

### Output 1:
<pre>
  undefined
  7
</pre>

![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/70620df3-1e24-42aa-9a12-470c904968ed)

JavaScript is a loosely typed language. It doesn't attach its variables to any datatype.
### Example 2:
<pre>
  var a = "Welcome";//string
  console.log(a);//Welcome
  var a = 74;
  console.log(a);//74
</pre>

### Output 2:
<pre>
  Welcome
  74
</pre>

![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/79025f74-7d93-4892-a7cd-a9e3052b0199)
![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/d82f7e2a-a6bb-4025-afd6-ab074819ecb0)

## Not Defined
- No memory is allocated but still, we are trying to access it.

### Note
- Never do this, not a good programming practice.
<pre>
  a = undefined; 
</pre>
