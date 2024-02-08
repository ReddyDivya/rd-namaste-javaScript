# Episode 2: How JavaScript Code is executed? & Call Stack 

- An Execution Context is created while running JS Code.
- In the Execution Context - there are 2 phases
- **Memory Creation** phase where it skims through every line of code and stores them as a **key-value pair in the Memory block(Variable Environment)**.
- Variables are stored as undefined at the beginning.
- Functions store the whole function.

### Example :

```
var n=2;
function square(num)
{
    var answer = num * num;
    return answer;
}

var square2 = square(n); //it's a function invocation and n is an argument
var square4 = square(4); //it's a function invocation - **for function invocation a new sub-execution context is created**.

console.log(square2);//4
console.log(square4);//16
```

### Output :
```
4
16
```

### Explanation:
- JS starts with the memory creation phase.
- It allocates memory space for variable 'n' (line 1) and function 'square' (line 2).
- For 'n', it stores 'undefined', a special initial value.
- For 'square', it stores the entire function code in its memory space.
- Then, it allocates memory for variables 'square2' and 'square4', storing 'undefined' for them.
- This completes the memory creation phase.

### Output:
- Memory allocated for 'n' with 'undefined'.
- Memory allocated for 'square' with the function code.
- Memory allocated for 'square2' and 'square4' with 'undefined'.

### 1) Memory Creation Phase:

![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/d39ad3aa-3523-4a16-89a9-9f78cf2733ae)

![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/117b999f-2675-460f-9e90-94995cff6af6)

- In the code execution phase (2nd phase), JS processes the code line by line.
- When encountering var n = 2, it assigns the value 2 to 'n', replacing the previous 'undefined' value.
- Since the function 'square' was already defined in the memory creation phase, there's nothing to execute for it now.
- Moving to line 6 (var square2 = square(n)), a new execution context is created for the function invocation.
- Within this new execution context's memory creation phase, memory is allocated for variables 'num' and 'answer', initialized to 'undefined'.
- In the code execution phase of this new context, 2 (the value of 'n') is assigned to 'num'.
- Then, var answer = num * num calculates 2 * 2, resulting in 4, which is stored in 'answer'.
return answer returns the value of 'answer' (4) to the point in the program where the function was invoked from.

![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/af451ec5-dac6-4b5c-a600-682ec35e0310)

### 2) Code Execution Phase:
![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/efeaa276-a413-4190-b740-f8f9c543a568)

```
Global Execution Context
----------------------------
|     Variable:   n   |   2   |
|     Function: square | [Code]|
|  Variable: square2   |   4   |
|  Variable: square4   |  16   |
----------------------------
```

- The global execution context contains variables n, square2, and square4, as well as the function square.
- n is assigned the value 2.
- square2 is assigned the value 4, calculated from the invocation square(n).
- square4 is assigned the value 16, calculated from the invocation square(4).
- The function square with its code is stored in memory.
- Once the execution of square2 and square4 is finished, and there's no further code to execute, the global execution context will be destroyed.

![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/19b1ea14-20c2-4f77-8bb7-688b5ca5996a)

- Once the JS code is finished then **Global Execution Context is deleted from the Call Stack**.

![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/e2c7a930-e7bc-4748-8df7-2e39465afcf5)

### Call Stack

- Call Stack maintains the order of execution of execution context.

![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/1fc853fc-cf9f-481f-8ab3-613512856c7f)

###  Call Stack also known as
![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/ad97ccfd-f537-4d89-96fc-7c5e8d87a203)


### Code Execution Context Creation and Deletion:

JavaScript creates and removes environments where code runs. These environments are called "execution contexts."
Each time you run a function or a block of code, JavaScript creates a new execution context for it.

### Call Stack:

Think of the Call Stack as a list of tasks for JavaScript to complete.
When you run a function, JavaScript adds it to the top of the Call Stack.
JavaScript then starts running that function, and when it's done, it removes it from the Call Stack.

### Keeping Track of Code:

- The Call Stack helps JavaScript keep track of where it is in the script.
- If you call multiple functions within each other, the Call Stack remembers the order they were called in.
- It ensures that JavaScript runs each function in the right order and manages the flow of code execution.

### Watch Demo on YouTube 
[Namaste JavaScript Ep-2](https://youtu.be/iLWTnMzWtj4?si=YWVVBaC1SBysjqYU)
