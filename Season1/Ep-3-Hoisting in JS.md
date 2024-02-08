# Episode 3: Hoisting in JavaScript (variables & functions)

## Hoisting
Hoisting is a concept that enables us to extract values of variables and functions even before `initialising/assigning value without getting errors. This happens due to the 1st (memory creation phase) of the Execution Context`.

Let's observe the below code and its explanation:

## Example 1:
```
getName(); // Namaste Javascript
console.log(x); // undefined
var x = 7;
function getName() {
 console.log("Namaste Javascript");
}
```

## Output 1:
```
Namaste Javascript
undefined
```

## Explanation:
- In many other programming languages, accessing something that hasn't been created (defined) would result in an outright error.
- However, in JavaScript, during the memory creation phase, it assigns 'undefined' to variables and allocates memory for functions.
- During execution, JavaScript executes whatever is asked of it.
- In JavaScript, execution happens line by line without prior compilation.
- Because of this, if a variable is accessed before it's declared and initialized, it will print 'undefined' without throwing an error.
- This behavior is not considered an error in JavaScript.
- However, if a variable is removed or accessed before it's declared and not initialized, it will result in an error like `Uncaught ReferenceError: x is not defined`.

So in Episode 2, we learned that execution context gets created in two phases, so even before code execution,
memory is created so in the case of a variable, it will be initialized as undefined while in the case of function the whole
function code is placed in the memory. 

![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/e4908ed9-f39f-4082-b654-76afdfa32a3f)

**Note:** Not defined & undefined are not the same.

![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/d07579e8-bc64-4fca-b508-92d0f37b6e42)

### Let's see what's inside the getName

![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/094e9ec8-c8ad-49fe-a432-de9d4629ad5c)


## Example 2:
```
  getName(); // Namaste Javascript
  console.log(x); // undefined
  
  function getName() {
   console.log("Namaste Javascript");
  }
```

## Output 2:
```
  Uncaught ReferenceError: x is not defined at <anonymous>:2:17
```

## Let's remove the declaration of 'x' variable & see what happens

![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/e622855e-563c-498c-9a16-ca5e6fea3188)

## Hoisting through Arrow Function
- In the Arrow function, it's considered a variable instead of a function.

## Example 3:
```
  getName(); // Namaste Javascript
  console.log(x); // undefined
  
  var getName = ()  => {
   console.log("Namaste Javascript");
  }
```

## Output 3:
```
  Uncaught TypeError: getName is not a function at <anonymous>:2:5
```

![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/ba7f54e3-0124-4a51-a518-efe80e419c65)

![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/d8ceb2e2-7d36-47d3-a882-552e0c58e58a)

![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/bee337e8-743f-4a11-a857-a2ccc04492ca)

![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/df9382c7-dbf9-4573-a55f-51a3cfe863be)

![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/672d72ea-ec03-4977-9315-b4545334c891)

![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/c126801a-d7ea-411f-ab3a-fc9da1179b23)

[Watch Demo on YouTube](https://youtu.be/Fnlnw8uY6jo?si=dGnyn7gTCGBnAfB3)
