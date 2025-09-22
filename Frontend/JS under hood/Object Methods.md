# 🔑 Commonly Used JavaScript Object Methods

  

## 1. `Object.keys(obj)`

  

-   Returns an array of the **keys** of an object.

  

``` js

const user = { name: "Ali", age: 25 };

console.log(Object.keys(user)); // ["name", "age"]

```

  

------------------------------------------------------------------------

  

## 2. `Object.values(obj)`

  

-   Returns an array of the **values** of an object.

  

``` js

console.log(Object.values(user)); // ["Ali", 25]

```

  

------------------------------------------------------------------------

  

## 3. `Object.entries(obj)`

  

-   Returns an array of `[key, value]` pairs.

  

``` js

console.log(Object.entries(user));

// [["name", "Ali"], ["age", 25]]

```

  

------------------------------------------------------------------------

  

## 4. `Object.assign(target, source)`

  

-   Copies properties from one object to another.

  

``` js

const target = { a: 1 };

const source = { b: 2 };

Object.assign(target, source);

console.log(target); // { a: 1, b: 2 }

```

  

------------------------------------------------------------------------

  

## 5. `Object.freeze(obj)`

  

-   Prevents adding, deleting, or modifying properties.

  

``` js

const car = { brand: "BMW" };

Object.freeze(car);

car.brand = "Audi"; // ❌ won’t change

console.log(car.brand); // "BMW"

```

  

------------------------------------------------------------------------

  

## 6. `Object.seal(obj)`

  

-   Prevents adding/removing properties, but allows modifying existing

    ones.

  

``` js

const book = { title: "JS Guide" };

Object.seal(book);

book.title = "Advanced JS"; ✅

book.author = "Ali"; // ❌ won't be added

console.log(book); // { title: "Advanced JS" }

```

  

------------------------------------------------------------------------

  

## 7. `Object.create(proto)`

  

-   Creates a new object with the given prototype.

  

``` js

const person = { greet() { console.log("Hello!"); } };

const student = Object.create(person);

student.greet(); // "Hello!"

```

  

------------------------------------------------------------------------

  

## 8. `Object.hasOwn(obj, prop)`

  

-   Checks if the object has a specific property.

  

``` js

const user = { name: "Omar" };

console.log(Object.hasOwn(user, "name")); // true

console.log(Object.hasOwn(user, "age"));  // false

```

  

------------------------------------------------------------------------

  

#  Summary

  

-   **Inspect:** `Object.keys()`, `Object.values()`, `Object.entries()`

-   **Copy/Clone:** `Object.assign()`

-   **Locking:** `Object.freeze()`, `Object.seal()`

-   **Inheritance:** `Object.create()`

-   **Check property:** `Object.hasOwn()`