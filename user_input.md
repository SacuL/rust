# Reading user input

To read standard input In Rust we call `std::io::stdin` and `read_line`. 

## Example

```rust
use std::io;

fn main() {
    let mut uinput = String::new();

    io::stdin().read_line(&mut uinput)
        .expect("Failed to read line");

}
```
