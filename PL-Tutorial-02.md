### Informal description of the λanguage

Before anything, we should have a clear picture about what we're trying to achieve. It's a good idea to put together a rigorous description of the grammar, but I'm going to keep things more informal in this tutorial, so here is the λanguage by examples:

```
# this is a comment

println("Hello World!");

println(2 + 3 * 4);

# functions are introduced with `lambda` or `λ`
fib = lambda (n) if n < 2 then n else fib(n - 1) + fib(n - 2);

println(fib(15));

print-range = λ(a, b)             # `λ` is synonym to `lambda`
                if a <= b then {  # `then` here is optional as you can see below
                  print(a);
                  if a + 1 <= b {
                    print(", ");
                    print-range(a + 1, b);
                  } else println("");        # newline
                };
print-range(1, 5);
```
```
Hello World!
14
610
1, 2, 3, 4, 5
```

Note above that identifier names can contain the minus character (print-range). That's a matter of personal taste: I always put spaces around operators, I don't like much camelCaseNames and the dash is nicer than the underscore. The nice thing about writing your own language is that you can do it as you like it. :)

```
a = {
  fib(10);  # has no side-effects, but it's computed anyway
  fib(15)   # the last semicolon can be missing
};
print(a); # prints 610
```

Functions are introduced with one of the keywords lambda or λ (they are synonyms). After the keyword there must be a (possibly empty) parenthesized list of variable names separated with commas, like in JavaScript — these are the argument names. The function body is a single expression, but it can be a sequence wrapped in {…}. There is no return statement (there are no statements) — the last expression evaluated in a function gives the value to return to its caller.
