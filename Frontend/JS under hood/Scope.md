# JavaScript Scope

## 1. Definition
**Scope** = The context in which variables are accessible.

---

## 2. Types of Scope
### 🔹 Global Scope
- Declared outside any function/block.
- Accessible everywhere.

```js
let x = 10; // Global
function print() { console.log(x); } 

```
### 🔹 Function Scope

- Variables inside a function are not accessible outside it.

```js
	function test() {
	  let y = 20; // Function scope
	}
	console.log(y); //  Error
	
	```
### 🔹 Block Scope

- `let` and `const` are limited to `{ }`.
- `var` ignores block scope.

```js
if (true) {
  let a = 5;   // Block scope
  var b = 10;  // Function/global scope
}
console.log(b); // work
console.log(a); // error

```
### 🔹 Lexical Scope

- Inner functions can access outer function variables.

```js
function outer() {
  let name = "JS";
  function inner() { console.log(name); } // work
  inner();
}

```

## 3. Key Points

- **Scope Chain**: JS looks for variables outward until global.
    
- **Closures**: Functions remember their scope even after the outer function finishes.