Although Rust has a robust Result type for error handling, it is not universally applicable. 
The `std::panic::catch_unwind` function can be used to implement a form of exception handling within Rust. 
It executes a closure and returns an Error with the cause of the "unwinding panic" if one occurs. 
Which statement best describes the phrase "unwinding panic"?

> Unwinding is a metaphor that refers to traversing the stack frame, which is a hidden data structure 
> set up by the programming language (inherited from the C ABI) for how function's call and return from
> one another.
>
> _TODO: finish


What is the responsibilities of the owner of a value?	

> Drop the value at the end of its scope.
