# JavaScript Key Points: Scope Chain & Closures

## 1. Scope Chain
- JS searches for variables **from the current scope outward**:
  1. Current (local) scope
  2. Outer scope(s)
  3. Global scope
- If not found anywhere → `ReferenceError`.

### Example:
```js
let globalVar = "I am global";

function outer() {
  let outerVar = "I am outer";

  function inner() {
    let innerVar = "I am inner";

    console.log(innerVar);  //  found in inner
    console.log(outerVar);  //  found in outer
    console.log(globalVar); //  found in global
  }

  inner();
}

outer();
```

## 2. Closures

- A **closure** happens when a function "remembers" the scope in which it was created,  
    even after the outer function has finished executing.
    
- The inner function keeps access to variables from its outer function.
    

### Example:

```js
function outer() {
  let counter = 0;

  function inner() {
    counter++;
    console.log(counter);
  }

  return inner;
}

let myFunc = outer(); // outer executes and returns inner
myFunc(); // 1
myFunc(); // 2
myFunc(); // 3

```

Here, `counter` stays alive because `inner` closes over it.

---

##  Difference

- **Scope Chain** → How JS looks up variables (search path).
    
- **Closure** → When a function preserves its scope even after the outer function ends.