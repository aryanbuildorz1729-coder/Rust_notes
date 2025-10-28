# 🦀 Rust Cargo & Formatting Commands — L-18 (Oct 2, 2025)

---

## 🧰 **rustfmt**
- **`rustfmt`** is a tool that **formats Rust code** according to standard Rust style guidelines.  
- Helps keep your code **clean, readable, and consistent**.

---

## 🧱 **cargo fmt**
- **`cargo fmt`** runs `rustfmt` on your **entire project**.  
- Automatically formats all `.rs` files to follow Rust style rules.

---

## ⚙️ **cargo build**
When you type:
```bash
cargo build
```
It means:  
> “Cargo, please compile my Rust code so I can run it later.”

### 🧠 Remember These 4 Points
- 🧩 Compiles your Rust code.  
- 🏗️ Saves the compiled program in **`target/debug/`**.  
- ⚡ Used mainly for **testing and development**.  
- 🧮 Use **`cargo build --release`** for a **faster, optimized version** (for production).

---

## 🧰 **Other Useful Cargo Commands**

| Command | What It Does |
|----------|---------------|
| `cargo build` | Just builds your project. |
| `cargo run` | Builds **and runs** your project. |
| `cargo check` | Only checks for errors (faster than full build). |

---

## ⚙️ **The Two Build Modes in Cargo**

| Mode | Command | When to Use | What It Does |
|------|----------|-------------|---------------|
| 🧱 **Debug Mode** | `cargo build` | When writing or testing code | Builds fast, but runs slower. |
| 🚀 **Release Mode** | `cargo build --release` | When project is ready to share/publish | Builds slower, but runs much faster. |

🪄 **Tip:**  
> Debug mode = for learning and fixing  
> Release mode = for speed and final use  

---

## 📦 **What is crates.io?**
- **`crates.io`** is like an **app store for Rust code**.  
- A website where developers share **packages (called crates)**.  
- A *crate* = a **library or project** you can reuse.  
- Cargo automatically **downloads crates** from crates.io when you build.

Example:
```toml
# Cargo.toml
rand = "0.8"
```
Cargo will download the `rand` crate from crates.io and include it in your project.

---

## ▶️ **cargo run & Variants**

| Command | Description |
|----------|--------------|
| `cargo run` | Builds **and runs** your project (in debug mode). |
| `cargo r` | Short form for `cargo run`. |
| `cargo run --quiet` | Runs without showing intermediary build steps. |

---

## 🏗️ **cargo build vs cargo check**

| Command | Description |
|----------|--------------|
| `cargo build` | Builds the executable, but does **not** run it. |
| `cargo check` | Only checks for **errors**, doesn’t build the executable (faster). |

##🧩 Immutable vs Mutable in Rust
Concept	Description
Immutable (let)	Variables are immutable by default — their values cannot be changed after assignment.
Mutable (let mut)	To allow value changes, declare the variable with the mut keyword.
🧱 Example: Immutable Variable
fn main() {
    let x = 5;
    println!("x = {}", x);

    x = 10; // ❌ Error: cannot assign twice to immutable variable
}


🧠 Explanation:
let x = 5; makes x immutable. Trying to reassign it causes a compiler error.

🔧 Example: Mutable Variable
fn main() {
    let mut x = 5;
    println!("x = {}", x);

    x = 10; // ✅ Works fine
    println!("x = {}", x);
}


🧠 Explanation:
Adding mut allows x to change its value safely.

📜 Key Notes
Feature	Immutable	Mutable
Declaration	let x = 5;	let mut x = 5;
Can reassign?	❌ No	✅ Yes
Default behavior	Immutable	Must use mut
Benefit	Safety and predictability	Flexibility when needed

## 🧩 Variable Shadowing in Rust

### 🧠 Concept
Shadowing means **re-declaring a variable with the same name using `let`** — this creates a new variable that “shadows” (hides) the old one.

### 🧱 Mutability
Mutability controls whether a variable’s value can change, but it doesn’t affect shadowing.

### 💻 Example
```rust
fn main() {
    let grams_of_protein: &str = "100.345";
    let grams_of_protein: f64 = 100.345;
    let mut grams_of_protein: i32 = 100;

    grams_of_protein = 105;
    println!("{}", grams_of_protein);
}
```

### 🧠 What’s Happening
- `let grams_of_protein: &str = "100.345";` → A string slice is created.  
- `let grams_of_protein: f64 = 100.345;` → New variable shadows the previous one (old one is gone).  
- `let mut grams_of_protein: i32 = 100;` → Another new variable, mutable this time, shadows the f64 one.  
- `grams_of_protein = 105;` → Works fine because this last one is mutable.

### 🧱 Key Idea
> Shadowing lets you reuse the same variable name while changing its type or mutability — it’s actually creating a new variable, not modifying the old one.

---

## 🔢 Constants in Rust

### 🧩 Concept
Constants are **values that never change** during the entire program.

### 🧱 Rules
- Declared using `const`, not `let`.  
- Must always have a **type annotation**.  
- Are **always immutable** (can’t use `mut`).  
- Usually written in **UPPERCASE** by convention.

### 💻 Example
```rust
const MAX_POINTS: u32 = 100_000;
```

### 🧠 Remember
- Stored in the program’s memory at **compile time**.  
- Can be used **anywhere**, even outside functions.  
- Great for **fixed values** like limits, units, or configurations.

---

## ⚙️ Type Alias (e.g., Meters) in Rust

### 🧩 Concept
A **type alias** lets you create a new name for an existing type — like giving it a nickname.

### 💻 Example
```rust
type Meters = u32;

let distance: Meters = 50;
```

✅ Here, `Meters` is just another name for `u32`.  
It doesn’t create a new type — it just makes code more readable.

### 🧠 Why Use It
- Makes complex types easier to understand.  
- Adds meaning to numbers (like `Meters`, `Seconds`, `Kilograms`, etc.).

---

## ⚙️ Compiler Directive (Simple Explanation)

### 🧩 Concept
A **compiler directive** is a special **instruction for the compiler**, not your program.  
It tells the compiler **how to handle** or **interpret** your code.

> Think of it like a note to the compiler saying:  
> “Hey compiler, do this differently or skip this warning!”

### 💻 In Rust
Compiler directives are written as **attributes**, like:
```rust
#![allow(unused_variables)]
```
or
```rust
#[derive(Debug)]
```

### 🧠 Two Types

| Type | Example | Meaning |
|-------|----------|----------|
| **Inner attribute** | `#![...]` | Applies to the **whole file** or **crate** |
| **Outer attribute** | `#[...]` | Applies only to the **next item** (function, struct, etc.) |

---
