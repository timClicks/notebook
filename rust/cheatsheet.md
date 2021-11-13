# About

Tasks that are useful for me.

# Compiling and building your code


## Build a library crate

```console
$ cargo build --lib
```


## Build a library create within a workspace

```console
$ cargo build --package <pkg-name> --lib
```

## Build a static library on Linux

musl

```console
$ RUSTFLAGS='-C target-feature=+crt-static' cargo build --release --target x86_64-unknown-linux-musl
...
    Finished release [optimized] target(s) in 0.00s
```

glibc

```console
$ RUSTFLAGS='-C target-feature=+crt-static' cargo build --release --target x86_64-unknown-linux-gnu
...
    Finished release [optimized] target(s) in 0.00s
```
