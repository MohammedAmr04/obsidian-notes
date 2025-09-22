# JavaScript Memory & Data Types

## 1. Data Types
- **Primitive Types**: `string`, `number`, `boolean`, `null`, `undefined`, `symbol`, `bigint`  
- **Non-Primitive (Reference) Types**: `object`, `array`, `function`  

---

## 2. Memory Storage
### Primitive (Stack)
- Stored directly in the **stack**.  
- Each variable holds its own copy of the value.  
- Structure:  
### Non-Primitive (Heap + Stack)
- The **stack** stores a reference (pointer) to the **heap**.  
- The **heap** stores the actual object/array/function.  
- Structure:  
## 3. Key Concept
- **Primitive → Copy by Value**  
- **Non-Primitive → Copy by Reference**