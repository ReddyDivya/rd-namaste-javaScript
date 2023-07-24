## What happens when we run a JS Code?

- An Execution Context is created while running JS Code.
- In the Execution Context - there are 2 phases
	- **Memory Creation** phase where it skims through every line of code and stores them as a **key-value pair in the Memory block(Variable Environment)**.
	- Variables are stored as undefined at the beginning.
	- Functions store the whole function.

   ### 1) Memory Creation Phase:
   ![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/117b999f-2675-460f-9e90-94995cff6af6)

   ### Call Stack

    - Call Stack maintains the order of execution of execution context.
  
    ![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/1fc853fc-cf9f-481f-8ab3-613512856c7f)

   ###  Call Stack also known as
    ![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/ad97ccfd-f537-4d89-96fc-7c5e8d87a203)

   ### 2) Memory Creation Phase:
    ![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/efeaa276-a413-4190-b740-f8f9c543a568)

    - Once the JS code is finished then **Global Execution Context is deleted from the Call Stack**.

   ### Example 1:
    <pre>
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
    </pre>

    ### Output 1:
    <pre>
	4
	16
    </pre>
    
   ### Explanation:
    1) JavaScript will allocate memory to variables and functions.
    2) **Memory Creation Phase** - JS skims through the code and allocates memory like the above **phase 1** block.
    3) **Code Execution Phase** - JS skims through the code again and starts assigning values if any <pre>n=2</pre> is set.
    4) Square function. So, nothing to do there.
    5) Square(n) is a function invocation, **for function invocation a new sub-execution context is created**.
  
   

  

