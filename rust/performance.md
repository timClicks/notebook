## Closures can be inlined

```rust
let f =  #[inline(always)] |a| {  /* ... */  };

f()
```
