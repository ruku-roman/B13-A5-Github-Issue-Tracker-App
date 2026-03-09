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

