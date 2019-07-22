
# The `Hello, World!` example in Rust
`main.rs`
```rust
fn main() {
    println!("Hello, World!");
}
```
Compiling:
```
> rustc main.rs
```
generates `main.exe` on Windows and `main` on Linux or macOS
Running:
```
> .\main.exe  #Windows
$ ./main      #Linux/macOS
```

# Takeaways
 - The `main` function is the entry point of the program
 - Rust style is to indent with four spaces, not a tab
 - `println!` calls a Rust macro, not a function
 - The semicolon marks the end of an expression, but this programs compiles and execute without it. Why?
 
# Next

[The Cargo tool](cargo)
