# Zero to Production in Rust

### Inner Development Loop

- Make a change
- Compile the application
- Run tests
- Run the application

### Faster Linking

`.cargo/config.toml`

```
# On MacOS, `brew install michaeleisel/zld/zld`
[target.aarch64-apple-darwin]
rustflags = ["-C", "link-arg=-fuse-ld=/usr/local/bin/zld"]
```

### cargo-watch

```
cargo install cargo-watch
```

Run `cargo check` after every file change:

```
cargo watch -x check
```

Command chaining:

```
cargo watch -x check -x test -x run
```

### Linting

```
cargo clippy
cargo clippy -- -D warnings
```

### Formatting

```
cargo fmt
cargo fmt -- --check
```

### Security Vulnerabilities

```
cargo install cargo-audit
cargo audit
```

## Dependencies

```
cargo add actix-web@4.0.0
```

List all installed:

```
cargo install --list
```

### Run

```
curl http://127.0.0.1:8000
```

## Compiler

`stable` compiler is installed by default.

To install `nightly`:

```
rustup toolchain install nightly --allow-downgrade
```

Additional tools can then be used, like `cargo expand`:

```
cargo install cargo-expand
cargo expand
```

Switch between versions:

```
rustup default nightly
rustup default stable
```

Get current version:

```
restup default
```

Use command from nightly while on stable:

```
cargo +nightly expand
```

## Test

```
curl -v http://127.0.0.1:8000/health_check
```
