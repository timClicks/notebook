Sometimes you don't need the temporary variable. That is, you don't need to
`.collect()` items into a temporary `Vec<T>`.

```rust
let text = "hello, I am some content.";
let words: Vec<_> = text.split_whitespace().collect();

for word in words.iter() {
  // ...
}
```

Often it's possible to refactor your code to keep things as the iterator. 

```rust
let text = "hello, I am some content.";
let words = text.split_whitespace();

for word in words {
  // ...
}
```
