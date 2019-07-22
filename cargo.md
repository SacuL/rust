
[Intro](#what-is-cargo) | [Creating a project](#creating-a-project-with-cargo) | [The Cargo config file](#the-cargo-configuration-file) | [Building and Running](#building-and-running-a-cargo-project) | [Takeaways](#takeaways)

# What is Cargo?

Cargo is one of Rust's main tool. It is a build system and a package manager.

# Creating a project with Cargo

```
> cargo new my_proj
```
This creates 2 files:
 -  **Cargo.toml**: Cargo configuration file
 -  **src/main.rs**: Hello world program
  
It also initialize a version control system repository, using **git** as default. In Rust 2018 three other VCS are available: hg, pijul and fossil.
If you don't want to initialize a repository you can use the `--vcs none` option.

# The Cargo configuration file

The Cargo config file format is [TOML](https://github.com/toml-lang/toml).

```toml
[package]
name = "my_proj"
version = "0.1.0"
authors = ["Your Name <you@example.com>"]
edition = "2018"

# See more keys and their definitions at https://doc.rust-lang.org/cargo/reference/manifest.html

[dependencies]
```

We will see more detailed information about the config file and its options in the next sections.

# Building and Running a Cargo Project

```
> cargo build
   Compiling my_proj v0.1.0 (...\my_proj)
    Finished dev [unoptimized + debuginfo] target(s) in 34.03s
```

This command creates an executable file in `target/debug/` directory rather than in your current directory.

```
> cargo run
   Compiling my_proj v0.1.0 (...\my_proj)
    Finished dev [unoptimized + debuginfo] target(s) in 0.61s
     Running `target\debug\my_proj.exe`
Hello, world!
```

The `cargo run` command build and execute the project.

```
> cargo check
    Checking my_proj v0.1.0 (...\my_proj)
    Finished dev [unoptimized + debuginfo] target(s) in 0.29s
```

The `cargo check` checks if the project build. It is a much faster way to check if your project compiles.

### Cargo behind proxy

If you are using a proxy, you might have to configure Cargo to work with your proxy. Instructions [here](cargo_proxy).

### The Cargo.lock file

From "[The Book](https://doc.rust-lang.org/book/ch01-03-hello-cargo.html#building-and-running-a-cargo-project)":
> Running cargo build for the first time also causes Cargo to create a new file at the top level: Cargo.lock. This file keeps track of the exact versions of dependencies in your project. This project doesn’t have dependencies, so the file is a bit sparse. You won’t ever need to change this file manually; Cargo manages its contents for you.

More info on the Cargo.lock file [here](cargo_lock).

# Takeaways
 - Create a new project with cargo: `cargo new`
 - Build using: `cargo build`
 - Check if a project compiles using `cargo check` (faster than build)
 - Build and execute using: `cargo run`
 - Build for release using: `cargo build --release`
 - [Cargo Docs](https://doc.rust-lang.org/cargo/)
