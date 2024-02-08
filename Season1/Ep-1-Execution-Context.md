# Episode 1: How JavaScript Works?


JavaScript is a synchronous single-threaded language which means runs one command at a time and in a specific order.

## Execution Context

- Everything in JavaScript happens inside the execution context. This means that whenever JavaScript code is running, it's always happening within something called an `execution context`. Think of it like a framework or environment where JS code operates.

- Imagine a sealed-off container inside which JS runs. Picture a closed box or container. Inside this container is where all the JavaScript code is running. It's like a closed-off space where the code does its work without directly interacting with anything outside of it.

- Whenever we run a JavaScript code an Execution context is created.

- This `execution context` is a bit of a theoretical idea. It's not a physical thing you can see or touch; it's more of a concept used to understand how JS operates. Inside this `container`, there's information about the environment in which the code is running. This could include things like `variables`, `functions`, and `other data that the code needs to work with`.

- So, in simpler terms, the line is saying that when JavaScript code runs, it's like it's running inside a closed container called the `execution context`, which holds all the information the code needs to do its job within the environment it's running in.

  ![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/97adc821-e2b9-4624-8dcd-ed9a5df590ab)

- Execution context is created in 2 phases i.e. 1) **Memory Component** and 2) **Code Component**.

![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/2bd92772-393c-4532-b8fc-d6ba8cf63a89)

- `Memory component` has all the variables and functions in key-value pairs. It is also called a `Variable environment`.
- `Code component` is the place where code is executed one line at a time. It is also called the `Thread of Execution`.
- JS is a synchronous, single-threaded language.
    - `Synchronous`: In a specific synchronous order.
    - `Single-threaded`: One command at a time.

![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/8547c219-a6da-4ea5-85cd-e34ffbe429af)

### Watch it live on YouTube
[Namaste JavaScript Ep.1](https://youtu.be/ZvbzSrg0afE?si=GdtGaPDCRo31UbdC)
