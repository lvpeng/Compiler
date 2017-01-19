### Writing a parser

write a parser is a complete task , which transform a piece of code (we inspect by looking at the characters) into abstract systax tree. (AST). AST is a structured in-memory representation of program

for example:
```
sum = lambda(a, b) {
  a + b;
};
print(sum(1, 2));
```
