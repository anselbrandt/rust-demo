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

### Run
```
curl http://127.0.0.1:8000
```