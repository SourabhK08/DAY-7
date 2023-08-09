# **Assignment JavaScript quiz 4**

## _Theory_

### 1. What are anonymous functions in JavaScript?

- An anonymous function is a function that does not have a name. Instead of being defined with a specific name like regular functions.

- Anonymous functions offer a more concise way to define small functions without the need to name them explicitly, making the code more readable and concise when the function is not reused elsewhere in the code.

- Example : using a map function

```Javascript
const array = [1,2,3,4,5];

function sqaure = array.map( function(num) =>{
    return num * num;
} );

console.log(square); // OUTPUT : [1, 4, 9, 16, 25]
```

### 2. Explain strict comparison and Abstract comparison in javascript?

- **Strict comparison (' === ')** checks both the values & type equality between 2 operands and return TRUE only if both the value and type are same.

- Example :

```Javascript
5 === 5; // true (Both values and types are the same)
5 === "5"; // false (The types are different)
```

- **Abstract Comparison (' == ')** checks for value equality between 2 operands , allowing for type coercion. If the operands are of different types, JavaScript will attempt to convert one or both of the operands to the same type before making the comparison.

- Example :

```Javascript
5 == 5; // true (Both values are the same)
5 == "5"; // true (Type coercion: Number 5 is converted to a string before comparison)
5 == true; // false (Type coercion: Boolean true is converted to 1 before comparison)
```

### 3. Difference b/w arrow functions and regular functions?

| Fature | Arrow Function                                      | Regular function                                       |
| ------ | --------------------------------------------------- | ------------------------------------------------------ |
| Syntax | Declared using an arrow => with optional parameters | Decalred using the FUNCTION keyword followed by a name |

- Example of Arrow Function :

```Javascript
const arrowFunction = (parameters) => {
  // Function code here
  return result;
};
```

- Example of Regular Function :

```Javascript
function regularFunction(parameters) {
  // Function code here
  return result;
}
```

### 4. What is Hoisting in JavaScript?

- Hoisting is a behavior in JS where variable and function can be use before they are declared in the code , before the actual execution of code.

- Example 1 : Hoisting with variable declarations

```Javascript
console.log(name); // Output: undefined
var name = "Sourabh";
console.log(name); // Output: Sourabh
```

- Example 2 : Hoisting with function declarations

```Javascript
sayHello(); // Output: Hello!

function sayHello() {
  console.log("Hello!");
}
```

### 6. Explain Shallow copy vs Deep copy in Javascript?

1. Shallow copy copies references to nested objects, so changes to nested objects will affect both the original and the copy.

2. Deep copy creates completely independent copies, so changes to nested objects will not affect the copy or the original. However, deep copying can be more complex and potentially less efficient than shallow copying, especially for large and complex data structures.

### 7. What is Object.freeze

- Object.freeze is a built-in method that allows you to prevent modifications to an object. When you call Object.freeze() on an object, it makes the object "immutable", meaning you cannot add, remove, or modify its properties or values.
- Example :

```Javascript
const person = {
  name: "John",
  age: 30,
};
// Freeze the 'person' object
Object.freeze(person);
// Try to modify the 'person' object
person.name = "Alice"; // This change will be ignored
person.gender = "Male"; // This change will be ignored
console.log(person); // Output: { name: 'John', age: 30 }
```

## _Program_

### 1. Write a function that generates a random number between two ranges, -100 to 0 and 800 - 900.

```Javascript
function randomInTwoRange(min1, max1, min2, max2) {
  // Generate a random number between 0 and 1 to determine which range to use
  const rangeSelector = Math.random();

  // Choose the range based on the random selector
  let min, max;
  if (rangeSelector < 0.5) {
    min = min1;
    max = max1;
  } else {
    min = min2;
    max = max2;
  }

  // Generate and return a random number within the selected range
  return Math.floor(Math.random() * (max - min + 1)) + min;
}

// Example usage
console.log(randomInTwoRange(-100, 0, 800, 900)); // Output will be a random number within the specified ranges

```

