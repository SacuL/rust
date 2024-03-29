# Cargo.lock

WORK IN PROGRESS 

The `Cargo.lock` is a file generated when you build a Rust project with Cargo for the first time.

From "[The Book](https://doc.rust-lang.org/book/ch01-03-hello-cargo.html#building-and-running-a-cargo-project)":

## Ensuring Reproducible Builds with the Cargo.lock File
> Cargo has a mechanism that ensures you can rebuild the same artifact every time you or anyone else builds your code: Cargo will use only the versions of the dependencies you specified until you indicate otherwise. For example, what happens if next week version 0.3.15 of the rand crate comes out and contains an important bug fix but also contains a regression that will break your code?

> The answer to this problem is the Cargo.lock file, which was created the first time you ran cargo build and is now in your guessing_game directory. When you build a project for the first time, Cargo figures out all the versions of the dependencies that fit the criteria and then writes them to the Cargo.lock file. When you build your project in the future, Cargo will see that the Cargo.lock file exists and use the versions specified there rather than doing all the work of figuring out versions again. This lets you have a reproducible build automatically. In other words, your project will remain at 0.3.14 until you explicitly upgrade, thanks to the Cargo.lock file.

## Updating a Crate to Get a New Version

> When you do want to update a crate, Cargo provides another command, update, which will ignore the Cargo.lock file and figure out all the latest versions that fit your specifications in Cargo.toml. If that works, Cargo will write those versions to the Cargo.lock file.

> But by default, Cargo will only look for versions greater than 0.3.0 and less than 0.4.0. If the rand crate has released two new versions, 0.3.15 and 0.4.0, you would see the following if you ran cargo update:

```shell
$ cargo update
    Updating registry `https://github.com/rust-lang/crates.io-index`
    Updating rand v0.3.14 -> v0.3.15
```
> At this point, you would also notice a change in your Cargo.lock file noting that the version of the rand crate you are now using is 0.3.15.


> If you wanted to use rand version 0.4.0 or any version in the 0.4.x series, you’d have to update the Cargo.toml file to look like this instead:

```toml
[dependencies]

rand = "0.4.0"
```
> The next time you run cargo build, Cargo will update the registry of crates available and reevaluate your rand requirements according to the new version you have specified.

> There’s a lot more to say about Cargo and its ecosystem which we’ll discuss in Chapter 14, but for now, that’s all you need to know. Cargo makes it very easy to reuse libraries, so Rustaceans are able to write smaller projects that are assembled from a number of packages.
