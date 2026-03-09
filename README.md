##1️⃣ What is the difference between var, let, and const?

**Answer:**

In JavaScript, variables can be declared using `var`, `let`, or `const`. They differ in **scope, hoisting, and mutability**.

- **`var`**
    - **Scope:** Function-scoped, meaning it is accessible throughout the function where it is declared.
    - **Hoisting:** Variables declared with `var` are hoisted to the top of their scope and initialized with `undefined`.
    - **Redeclaration & Update:** Can be redeclared and updated.
    - **Example:**
    ```javascript
    function testVar() {
        console.log(a); // undefined
        var a = 10;
        console.log(a); // 10
    }
    testVar();
    ```
- **`let`**
    - **Scope:** Block-scoped, meaning it is only accessible within the {} block.
    - **Hoisting:** Hoisted but not initialized; accessing before declaration causes a `ReferenceError.`
    - **Redeclaration & Update:** Cannot be redeclared in the same scope, but can be updated.
    - **Example:**

    ```javascript
    let x = 5;
    x = 10; // allowed
    // let x = 20; // Error: x has already been declared
    ```

- **`const`**
    - **Scope:** Block-scoped.
    - **Hoisting:** Similar to `let`.
    - **Redeclaration & Update:** Cannot be redeclared or updated. Must be initialized at the time of declaration.
    - **Example:**

    ```javascript
    const pi = 3.14;
    // pi = 3.1415; // Error: Assignment to constant variable
    ```

    - **Tip:** Use `const` by default and `let` if the variable value will change. Avoid `var` in modern JavaScript.

---

##2️⃣ What is the spread operator (...)?

**Answer:**

The **spread operator** (`...`) allows an **iterable** (like an array or object) to be expanded into individual elements. It is commonly used for **copying arrays, merging arrays, and passing multiple arguments** to functions.

- **`Array example:`**

    ```javascript
    const arr1 = [1, 2, 3];
    const arr2 = [...arr1, 4, 5]; // [1, 2, 3, 4, 5]
    ```

- **`Object example:`**

    ```javascript
    const obj1 = { a: 1, b: 2 };
    const obj2 = { ...obj1, c: 3 }; // { a: 1, b: 2, c: 3 }
    ```

- **`Function arguments example:`**

    ```javascript
    function sum(a, b, c) {
        return a + b + c;
    }
    const nums = [1, 2, 3];
    console.log(sum(...nums)); // 6
    ```

- **Tip:** Spread operator is **different from rest operator**, though both use `....`
    - **Spread:** Expands an iterable
    - **Rest:** Collects remaining elements into an array

---


##3️⃣ What is the difference between map(), filter(), and forEach()?

**Answer:**

These are array methods used for **iterating over arrays**, but they serve different purposes:

- **`map()`**
    - Creates a **new array** by applying a function to each element.
    - **Returns:** a new array
    - **Example:**

    ```javascript
    const numbers = [1, 2, 3];
    const doubled = numbers.map((num) => num * 2);
    console.log(doubled); // [2, 4, 6]
    ```

- **`filter()`**
    - Creates a **new array** containing elements that meet a condition.
    - **Returns:** a new array
    - **Example:**

    ```javascript
    const numbers = [1, 2, 3, 4];
    const evenNumbers = numbers.filter((num) => num % 2 === 0);
    console.log(evenNumbers); // [2, 4]
    ```

- **`forEach()`**
    - Executes a function for each element in the array.
    - **Does not return** a new array.
    - **Example:**

    ```javascript
    const numbers = [1, 2, 3];
    numbers.forEach((num) => console.log(num));
    // Output: 1 2 3
    ```

- **`Tip:`** Use `map` or `filter` if you want a **new array**, and `forEach` if you just want to **perform side effects.**

---

##4️⃣ What is an arrow function?

**Answer:**

Arrow functions provide a **shorter syntax** to define functions and have **lexical** `this`, meaning they inherit `this` from their parent scope.

- **`Syntax:`**

    ```javascript
    const functionName = (parameters) => expression;
    ```

- **`Examples:`**

    ```javascript
    // Single line
    const add = (a, b) => a + b;
    console.log(add(2, 3)); // 5

    // Multiple lines
    const multiply = (a, b) => {
        const result = a * b;
        return result;
    };
    console.log(multiply(2, 3)); // 6
    ```

- **`Tip:`** Avoid arrow functions for object methods if you need `this` to refer to the object.

---


##5️⃣ What are template literals?

**Answer:**

Template literals are **string literals** that allow:

- **Embedded expressions** using `${expression}`
- **Multi-line strings** without using `\n`
- Easier string concatenation

- **`Examples:`**

    ```javascript
    const name = 'Alice';
    const age = 25;

    // Embedded expressions
    const greeting = `Hello, ${name}! You are ${age} years old.`;
    console.log(greeting); // Hello, Alice! You are 25 years old.

    // Multi-line strings
    const multiline = `This is line 1
    This is line 2`;
    console.log(multiline);
    ```

- **`Tip:`** Use template literals instead of **`+`** for string concatenation to make your code cleaner and readable.

---



