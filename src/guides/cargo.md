# Cargo: Rust's Package Manager

Cargo is the official package manager and build tool for Rust. It handles many tasks such as building your code, downloading dependencies, and building those dependencies.

## Creating a New Project

To create a new Rust project:

```bash
cargo new your_project_name
```

For a library project:

```bash
cargo new --lib your_project_name
```

## Building and Running

Build your project:

```bash
cargo build
```

Run your project:

```bash
cargo run
```

## Other Useful Commands

- Check for errors: `cargo check`
- Run tests: `cargo test`
- Generate documentation: `cargo doc`
- Update dependencies: `cargo update`

## Cargo.toml

The `Cargo.toml` file in your project root is the manifest where you can specify:

- Project metadata
- Dependencies
- Build settings

Example:

```toml
[package]
name = "your_project_name"
version = "0.1.0"
authors = ["Your Name <you@example.com>"]
edition = "2018"

[dependencies]
serde = "1.0"
```

Remember to run `cargo build` after modifying your `Cargo.toml` to download and compile new dependencies.
