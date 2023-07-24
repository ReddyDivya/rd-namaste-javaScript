# Episode 1: How JavaScript Works?

JavaScript is a synchronous single-threaded language which means runs one command at a time and in a specific order.

## Execution Context

- Everything in JavaScript happens inside the execution context.
  
  ![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/97adc821-e2b9-4624-8dcd-ed9a5df590ab)

- Whenever we run a JavaScript code an Execution context is created.
- Execution context is created in 2 phases i.e. 1) **Memory Component** and 2) **Code Component**.

  ![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/8547c219-a6da-4ea5-85cd-e34ffbe429af)

## What happens when we run a JS Code?

- An Execution Context is created while running JS Code.
- In the Execution Context - there are 2 phases
	- **Memory Creation** phase where it skims through every line of code and stores them as a **key-value pair in the Memory block(Variable Environment)**.
	- Variables are stored as undefined at the beginning.
	- Functions store the whole function.
   ![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/117b999f-2675-460f-9e90-94995cff6af6)

## Call Stack

- Call Stack maintains the order of execution of execution context.
  
  ![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/1fc853fc-cf9f-481f-8ab3-613512856c7f)
