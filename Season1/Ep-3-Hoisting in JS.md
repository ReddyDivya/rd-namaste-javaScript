# Episode 3: Hoisting in JS (Variables and Functions)

## Hoisting
- Hoisting means we can access variables and functions before initializing them.

- Let's observe the below code and its explanation:
  ### Example 1:
  <pre>
    getName(); // Namaste Javascript
    console.log(x); // undefined
    var x = 7;
    function getName() {
     console.log("Namaste Javascript");
    }
  </pre>

  ### Output 1:
  <pre>
    Namaste Javascript
    undefined
  </pre>

  ### Explanation:
  1) getName(); - We can invoke functions before initializing them i.e. Hoisting.
  2) console.log(x); - x value is undefined because it's not declared and initialized.
  3) console.log(getName); - it prints the whole function because it resides in the GEC.
  4) var x = 7; - Now, the value is reassigned with 7 in the memory.
  5) line 4-6 => getName function is defined

  ![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/e4908ed9-f39f-4082-b654-76afdfa32a3f)

  **Note:** Not defined & undefined are not the same.

  ![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/d07579e8-bc64-4fca-b508-92d0f37b6e42)

  ![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/094e9ec8-c8ad-49fe-a432-de9d4629ad5c)

 ### Example 2:
  <pre>
    getName(); // Namaste Javascript
    console.log(x); // undefined
    
    function getName() {
     console.log("Namaste Javascript");
    }
  </pre>

  ### Output 2:
  <pre>
    Uncaught ReferenceError: x is not defined at <anonymous>:2:17
  </pre>

  ### Let's remove the declaration of 'x' variable
  ![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/e622855e-563c-498c-9a16-ca5e6fea3188)

  ### Hoisting through Arrow Function

  ### Example 3:
  <pre>
    getName(); // Namaste Javascript
    console.log(x); // undefined
    
    var getName = ()  => {
     console.log("Namaste Javascript");
    }
  </pre>

  ### Output 3:
  <pre>
    Uncaught TypeError: getName is not a function at <anonymous>:2:5
  </pre>
  ![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/ba7f54e3-0124-4a51-a518-efe80e419c65)

  ![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/d8ceb2e2-7d36-47d3-a882-552e0c58e58a)

  ![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/bee337e8-743f-4a11-a857-a2ccc04492ca)

  ![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/df9382c7-dbf9-4573-a55f-51a3cfe863be)

  ![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/672d72ea-ec03-4977-9315-b4545334c891)

  ![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/c126801a-d7ea-411f-ab3a-fc9da1179b23)
