# JavaScript Prototype Chain

## 1. Objects
| Instance              | Prototype                | Next Prototype       |
|-----------------------|--------------------------|----------------------|
| `{}` (object literal) | `Object.prototype`       | `null`               |

 Chain:  
`{}` → `Object.prototype` → `null`

---

## 2. Arrays
| Instance      | Prototype          | Next Prototype       | Next |
|---------------|-------------------|----------------------|------|
| `[1,2,3]`     | `Array.prototype` | `Object.prototype`   | null |

 Chain:  
`[1,2,3]` → `Array.prototype` → `Object.prototype` → `null`

---

## 3. Functions
| Instance             | Prototype             | Next Prototype       | Next |
|----------------------|----------------------|----------------------|------|
| `function() {}`      | `Function.prototype` | `Object.prototype`   | null |

 Chain:  
`function(){}` → `Function.prototype` → `Object.prototype` → `null`

---

##  Key Points
- **All Arrays inherit from `Array.prototype`**, which itself inherits from `Object.prototype`.  
- **All Functions inherit from `Function.prototype`**, which also inherits from `Object.prototype`.  
- **All Objects eventually inherit from `Object.prototype`**, the root of the chain.  
- `Object.prototype` has common methods like `toString()`, `hasOwnProperty()`, etc.
