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
