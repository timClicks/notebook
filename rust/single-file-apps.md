Let's enable single `app.rs` file would be able to declare its own dependencies.

As a starting point for discussion, what about extending string literals with a new type that refers to dependencies?

```rust
use dep"crates.io/fastrand";

fn main() {
  if fastrand::bool() {
    println!("heads");
  } else {
    println!("tails");
  }
}
```

My motivation is making things easier for beginners. Beginners don't want to have to learn
`cargo`, TOML, `Cargo.toml` _and_ Rust. They just want to learn Rust. Every layer of cognitive
complexity that we can reduce from a beginner's experience will benefit the entire community.

It would also enable programming-in-the-small. Enabling single-file applications would reduce 
friction for people who want to prototype in Rust.

What do you think? Feel free to use [Twitter](https://twitter.com/timClicks) to discuss the idea.
Is this worth creating a bona fide RFC[1] for?

<!-- Rust doesn't have random number generation within the standard library. That makes building
trivial games difficult.

This would be a big change. It would  `rustc` with the capability to download and include packages 
from crates.io and elsewhere. This would remove some of the bureaucrazy needed when programing
with Rust for small things.
 -->



---

1. As an aside, isn't it strange that an RFC ("Request for Comments") isn't used to request comments?

1. <a id="footnote-1" name="footnote-1"></a>Yes, and also `#[no_core]`, I supposee.
