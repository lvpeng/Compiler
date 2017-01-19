### How to implement a PL(programming language) in Javascript
This is a tutorial on how to implement a programming language. If you ever wrote an interperter or a compiler, then there is probably nothing new for you here.

`What are you going to learn`
* What is a parser, and how to write one.
* How to write an interpreter.
* Continuations, and why are they important.
* Write a compiler.
* How to transform code to continuations-passing style.
* A few basic optimization techniques.
* Examples of what out λanguage brings new over plain Javascript.

In between, I'm going to argue why Lisp is a great programming language. However, the language we will work on is not a Lisp. It has a richer syntax (classical infix notation that everybody knows) and will be about as powerful as Scheme, except for macros. Sadly or not, macros are the ultimate bastion of Lisp, something that other languages just can't conquer (unless they are called Lisp dialects). [Yes, I know about SweetJS… close but no cigar.]
