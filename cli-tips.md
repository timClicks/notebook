# CLI tips

One liners and more for working on the command line:

## Free up space

Delete Rust build artifacts without cargo plugins:

```sh
find ~ -type d -name target -prune -o -name Cargo.lock -execdir cargo clean \; -print
```
