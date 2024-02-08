# Episode 6: undefined vs not defined in JavaScript

## Memory Allocation Phase:

- In the first phase, JavaScript assigns each variable a placeholder called 'undefined'.
- 'Undefined' means that memory is set aside for the variable, but no value is assigned to it yet.

## Not Defined vs Undefined:

- If an object or variable is not even declared or found during the memory allocation phase, and you try to access it later in the code, it is considered 'Not Defined'.
- It's important to note that 'Not Defined' is different from 'Undefined'. 'Not Defined' means the object or variable doesn't exist at all, while 'Undefined' means the variable exists but has no value assigned to it yet.

## Undefined
- Undefined is a special keyword, separate memory is created too. It can be assigned with value in the later part of the code.
- Like a placeholder which means a memory is allocated to a variable already.

- When variable is declared but not assigned value, its current value is undefined. But when the variable itself is not declared but called in code, then it is not defined.

## Example 1:
```
console.log(a);//undefined
var a = 7;
console.log(a);//7
```

![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/676800aa-16a9-4c48-893c-a3729ad4f72b)

## Output 1:
```
undefined
7
```

![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/70620df3-1e24-42aa-9a12-470c904968ed)

## Example 2:
```
var a = "Welcome";//string
console.log(a);//Welcome
var a = 74;
console.log(a);//74
```

## Output 2:
```
Welcome
74
```

![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/79025f74-7d93-4892-a7cd-a9e3052b0199)

![image](https://github.com/ReddyDivya/rd-namaste-javaScript/assets/34181144/d82f7e2a-a6bb-4025-afd6-ab074819ecb0)

## Example 3:
```
console.log(x); // undefined
var x = 25;
console.log(x); // 25
console.log(a); // Uncaught ReferenceError: a is not defined
```

## Output 3:
```
undefined
25
Uncaught ReferenceError: a is not defined
```

- JavaScript (JS) is a loosely typed or weakly typed language.
- It doesn't restrict variables to a specific data type.
- For example, you can declare a variable like var a = 5, and later change its value to a boolean like a = true or a string like a = 'hello'.
- It's not necessary to manually assign undefined to a variable. JavaScript automatically assigns undefined to a variable when it's declared but not assigned a value.

## Not Defined
- No memory is allocated but still, we are trying to access it.

## Example 4:
```
var a = 10;
console.log(b); // Uncaught ReferenceError: b is not defined
```

## Output 4:
```
Uncaught ReferenceError: b is not defined
```

## Important Note
- Never do this, not a good programming practice.

```
a = undefined; 
```

[Watch Demo on YouTube](https://youtu.be/B7iF6G3EyIk?si=F_boPaEJN5eznYZf)
