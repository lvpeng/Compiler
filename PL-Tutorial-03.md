### Writing a parser

write a parser is a complete task , which transform a piece of code (we inspect by looking at the characters) into abstract systax tree. (AST). AST is a structured in-memory representation of program

for example:
```
sum = lambda(a, b) {
  a + b;
};
print(sum(1, 2));
```

our parser will generate the following AST, as a JavaScript object:

```
{
  type: "prog",
  prog: [
    // first line:
    {
      type: "assign",
      operator: "=",
      left: { type: "var", value: "sum" },
      right: {
        type: "lambda",
        vars: [ "a", "b" ],
        body: {
          // the body should be a "prog", but because
          // it contains a single expression, our parser
          // reduces it to the expression itself.
          type: "binary",
          operator: "+",
          left: { type: "var", value: "a" },
          right: { type: "var", value: "b" }
        }
      }
    },
    // second line:
    {
      type: "call",
      func: { type: "var", value: "print" },
      args: [{
        type: "call",
        func: { type: "var", value: "sum" },
        args: [ { type: "num", value: 1 },
                { type: "num", value: 2 } ]
      }]
    }
  ]
}
```
