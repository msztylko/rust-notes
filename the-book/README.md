# The Rust Programming Language

Notes from reading [The Rust Programming Language](https://doc.rust-lang.org/book/)

### Installing Rust on MacOS

Use `rustup` for managing Rust versions and follow [Installing rustup on Linux or macOS](https://doc.rust-lang.org/book/ch01-01-installation.html#installing-rustup-on-linux-or-macos)

### [Hello, World!](https://doc.rust-lang.org/book/ch01-02-hello-world.html#hello-world)

```rust
fn main() {
    println!("Hello, World!");
}
```

`main` is always the first code that runs in every executable Rust program.  
`println!` is a Rust macro. `!` means that you're calling a macro instead of a normal function.

Rust is an ahead-of-time compiled language, meaning you can compile a program and give the executable to someone else, and they can run it even without having Rust installed.

### [Cargo](https://doc.rust-lang.org/book/ch01-03-hello-cargo.html#hello-cargo)

Cargo is Rust’s build system and package manager.

Create new project with cargo `cargo new hello_cargo`. This creates 2 files:
 - `Cargo.toml` - configuration file
 - `src/main.rs`
 
 `Cargo.toml`
 ```toml
 [package]
name = "hello_cargo"
version = "0.1.0"
edition = "2021"

# See more keys and their definitions at https://doc.rust-lang.org/cargo/reference/manifest.html

[dependencies]
 ```

In Rust, packages of code are referred to as **crates**. 

Cargo expects your source files to live inside the src directory. The top-level project directory is just for README files, license information, configuration files, and anything else not related to your code.

Build cargo project with `cargo build`. This creates an executable in `target/debug/hello_cargo`
