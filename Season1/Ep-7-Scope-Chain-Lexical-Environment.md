# Episode 7: The Scope Chain, Scope, and Lexical Environment in JS

## Scope
- Scope is where we can access a specific variable or a function in our code.
- Scope directly depends on the lexical environment.
- Whenever an execution context is created a lexical environment is created.

### Lexical Environment
- Local memory along with the lexical environment of the parent where Lexical means hierarchy or in sequence.
<pre>
  lexical environment = local memory + lexical environment of parent
</pre>

![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/b6a5b00d-f10c-415e-a468-ec2c1ff56518)
![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/fd5ba364-ccbb-4259-9baa-9d0dd3f8391e)

### Example 1:
<pre>
  function a(){
    var b = 10;
    c();
    function c(){
      console.log(b);
    }
  }
  a();
  console.log(b);
</pre>

### Code Explanation
1) To print console.log(b). It's first checked inside c()'s local memory.
2) It's not available there. So, now checked inside the lexical environment of the parent of c() i.e a()
3) THe 'b' variable is available. So, it prints 'b' value i.e. 10 in the console.
4) Imagine, 'b' is not inside a(), then it's checked inside the lexical environment of a() i.e. Global Execution/Global Scope.
   But if it's not there as well. So, now checked inside the lexical environment of GEC i.e. its parent which has nothing. So, null is printed.
   
![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/dd8b285e-ac45-4cf7-b5f4-d2bde7ad35d3)
![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/dfba3f68-8b2d-4a46-866f-8b24d734b77e)
![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/edce938b-5d23-419b-a6dd-e56905581a6a)
![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/1376b8f7-31c7-4333-93e2-ec3e6d093449)

### Output 2:
<pre>
  10
  Uncaught ReferenceError: b is not defined at <anonymous>:10:15
</pre>

## Scope Chain
- The whole chain of lexical environment for finding variables is called Scope Chain.
- The way of finding variables in c(), a(), Global Execution context is known as Scope Chain.
- Scope Chain is nothing but checking for variables in a different lexical environment.

![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/60c77c4e-bfb6-4889-a7c0-cd0a0f1a5b27)

### In browser - lexical environment of c
<pre>
  Local => local memory
  Closure (a) => Lexical environment of parent i.e a()
  Global => Lexical environment of a()'s parent i.e., Global Execution Context
  
  The above whole chain is called Scope Chain.
</pre>



