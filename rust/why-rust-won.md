Why Rust won
============

It's slightly crazy to consider that Rust has achieved the level of success that it has.
It's part of applications that are relied upon on billions such as Android, Chrome, 
Firefox and `curl`. It also sits underneath large cloud services that have a similar
reach including Microsoft Azure, AWS and Dropbox. The prospect of Rust entering the 
Linux kernel becomes more likely every month.

How did this happen? Perhaps most  importantly, how did this happen to a language that 
is **hard to learn** within a  competitive  environment with extremely strong and 
**entrenched incumbents**?


## solves some really annoying problems

Build systems

Build systems should not be as complex as the systems that they're building.
C++ code bases are difficult. `cargo` makes building pure Rust projects trivial
and hybrid projects easy.

Other ways this shines through:

- the compiler knows how to produce a test binary. Functions can be annotated with `[test]`, and they'll be run. If the function panics, the test is marked as a failure.  
- Markdown inline comments
- HTML documentation (that has direct links to the source code)
- opinionated formatter (inspired by `go fmt`, but slightly weaker). this came later, but early enough to become heavily adopted


## unapologetic about its preferences

Rust values control and precision. That provides a cognitive burden on people who are learning
the language. 


Lesson: Being difficult to learn is less useful for a language that is solving a genuine problem for its target market. (Other examples: [Futhark](https://futhark-lang.org/) (GPGPG) )


## it followed the trends

Functional programming has been on the ascendency since ~2005.

- In languages: Scala, Clojure (immutable datastructures), Erlang (now Elixir)
- In data processing: MapReduce paradigm, NoSQL more generally
- In libraries: underscore.js, ...

Unlike those languages, it couldn't use a runtime such as the JVM or BEAM. Given the intended use case (write a new web browser for multi-core)

Objects are less fashionable. Why? Objects imply hidden mutable state. Multiple inheritance also causes problems in C++. Typically 

Personal anecdote: Python's community norms changed greatly from 2005 to 2015. List/dict comprehensions, data classes, `lambda` became acceptable, methods that processed iterators became lazy (no more `.izip()`, `.imap()`).

> ### aside: data-oriented programming
> 
> We're likely to see a 

**lesson:** follow the trends

**lesson:** Rust will fall out of favour in time


## luck

ML heritage: ("Rust is a programming language where teams of Haskell and Java programmers can get along.") Lots of Rust is derived from its intial OCaml heritage. Pattern matching etc may have been a different language if its starting point was different.

LLVM: LLVM has enabled a new tranche of excellent programming languages (Julia, Swift, ...). It has dramatically reduced the cost of developing an industrial strength compiler.


## small (initial) target market

Rust was written to serve the needs of the team that was writing Rust. 
"We need a language that be used to write Servo. Firefox is too buggy, 
it's impossible to fix and we will be eaten alive by Chrome." (not quite an accurate quote)



## suited the needs of its target market

The C++ ("systems programming") crowd needed some things:

 - memory safety
 - full control over data layout (no GC)
 - fearless concurrency


## design factors

- rust is an amalgam of good ideas
- designed in conjunction with real experience in the language (Servo); early Erlang/OTP was similar
- nothing completely novel in Rust (everything that Rust has was already verified by research)  
  - no nullable pointers
  - result monad
  - maybe monad
  - no null-terminated strings
  - UTF-8 in the type system
  - expression-based
  - memory regions (lifetimes)
  - sum types (tagged unions)
  - affine types (move semantics vs copy semantics)
  - smart/fat pointers
- big audacious goal&mdash;memory safety without garbage collection&mdash;that hasn't been able 
  to be achieved by bolting on safety to other languages. consider [Cyclone], and [MiraclePtr<T>] 

### background: lifetimes

To an assembly programmer, Rust's lifetimes are understood as a guarantee that references to addresses higher in the stack

### background on other projects


**C: cylone**

> Cyclone is a language for C programmers who want to write secure, robust programs. It’s a dialect of C designed to be safe: free of crashes, buffer overflows, format string attacks, and so on. Careful C programmers can produce safe C programs, but, in practice, many C programs are unsafe. Our goal is to make all Cyclone programs safe, regardless of how carefully they were written. All Cyclone programs must pass a combination of compile-time, link-time, and run-time checks designed to ensure safety.

**C++: miracleptr**

> Chrome's biggest security problem is a constant stream of exploitable (and exploited) Use-after-Frees. Our goal is to stop them being exploitable by turning them from security bugs to non-security crashes or memory leaks.

[Cyclone]: https://cyclone.thelanguage.org/
[MiraclePtr<T>]: https://docs.google.com/document/d/1pnnOAIz_DMWDI4oIOFoMAqLnf_MZ2GsrJNb_dbQ3ZBg/edit#

## developer experience

- impossible to use its assignment operator (`=`) inside of a conditional expression
- pattern matching
- documentation/advocacy (Steve Klabnik, Carol Nichols)
- early industry buy-in (Dropbox, many others); developed in the Bay Area where are are many influential developers/companies
- welcoming community; queer-friendly

## early factors

- humble creator (Graydon Hoare), who yielded on a few key areas (actors) to create something that's focused on systems

## external factors

- underdog mentality (Mozilla vs Google)
- (largely) industry neutral
- incubated with multi-year financial support (Mozilla)
  
  
## rust gave itself time to mature
  
When Rust was publicly announced in ~2012, the language looked very different.
It was also a much bigger langauge. It contained non-nullable pointer types (in the language) a garbage.
  
Generally speaking, Rust has a very slow pace of feature development:
  
  

  
