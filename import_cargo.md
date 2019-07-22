# Using a Crate to Get More Functionality

From [The Book](https://doc.rust-lang.org/book/ch02-00-guessing-game-tutorial.html#using-a-crate-to-get-more-functionality): 

Remember that a crate is a collection of Rust source code files. The project we’ve been building is a binary crate, which is an executable. The rand crate is a library crate, which contains code intended to be used in other programs.

Cargo’s use of external crates is where it really shines. Before we can write code that uses rand, we need to modify the Cargo.toml file to include the rand crate as a dependency. Open that file now and add the following line to the bottom beneath the [dependencies] section header that Cargo created for you:

Filename: Cargo.toml
```toml
[dependencies]

rand = "0.3.14"
```

In the Cargo.toml file, everything that follows a header is part of a section that continues until another section starts. The [dependencies] section is where you tell Cargo which external crates your project depends on and which versions of those crates you require. In this case, we’ll specify the rand crate with the semantic version specifier 0.3.14. Cargo understands Semantic Versioning (sometimes called SemVer), which is a standard for writing version numbers. The number 0.3.14 is actually shorthand for ^0.3.14, which means “any version that has a public API compatible with version 0.3.14.”