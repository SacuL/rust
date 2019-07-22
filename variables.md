# Variables

## Declaration

Variables in Rust are declres with the `let` keyword:

```rust
let foo = bar;
```
This line creates a new variable named foo and binds it to the value of the bar variable.

## Mutability

In Rust, variables are immutable by default. To make a variable mutable use mut before the variable name:

```
let foo = 5; // immutable
let mut bar = 5; // mutable
```