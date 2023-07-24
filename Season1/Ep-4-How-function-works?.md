# Episode 4: How function works in JavaScript?

### Example 1:
<pre>
  var x = 1;
  a(); //10
  b(); //100
  console.log(x);

  function a(){
    var x = 10;
    console.log(x);
  }

  function b(){
    var x = 100;
    console.log(x);
  }
</pre>

### Let's see the Explanation
![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/9585cf56-dccd-4f45-b4cb-32504d3896b9)
![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/f42a00ff-e8a3-4e7b-8683-25b06112cfed)

### Output 2:
<pre>
  10
  100
  1
</pre>
