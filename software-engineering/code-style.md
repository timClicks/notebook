# Principles of programming style


## When writing comments - avoid tautologies

Comments should be more informative than the code that they describe. They should pay for themselves in 
terms of overall time taken to comprehend what's being intended. Naturally it's difficult to completely 
anticipate people's level of prior knowledge. So some discretion is required. But that discretion should
err on being informative.

Respect your reader by thinking about what they need to know. 

> But I do comment sometimes. Almost exclusively, I use them as an introduction to what follows.
> Examples: explaining the use of global variables and types (the one thing I always comment in large programs); 
> as an introduction to an unusual or critical procedure; or to mark off sections of a large computation.
> 
> There is a famously bad comment style:
>
> ```plain
> i=i+1;    /* Add one to i */
> ```
> 
> and there are worse ways to do it:
> 
> ```plain
> /**********************************
> *                                 *
> *         Add one to i            *
> *                                 *
> **********************************/
> i=i+1;
> ```
> Don’t laugh now, wait until you see it in real life.

See also: Rob Pike, [_Notes on Programming in C_], p3.

[_Notes on Programming in C_]: http://www.r-5.org/files/books/computers/languages/c/style/Rob_Pike-Notes_on_Programming_in_C-EN.pdf
