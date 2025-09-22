


## 1. What is `this`?

  

-   `this` is a **special keyword** in JavaScript.

-   Its value depends on **how** (not where) the function is called.

  

------------------------------------------------------------------------

  

## 2. Different Scenarios

  

### A. Global Scope

  

``` js

console.log(this);

```

  

-   **Browser** → `window`

-   **Node.js** → `{}` (empty object in modules)

  

------------------------------------------------------------------------

  

### B. Inside a Function

  

``` js

function show() {

  console.log(this);

}

show();

```

  

-   **Non-strict mode** → global object (window in browser)

-   **Strict mode** → `undefined`

  

------------------------------------------------------------------------

  

### C. Inside an Object Method

  

``` js

const user = {

  name: "Ali",

  greet: function() {

    console.log(this.name);

  }

};

user.greet(); // "Ali"

```

  

-   `this` refers to the object that owns the method.

  

------------------------------------------------------------------------

  

### D. Arrow Functions

  

``` js

const user = {

  name: "Ali",

  greet: () => {

    console.log(this.name);

  }

};

user.greet(); // (undefined in strict mode ) (window in non-strict mode )

```

  

-   Arrow functions **don't have their own `this`**.

-   They inherit `this` from their surrounding lexical scope.

  

------------------------------------------------------------------------

  

## 3. Controlling `this`: `call`, `apply`, `bind`

  

### A. `call()`

  

-   Calls a function **immediately** with a specific `this`.

-   Arguments are passed **one by one**.

  

``` js

function greet(greeting, punctuation) {

  console.log(greeting + " " + this.name + punctuation);

}

  

const person = { name: "Omar" };

  

greet.call(person, "Hello", "!");

// Hello Omar!

```

  

------------------------------------------------------------------------

  

### B. `apply()`

  

-   Similar to `call()`, but arguments are passed as an **array**.

  

``` js

greet.apply(person, ["Hi", "!!"]);

// Hi Omar!!

```

  

------------------------------------------------------------------------

  

### C. `bind()`

  

-   Returns a **new function** with `this` permanently set.

-   Does **not execute immediately**.

  

``` js

const boundGreet = greet.bind(person, "Hey");

boundGreet("?");

// Hey Omar?

```

  

------------------------------------------------------------------------

  

### D. Comparison Table

  

  Method    Calls Immediately?   How to Pass Arguments

  --------- -------------------- ----------------------------

  `call`    ✅ Yes               List (`arg1, arg2, ...`)

  `apply`   ✅ Yes               Array (`[arg1, arg2]`)

  `bind`    ❌ No                List when binding or later

  

------------------------------------------------------------------------

  

## 4. Key Takeaways

  

-   `this` depends on **HOW** a function is called.

-   In objects → refers to the object itself.

-   In normal functions → global object (or `undefined` in strict mode).

-   In arrow functions → takes `this` from the outer scope.

-   Use **`call` / `apply`** to invoke immediately with custom `this`.

-   Use **`bind`** to create a function with fixed `this` (useful in

    callbacks).