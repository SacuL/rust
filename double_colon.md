# The double colon (`::`)

In Rust, the `::` syntax indicates an associated function. An associated function is implemented on a type rather than on a particular instance. Some languages call this a static method.

## Example

```rust
let mut texto = String::new();
```

The `::new` indicates that `new` is an associated function of the String type.
