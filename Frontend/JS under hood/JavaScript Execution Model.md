
## 1. Single Thread
- JavaScript is **single-threaded** → one **Call Stack** only.
- Executes **one task at a time** (synchronously).

---

## 2. Call Stack
- Holds function calls in **LIFO** (Last In, First Out).
- Example:
```js
function a() { b(); }
function b() { console.log("Hello"); }
a();
```

 Stack sequence: `a()` → `b()` → `console.log` → pop → pop → pop.

## 3. Event Loop

- The **Event Loop** constantly checks:
    
    1. Is the **Call Stack empty**?
        
    2. If yes → take the next task from a queue and push it into the stack.
        
- Keeps the program running smoothly.

## 4. Callback Queue (Macro-task Queue)

- Stores async tasks like:
    
    - `setTimeout`, `setInterval`
        
    - DOM events (click, input, etc.)
        
    - AJAX callbacks
        
- Tasks here wait until the stack is free.

## 5. Job Queue (Microtask Queue)

- Special queue for:
    
    - `Promises`
        
    - `MutationObserver` (Dom changes)
        
- **Higher priority** than Callback Queue.
    
- Event Loop always clears **all microtasks first** before moving to macro-tasks.

## Example
```js
console.log("Start");

setTimeout(() => {
  console.log("Timeout"); // Callback Queue (macro-task)
}, 0);

Promise.resolve().then(() => {
  console.log("Promise"); // Job Queue (micro-task) (more priority)
});

console.log("End");

```

Output: Start --> End -->Promise --> Timeout

##  Key Points

- **Single Thread** → executes one thing at a time.
    
- **Call Stack** → current running tasks.
    
- **Event Loop** → moves tasks from queues to stack.
    
- **Job Queue (Microtasks)** → Promises → executed **before** Callback Queue.
    
- **Callback Queue (Macro-tasks)** → Timers, events, I/O callbacks.