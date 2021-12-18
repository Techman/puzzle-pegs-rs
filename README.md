# Puzzle Pegs (Rust)

This is the Rust version of the [Puzzle Pegs](https://github.com/Techman/puzzle-pegs) program. I created this version specifically to compare it to the [C++](https://github.com/Techman/puzzle-pegs-cpp) version, as Rust is often compared to C++ in some online communities. There is usually a bias towards Rust, but it was enough to get me to look into the language.

This is technically the first program I have ported to Rust, so I make no claim on being proficient in the language, although I found myself liking it more and more by the end of the initial implementation.

To view details on Puzzle Pegs itself, please visit the main repository linked above.

## Build

This projects makes use of Cargo, the standard project tool for Rust.

- Use `cargo build` for building
- Use `cargo run` for running, or you can visit the `target` directory and run the debug/release executable directly.

For performance comparisons, remember to compile and run in release mode.

## Debug

Although most documentation online mentions the LLDB debugging extension for Visual Studio Code, I created configurations for using the C/C++ extension's debuggers. This is probably not supported, but it works.

1. Compile in debug mode
2. Run the debug configuration that fits your system

Some of the "fancy" display features that you might have become used to, such as being able to see the contents of a `std::vector` without having to view the underlying data, is not available when debugging the Rust versions. However, you can work around this by adding a dereference to the data pointer + an additional desired offset to the watch panel.

Example:
```rust
*((((vec_name).buf).ptr).pointer + offset)
```
With `vec_name` being the name of the Vec, and `offset` being the desired offset, such as `0`. This allows you to see a value at that address, but not the entire array.
