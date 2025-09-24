## Intro to Compilers  
### What is a compiler?  

Computers understand only one language, and that language consists of sets of instructions made of ones and zeros. This computer language is called *machine language*.  

To make programming easier, high-level languages have been developed. High-level programs also make it easier for programmers to inspect and understand each other's programs.  

Because a computer can only understand machine language and humans wish to write in high-level languages, these programs have to be translated into machine language at some point. This is done by special programs called **compilers, interpreters, or assemblers** that are built into various programming applications.  

C++ is designed to be a **compiled language**, meaning that it is generally translated into machine language that can be understood directly by the system, making the generated program highly efficient. For that, a set of tools are needed, known as the **development toolchain**, whose core are a compiler and its linker.  

---

## Compiler vs Interpreter  

| Aspect              | Compiler                                         | Interpreter                                |
|---------------------|--------------------------------------------------|--------------------------------------------|
| **Execution**       | Translates the entire program before execution   | Translates and executes line by line        |
| **Speed**           | Faster execution (already compiled)              | Slower (translation happens during runtime) |
| **Errors**          | Shows all errors after compilation               | Stops at the first error during execution   |
| **Examples**        | C, C++, Rust, Go                                 | Python, JavaScript, Ruby                    |

 **Summary:**  
- Compiled languages → usually faster, but need compilation step.  
- Interpreted languages → easier for quick testing, but slower in execution.  

## Structure of a program

The best way to learn a programming language is by writing programs. Typically, the first program beginners write is a program called "Hello World", which simply prints "Hello World" to your computer screen. Although it is very simple, it contains all the fundamental components C++ programs have:
```c++

#include <iostream>

int main(){
std::cout<<"hello world";
}

```
### Explanation:

#### 1. `#include <iostream>`

- This tells the compiler to **include the iostream library**.
    
- `iostream` provides functionality for **input/output operations**:
    
    - `std::cout` → output to the console.
        
    - `std::cin` → input from the user.
        
- Similar to **`import` in JavaScript**.
    

---

#### 2. `int main() {`

- Every C++ program starts from the **`main` function**.
    
- `int` means the function returns an **integer value** (exit code).
    
    - `0` → program finished successfully.
        
    - Any non-zero → program ended with an error.
        

---

#### 3. `std::cout << "hello world";`

- `std` → refers to the **standard namespace** (contains `cout`, `cin`, etc.).
    
- `cout` → stands for **console output**.
    
- `<<` → the **insertion operator**, sends the string into the output stream.
    
- Prints `"hello world"` to the screen.
    

---

#### 4. `}`

- Marks the **end of the `main` function**.
