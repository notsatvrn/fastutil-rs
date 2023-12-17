# `fastutil-rs`

Fast utilities and optimizations for Rust.

`fastutil-rs` is a convenience crate that wraps around other crates to provide faster, or otherwise useful replacements for common things in Rust, like collections, random number generators, etc.

## Features

- `no_std` and WASM support
- 100% safe

## Optional Features

- **`std`** uses the Rust standard library to provide collections
- **`alloc`** uses alloc + [`hashbrown`](https://crates.io/crates/hashbrown) to provide collections
- **`hash` (default)** provides a fast platform-based hashing algorithm
  - [`gxhash`](https://crates.io/crates/gxhash) only works on `x86-64` and `aarch64`.
  - Falls back to [`zwohash`](https://crates.io/crates/zwohash) on other systems.
- **[`indexmap`](https://crates.io/crates/indexmap) (default)** provides a `HashMap` and `HashSet` that keeps insertion order
- **[`multimap`](https://crates.io/crates/multimap) (`std` only)** provides a `HashMap` which stores multiple values
- **`rand` (default)** provides minimal RNG implementations from [`smolcrush`](https://crates.io/crates/smolcrush)
- **[`serde`](https://crates.io/crates/serde)** enables (de)serialization of collections
- **`nightly`** provides nightly-only optimizations
  - `likely` and `unlikely` can be wrapped around conditions to help the compiler optimize if statements based on the likelihood of them being true.
  - This also enables nightly optimizations for `hashbrown` if `alloc` is being used.

## **M**inimum **S**upported **R**ust **V**ersion (MSRV)

The current MSRV is 1.63.0.