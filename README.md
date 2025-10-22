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
