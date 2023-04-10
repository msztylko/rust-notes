# The Rust Programming Language

Notes from reading [The Rust Programming Language](https://doc.rust-lang.org/book/)

## Getting Started

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

Build cargo project with `cargo build`. This creates an executable in `target/debug/hello_cargo`. Now you can the executable with `./target/debug/hello_cargo`. You can also use `cargo run` instead which will compile the code and the run the executable. 

Cargo also provides `cargo check` which quickly checks if your code compiles but doesn't produce an executable.

Why would you not want an executable? Often, `cargo check` is much faster than `cargo build` because it skips the step of producing an executable. If you’re continually checking your work while writing the code, using `cargo check` will speed up the process of letting you know if your project is still compiling! As such, many Rustaceans run cargo check periodically as they write their program to make sure it compiles. Then they run `cargo build` when they’re ready to use the executable.

#### Building for Release

When your project is finally ready for release, you can use `cargo build --release` to compile it with optimizations. This command will create an executable in *target/release* instead of *target/debug*. The optimizations make your Rust code run faster, but turning them on lengthens the time it takes for your program to compile. This is why there are two different profiles: one for development, when you want to rebuild quickly and often, and another for building the final program you’ll give to a user that won’t be rebuilt repeatedly and that will run as fast as possible. If you’re benchmarking your code’s running time, be sure to run `cargo build --release` and benchmark with the executable in *target/release*.

#### Cargo as Convention

It is common to run

```bash
$ git clone example.org/someproject
$ cd someproject
$ cargo build
```

### Rust in Jupyter Notebook

[Evcxr](https://github.com/evcxr/evcxr) allows you to run Rust in jupyter notebooks. You can easilly install it with cargo:
```bash
cargo install evcxr_jupyter
evcxr_jupyter --install
```
