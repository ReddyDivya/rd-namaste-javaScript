# Episode 9: Block Scope and Shadowing in JavaScript

## Block
- Block is defined by curly braces {}. The block is used to combine multiple JS statements into one group.

### Why block {} is required?
- The group of multiple statements is used where the JS engine expects one statement like an if statement because "if" expects
  single statements syntactically but we're using a group of statements to do that we use block {}.
- Block is compulsory to have multiple statements.

<pre>
  {
    //group of code
  }
</pre>

### Example 1:
<pre>
  {
    var a = 10;
    console.log(a);
  }
</pre>

### Output 1:
<pre>
  10
</pre>

## Block Scope
- The variables and functions that we can access inside the block it's known as block scope.

### Example 1:
<pre>
  {
    var a = 10; // Global Scope

    //let and const are block scope
    let b = 20;
    const c = 30;
  }
</pre>

- let and const are hoisted in separate memory space and reserved as an undefined.
- let and const are block scope means can't be accessed out of stock.

### Example 2:
<pre>
  {
    var a = 10;
    let b = 20;
    const c = 30;
   
    console.log(a);//10
    console.log(b);//20
    console.log(c);//30
  }

  console.log(a);//10
  console.log(b);
  console.log(c);
</pre>

### Output 2:
<pre>
  Uncaught ReferenceError: b is not defined at <anonymous>:12:15
</pre>
- The moment we're executing the line **console.log(b);** the block scope is removed in the browser.

## Shadowing
- If we have a same named variable outside of the block {}, that variable is going to be shadowed by the
  variable inside the block because both are pointing to same memory location.

### Example 3 - using var:
<pre>
  var a = 100;
  {
    var a = 10; //this variable shadows the above 'a' = 100 variable
    var b = 20;
    const c = 30;

    console.log(a);//10 - because of shadowing, 10 is printed
    console.log(b);
    console.log(c);
  }
  console.log(a);//10 - because of shadowing, 10 is printed, because pointing to same memory location.
</pre>


### let and const are hoisted and stored in different scope. In browser, let and const are stored in the 'script' label.

### Example 4 - using let:
<pre>
  let b = 100; //let and const are hoisted and stored in different scope.

  {
    var a = 10; //global scope because it's a var datatype
    let b = 20; //shadowing the value of above 'b' variable
    const c = 30;
    console.log(a);//10
    console.log(b);//20 - 'b' variable got shadowed, here 'b' refers to block scope
    console.log(c);//30
  }
  console.log(b);//100 - refers to outside scope since 'b' is a let datatype
</pre>

### Output 4:
<pre>
  10
  20
  30
  100
</pre>

## const is like let

### Example 5:
<pre>
  const c  = 100;
  {
    var a = 10;
    let b = 20;
    const c = 30; //shadowing the value of the above 'c' variable with 30
    console.log(a);//10
    console.log(b);//20
    console.log(c);//30  - 'c' variable got shadowed, here 'c' refers to block scope
  }
  console.log(c);//100 - because its outside of the scope i.e. script block[check in browser]
</pre>

### Output 5:
<pre>
  10
  20
  30
  100
</pre>

## Shadowing behaves in a similar way in functions as well.

### Example 6:
<pre>
  var c = 100;
  function x(){
    const c = 10; //shadowing the value of the above 'c' variable with 10
    console.log(c);//10 - 'c' variable got shadowed, here 'c' refers to block scope
  }
  x();
  console.log(c);//100 - because its outside of the scope i.e. script block[check in browser]
</pre>

### Output 6:
<pre>
  10
  100
</pre>

## Illegal Shadowing in case of let
- We can't shadow a **let** with a **var** in a block scope. It throws an error because it's crossing the boundary of its scope.

### Example 7: - Invalid let -> var

<pre>
  let a = 20;
  {
    //we can do it with **let** type
    var a = 20; //SyntaxError
  }
</pre>

### Output 7:
<pre>
  Uncaught SyntaxError: Identifier 'a' has already been declared
</pre>

### Example 8: - Valid var -> let
<pre>
    var a = 20;
    {
      let a = 40;//shadowed
      console.log(a);
    }
</pre>

### Output 8:
<pre>
  40
</pre>

## Try implementing illegal shadowing in case of functions

### Example 9: - Valid let -> var
<pre>
  let a = 20;
  function x(){
    var a = 20;
  }
</pre>

### Code Explanation
- This program doesn't throw any error at all because **var** has its own function boundaries.
- It's not interfering with <pre>let a = 20</pre>
- This is totally valid. So, we can't call it illegal shadowing.

## Illegal shadowing in case of const
### Example 10:
<pre>
  const a  = 20;
  {
    const a  = 30; //shadowing a variable
    console.log(a);//30
  }
</pre>
- works fine because it's in the same memory.
  
### Output 10:
<pre>
  30
</pre>

## Block scope also follows the lexical scope

### Lexical Scope

<pre>
  //outer
  const a = 20;
  {
    //inner-1
    const a = 100;
    {
      //inner-2
      const a = 200; //shadowing 'a' variable with 200. since const is a block scope.
      console.log(a);//200 - because 'a' got shadowed
    }
    console.log(a);//100 - shadowing 'a' variable with 100. since const is a block scope.
  }
  console.log(a);//20 - global scope
</pre>

  ### Output 11:
  <pre>
    200
    100
    20
  </pre>

  ### Code Explanation
  1) console.log(a); in inner-2 block, if 'a' variable isn't available.
     Then, it checks 'a' in the lexical environment of its parent i.e. a=100
  2) If 'a' is not available the inner-1 block. Then, it checks 'a' in the lexical environment of its parent i.e. outer block.
      i.e. Global Execution Context a=20.

  ## Note
   ### Scope is same for normal functions and arrow functions
   ### Block scope rules are the same as well.
