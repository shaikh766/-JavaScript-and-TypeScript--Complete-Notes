# -JavaScript-and-TypeScript--Complete-Notes
# JavaScript and TypeScript Complete Notes

Welcome to the **JavaScript + TypeScript Complete Notes**! This guide is designed for beginners, including those with no prior programming experience. By the end of these notes, you'll have a solid understanding of JavaScript (JS) and TypeScript (TS) fundamentals.

---

## **Table of Contents**
1. [Data Types in JavaScript and TypeScript](#data-types-in-javascript-and-typescript)
    - Primitive Types
    - Non-Primitive/Reference Types
    - Methods for Types
2. [Enum in TypeScript](#enum-in-typescript)
3. [Types in TypeScript](#types-in-typescript)
    - Why Types Were Introduced
    - Declaring and Assigning Types
4. [Core Concepts](#core-concepts)
    - Conditional Statements
    - Operators
    - Loops
5. [Functions](#functions)
    - Function Types
    - Callback Functions
6. [Advanced JavaScript](#advanced-javascript)
    - Spread and Rest Operators
    - Map, Reduce, and Filter
    - Asynchronous Programming
7. [Object-Oriented Programming (OOP)](#object-oriented-programming-oop)
    - Classes and Objects
    - Constructor
    - This and Super Keywords
    - Abstract Classes and Interfaces
8. [Generics](#generics)
9. [Exception Handling](#exception-handling)

---

## **1. Data Types in JavaScript and TypeScript**

### **Primitive Types**
Primitive types are the most basic data types in JavaScript and TypeScript. These include:
- **String**
- **Number**
- **Boolean**
- **Null**
- **Undefined**
- **Symbol** (ES6)
- **BigInt** (ES11)

### **Examples:**
```javascript
// String
let name = "John Doe";
console.log(typeof name); // Output: string

// Number
let age = 25;
console.log(typeof age); // Output: number

// Boolean
let isStudent = true;
console.log(typeof isStudent); // Output: boolean

// Null
let emptyValue = null;
console.log(typeof emptyValue); // Output: object

// Undefined
let uninitialized;
console.log(typeof uninitialized); // Output: undefined

// Symbol
let uniqueId = Symbol("id");
console.log(typeof uniqueId); // Output: symbol

// BigInt
let largeNumber = 12345678901234567890n;
console.log(typeof largeNumber); // Output: bigint
```

### **Non-Primitive/Reference Types**
Reference types include:
- **Object**
- **Array**
- **Function**

### **Examples:**
#### Object
```javascript
let person = {
    name: "Alice",
    age: 30,
    isEmployed: true
};
console.log(person.name); // Output: Alice
```

#### Array
```javascript
let fruits = ["Apple", "Banana", "Cherry"];
console.log(fruits[1]); // Output: Banana
```

#### Function
```javascript
function greet(name) {
    return `Hello, ${name}!`;
}
console.log(greet("Alice")); // Output: Hello, Alice!
```

### **Methods for Data Types**
#### **String Methods**
```javascript
let str = "Hello, World!";
console.log(str.toLowerCase()); // hello, world!
console.log(str.toUpperCase()); // HELLO, WORLD!
console.log(str.includes("World")); // true
console.log(str.split(", ")); // [ 'Hello', 'World!' ]
```

#### **Number Methods**
```javascript
let num = 123.456;
console.log(num.toFixed(2)); // 123.46
console.log(num.toString()); // "123.456"
console.log(Number.isInteger(num)); // false
```

#### **Array Methods**
```javascript
let arr = [1, 2, 3, 4, 5];
console.log(arr.push(6)); // Adds 6, Output: 6
console.log(arr.pop()); // Removes last element, Output: 6
console.log(arr.slice(1, 3)); // [2, 3]
console.log(arr.map(x => x * 2)); // [2, 4, 6, 8, 10]
```

#### **Object Methods**
```javascript
let obj = { a: 1, b: 2, c: 3 };
console.log(Object.keys(obj)); // [ 'a', 'b', 'c' ]
console.log(Object.values(obj)); // [ 1, 2, 3 ]
console.log(Object.entries(obj)); // [ ['a', 1], ['b', 2], ['c', 3] ]
```

---

## **2. Enum in TypeScript**
Enums are a feature of TypeScript that allow defining a set of named constants.

### **Example:**
```typescript
enum Color {
    Red = 1,
    Green,
    Blue
}
let c: Color = Color.Green;
console.log(c); // Output: 2
```

### **Why Use Enums?**
- Provide meaningful names to numeric values.
- Help reduce errors by using predefined constants.

---

## **3. Types in TypeScript**

### **Why Types Were Introduced**
Types provide static type-checking, reducing runtime errors and improving code quality.

### **Declaring and Assigning Types**
#### **Basic Types:**
```typescript
let isActive: boolean = true;
let total: number = 100;
let name: string = "Alice";
```

#### **Array Types:**
```typescript
let numbers: number[] = [1, 2, 3];
let strings: Array<string> = ["a", "b", "c"];
```

#### **Tuple Types:**
```typescript
let tuple: [string, number] = ["Alice", 25];
```

#### **Union Types:**
```typescript
let mixed: string | number;
mixed = "Hello";
mixed = 42;
```

#### **Type Aliases:**
```typescript
type ID = string | number;
let userId: ID = "abc123";
```

---

## **4. Core Concepts**

### **Conditional Statements**
Conditional statements control the flow of execution based on conditions.

#### **Examples:**
```javascript
let age = 18;
if (age >= 18) {
    console.log("You are an adult.");
} else {
    console.log("You are a minor.");
}

let day = "Monday";
switch (day) {
    case "Monday":
        console.log("Start of the workweek.");
        break;
    case "Friday":
        console.log("End of the workweek.");
        break;
    default:
        console.log("It's a regular day.");
}
```

### **Operators**
Operators perform operations on variables and values.

#### **Types of Operators:**
1. **Arithmetic Operators:** `+`, `-`, `*`, `/`, `%`
2. **Comparison Operators:** `==`, `===`, `!=`, `!==`, `<`, `>`, `<=`, `>=`
3. **Logical Operators:** `&&`, `||`, `!`
4. **Assignment Operators:** `=`, `+=`, `-=`, `*=`, `/=`, `%=`

#### **Examples:**
```javascript
let x = 10;
let y = 5;
console.log(x + y); // 15
console.log(x > y && y > 0); // true
console.log(x === "10"); // false (strict equality)
```

### **Loops**
Loops allow you to execute a block of code multiple times.

#### **Types of Loops:**
1. **For Loop**
   ```javascript
   for (let i = 0; i < 5; i++) {
       console.log(i);
   }
   ```

2. **While Loop**
   ```javascript
   let i = 0;
   while (i < 5) {
       console.log(i);
       i++;
   }
   ```

3. **Do-While Loop**
   ```javascript
   let i = 0;
   do {
       console.log(i);
       i++;
   } while (i < 5);
   ```

---

### 5. Functions and Their Types

Functions are reusable blocks of code that can be executed when called. They allow us to write code once and use it multiple times.

#### Basic Function Syntax:
```javascript
function greet(name) {
    return `Hello, ${name}!`;
}

console.log(greet("Alice")); // Output: Hello, Alice!
```

#### Function Types:
There are different types of functions:

1. **Regular Functions:**
   Functions that can be called multiple times.

   ```javascript
   function add(x, y) {
       return x + y;
   }

   console.log(add(5, 3)); // Output: 8
   ```

2. **Anonymous Functions:**
   Functions without a name, often used for passing as arguments or storing in variables.

   ```javascript
   let multiply = function(x, y) {
       return x * y;
   };
   console.log(multiply(2, 3)); // Output: 6
   ```

3. **Arrow Functions:**
   Shorter syntax for writing functions, using the `=>` syntax.

   ```javascript
   const subtract = (x, y) => x - y;
   console.log(subtract(10, 5)); // Output: 5
   ```

####  Function with Return and Without Return
- **With Return:**
   ```javascript
   function square(x) {
       return x * x;
   }
   console.log(square(4)); // Output: 16
   ```

- **Without Return:**
   ```javascript
   function sayHello() {
       console.log("Hello, World!");
   }
   sayHello(); // Output: Hello, World!
   ```

---

### 6. Callback Functions

A **callback function** is a function passed as an argument to another function and is executed after the completion of that function.

#### Example:
```javascript
function fetchData(callback) {
    let data = "Hello, Data!";
    callback(data);
}

function displayData(data) {
    console.log(data); // Output: Hello, Data!
}

fetchData(displayData);
```

In this example, `displayData` is the callback function, and it's executed once `fetchData` completes its task.

---

### 7. Advanced JavaScript Concepts

#### Spread and Rest Operators

The **spread operator (`...`)** is used to spread elements of an array or object into another array or object. The **rest operator** is used to collect multiple elements into a single variable.

- **Spread Operator Example:**
   ```javascript
   let arr1 = [1, 2, 3];
   let arr2 = [...arr1, 4, 5]; // Output: [1, 2, 3, 4, 5]
   ```

- **Rest Operator Example:**
   ```javascript
   function sum(...numbers) {
       return numbers.reduce((total, num) => total + num, 0);
   }
   console.log(sum(1, 2, 3, 4)); // Output: 10
   ```

#### Map, Reduce, and Filter

These are higher-order functions used for manipulating arrays.

- **Map:** Creates a new array with the results of calling a provided function on every element in the array.
   ```javascript
   let numbers = [1, 2, 3];
   let squaredNumbers = numbers.map(num => num * num); // Output: [1, 4, 9]
   ```

- **Filter:** Creates a new array with all elements that pass the test implemented by the provided function.
   ```javascript
   let numbers = [1, 2, 3, 4, 5];
   let evenNumbers = numbers.filter(num => num % 2 === 0); // Output: [2, 4]
   ```

- **Reduce:** Executes a reducer function (on each element) to reduce the array to a single value.
   ```javascript
   let numbers = [1, 2, 3];
   let sum = numbers.reduce((total, num) => total + num, 0); // Output: 6
   ```

---

### 8. Asynchronous Programming (Async/Await)

Asynchronous programming allows for tasks to run independently without blocking the main thread, often used for tasks like fetching data from an API.

#### Example using `async` and `await`:
```javascript
async function fetchData() {
    let response = await fetch("https://api.example.com/data");
    let data = await response.json();
    console.log(data);
}

fetchData();
```

Here, the `await` keyword waits for the promise (fetch operation) to resolve before continuing with the next lines of code.

---

Sure! Here's the content for **Object-Oriented Programming (OOP)**, including the following topics:

---

## 8. Object-Oriented Programming (OOP)

Object-Oriented Programming (OOP) is a programming paradigm that organizes software design around data, or objects, rather than functions and logic. Objects represent real-world entities, and classes are blueprints for creating objects.

### Key Concepts in OOP:
- **Classes and Objects**
- **Constructor**
- **This and Super Keywords**
- **Abstract Classes and Interfaces**
- **Generics**
- **Exception Handling**

---

### 8.1. Classes and Objects

A **class** is a blueprint for creating objects. It defines properties (attributes) and methods (functions) that the objects created from the class will have. 

An **object** is an instance of a class. It has the properties and methods defined in the class.

#### Example: Creating a Class and Object in JavaScript

```javascript
class Person {
    constructor(name, age) {
        this.name = name;  // Property
        this.age = age;    // Property
    }

    greet() {  // Method
        console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
    }
}

// Creating an object of the Person class
let person1 = new Person("Alice", 25);
person1.greet();  // Output: Hello, my name is Alice and I am 25 years old.
```

In this example:
- `Person` is a class.
- `person1` is an object of the `Person` class.

---

### 8.2. Constructor

A **constructor** is a special method used to initialize objects. It’s called when an object is created from a class. 

#### Example: Constructor in JavaScript

```javascript
class Car {
    constructor(make, model, year) {
        this.make = make;
        this.model = model;
        this.year = year;
    }

    displayInfo() {
        console.log(`${this.year} ${this.make} ${this.model}`);
    }
}

let car1 = new Car("Toyota", "Corolla", 2021);
car1.displayInfo();  // Output: 2021 Toyota Corolla
```

The `constructor` method is called automatically when a new instance of the `Car` class is created.

---

### 8.3. `this` and `super` Keywords

- **`this`**: Refers to the current object. It is used to access the properties and methods of the current object.
- **`super`**: Refers to the parent class. It is used to call methods or constructors of the parent class.

#### Example: `this` and `super` Keywords in JavaScript

```javascript
class Animal {
    constructor(name) {
        this.name = name;
    }

    speak() {
        console.log(`${this.name} makes a sound.`);
    }
}

class Dog extends Animal {
    constructor(name, breed) {
        super(name);  // Calls the parent class constructor
        this.breed = breed;
    }

    speak() {
        super.speak();  // Calls the parent class speak method
        console.log(`${this.name} barks.`);
    }
}

let dog1 = new Dog("Max", "Labrador");
dog1.speak();
// Output:
// Max makes a sound.
// Max barks.
```

In this example:
- `super(name)` calls the constructor of the `Animal` class.
- `super.speak()` calls the `speak()` method of the `Animal` class.

---

### 8.4. Abstract Classes and Interfaces

- **Abstract Class**: A class that cannot be instantiated directly and must be inherited by another class. It may contain abstract methods (methods without implementation).
- **Interface**: A structure that defines the contract for a class, without providing the implementation.

#### Example: Abstract Class and Interface in JavaScript (Using TypeScript)

```typescript
// Abstract Class
abstract class Animal {
    abstract speak(): void;  // Abstract method
}

class Dog extends Animal {
    speak() {
        console.log("Woof!");
    }
}

let dog = new Dog();
dog.speak();  // Output: Woof!

// Interface
interface Flyable {
    fly(): void;
}

class Bird implements Flyable {
    fly() {
        console.log("Flying high!");
    }
}

let bird = new Bird();
bird.fly();  // Output: Flying high!
```

In this example:
- The `Animal` class is abstract and cannot be instantiated directly.
- The `Dog` class inherits from `Animal` and implements the `speak()` method.
- The `Flyable` interface defines a `fly()` method, which is implemented by the `Bird` class.

---

### 8.5. Generics

Generics allow you to write code that works with any data type while maintaining type safety. In TypeScript, generics can be used in functions, classes, and interfaces.

#### Example: Generics in TypeScript

```typescript
// Generic Function
function identity<T>(arg: T): T {
    return arg;
}

let numberIdentity = identity(5);  // Works with a number
let stringIdentity = identity("Hello");  // Works with a string

// Generic Class
class Box<T> {
    value: T;

    constructor(value: T) {
        this.value = value;
    }

    getValue(): T {
        return this.value;
    }
}

let numberBox = new Box(10);
console.log(numberBox.getValue());  // Output: 10

let stringBox = new Box("Hello");
console.log(stringBox.getValue());  // Output: Hello
```

In this example:
- The `identity` function uses a generic type `T`.
- The `Box` class uses a generic type `T` for the `value` property.

---

### 8.6. Exception Handling

Exception handling allows you to manage errors in a controlled way using `try`, `catch`, and `finally` blocks.

#### Example: Exception Handling in JavaScript

```javascript
try {
    let result = 10 / 0;  // This will cause an error (divide by zero)
    console.log(result);
} catch (error) {
    console.log("An error occurred: " + error.message);  // Catch the error
} finally {
    console.log("Execution completed.");  // Always executes
}
```

In this example:
- The `try` block contains code that may throw an error.
- The `catch` block handles any errors that occur.
- The `finally` block always executes, regardless of whether an error occurred.

---

### Summary

- **Classes and Objects**: Fundamental concepts for structuring data and behavior.
- **Constructor**: Special method for initializing objects.
- **`this` and `super`**: Used for accessing the current object and parent class.
- **Abstract Classes and Interfaces**: Enable polymorphism and code flexibility.
- **Generics**: Provide type safety while working with different data types.
- **Exception Handling**: Manages runtime errors gracefully.

---

