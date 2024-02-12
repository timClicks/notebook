# About

Tasks that are useful for me.

# Compiling and building your code


## Build a library crate

```console
$ cargo build --lib
```

## Free up disk space

Search for `target` directories and invoke `cargo clean` in their parent.

```console
find ~ -type d -name target -exec sh -c 'cd {} && cd .. && cargo clean' \
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

# Workflow

Speed up tool downloads by using `cargo binstall` rather than `cargo install`. [`cargo-binstall`](https://github.com/cargo-bins/cargo-binstall) installs pre-built binary packages, rather than requiring you to compile everything from source.

```console
$ cargo install cargo-binstall
```

# Raw pointers

## Creating a C `* char` string

I think this is the least ugly way to create a C-compatible string in Rust. It's also possible to create the same via the `std::ffi` module. 

```rust
b"some text\0".as_ptr() as *const i8
```
## Deallocating a raw pointer

If you need to do the equivalent of `free()`, then there's a slight trick available to you. Instead of calling `free()` directly, you can use `Box::from_raw()` that will be freed at the end of its scope. 

I guess if you wanted to, you could simply call `free()` yourself:

```rust
extern crate libc;

use std::mem;

unsafe {
    let my_num: *mut i32 = libc::malloc(mem::size_of::<i32>()) as *mut i32;
    if my_num.is_null() {
        panic!("failed to allocate memory");
    }
    libc::free(my_num as *mut libc::c_void);
}
```

See also https://eli.thegreenplace.net/2021/rust-data-structures-with-circular-references/
